---
title: "Amazon PollyとAmazon CognitoでWebサイトの読み上げシステムを構築する"
date: 2016-12-18T22:58:13+09:00
draft: false
description: "AWS re:Invent 2016で発表されたばかりの新サービスであるAmazon Pollyを使って、従来からあるWebサイトの読み上げシステムを構築してみました。"
images: ["/images/main-image-building-websites-reciting-system-with-amazon-polly-and-amazon-cognito.jpeg"]
---

### はじめに
この記事は、<a href="http://www.adventar.org/calendars/1589">Web Accessibility Advent Calendar 2016</a>の18日目の記事です。

通算3回目になる"Web Accessibility Advent Calendar"への参加ですが、今年は、[Webじゃないアクセシビリティ Advent Calendar](http://www.adventar.org/calendars/1799)にも参加させていただいていて、そちらとの違いを意識しつつ、こちらでは"Web Accessibility"を意識して記事を書いています。

と書きながら、いわゆるWeb技術の「フロントエンド」な話題ではないのは、私がフロントエンド・エンジニアではないことと、個人的に、もうマークアップ関連の話題は出尽くしたと感じるためです。

今年の Accessibility Advent Calendar 2016を眺めていると確実な変化を感じます。それは、Webアクセシビリティのチェックに関するソリューションが、より手軽になってきていることです。

この流れの中で、チェックではなく、別のことで何かできることはないのか...と考え、[AWS re:Invent 2016](https://reinvent.awsevents.com/)で発表されたばかりの新サービスである[Amazon Polly](https://aws.amazon.com/jp/polly/)を使って、従来からあるWebサイトの読み上げシステムを構築してみました。

{{< entry-image src="/images/main-image-building-websites-reciting-system-with-amazon-polly-and-amazon-cognito.jpeg" credit-name="Republica" credit-link="https://pixabay.com/en/users/Republica-24347/" >}}
<!--more-->
### 最初におことわり

今回構築しているのは、いわゆる「サイト閲覧支援ツール」とか「Webサイトの読み上げシステム」などと呼ばれるものですが、「そういうシステムは必ずしもWebアクセシビリティの向上とは関係ない」、「それぞれの利用者のデバイスにインストールされたスクリーンリーダーなどを使えば十分」といった意見があることは重々承知しています。今回は「作ってみた」だけですので、どうぞお手柔らかにお願いします。

### システムの利用

ページのヘッダにある「音声で読み上げ」ボタンをクリックして、少し待っていただければ、ページの内容を読み上げます。

### システムの概要

JavaScriptを使って、各ページのHTMLからテキストを抽出し、Amazon Pollyに渡しています。

Amazon Pollyは、AWSで提供される<span lang="en">text-to-speech</span>システムです。テキストが長くても応答が速い、自然な音声、安価で利用可能であるなどの特徴があります。先日発表されたばかりですが、リージョンこそ限られているものの、最初から日本語もサポートされているのが大変ありがたいです。

今回は、AWSのサービスをJavaScriptから実行できる[AWS SDK for JavaScript](https://aws.amazon.com/jp/sdk-for-browser/)を使って呼び出しています。

ただし、AWSサービスをブラウザから呼び出す際に、AWS認証情報をソースコードに直接記述することはセキュリティ上問題がありますので、[Amazon Cognito](https://aws.amazon.com/jp/cognito/)で"Unauthenticated Identities"を有効にしたフェデレーティッドアイデンティティを構成します。不正利用などに対するセキュリティ対策は、アイデンティティに関連付けられたIAMロールのロールポリシーで行います。

Amazon Pollyへのテキストの引き渡しと、サービスから得られた音声のブラウザでの再生は、[ChattyKathy](https://github.com/ejbeaty/ChattyKathy)のお世話になっております。アクセスキーとシークレットアクセスキーだけでなく、Cognitoを利用した安全なクレデンシャルにも対応しています。

ChattyKathyは、HTML5のaudio要素を動的にコンテンツに追加してブラウザでの音声再生を実現しています。メディアフォーマットとしてmp3を指定しています。

この仕組みのため、今回のWebサイト読み上げシステムは必然的にデバイス依存性が低くなっており、Android上のGoogle ChromeやFirefoxでも再生できることを確認しています。iOSのSafariでは、みなさまご承知の様々な制約により、現状再生できていませんが、おそらく対応できるとみています。

既存のWebサイト読み上げソリューションでマルチデバイスに対応していたりFlashに依存していないものは少ないので、この点ではアドバンテージがあるかと考えています。

### 今後の課題

お試しいただけますと分かりますが、現状は「作ってみた」の域を出ていません。今後、このシステムを改良するとして、いろいろと課題があります。

<dl>
    <dt>一度再生した音声を停止することができない</dt>
    <dd>再生中の音声を停止する仕組みはあるので、実装は可能とみています。</dd>
    <dt>途中で途切れる</dt>
    <dd>一度に渡せる文字列が1000文字までという制限があることと、その制約に対応した実装をしていないためです。これも対処可能です。</dd>
    <dt>読み上げ箇所を反転表示する</dt>
    <dd>そういうのあるといいですよね...。</dd>
    <dt>iOSにきちんと対応する</dt>
    <dd><a href="https://www.ibm.com/developerworks/jp/web/library/wa-ioshtml5/">iOSにおけるHTML5のaudio要素に関する制約</a>を丁寧に調査していけば解決できるのではとみていますが、現状のChattyKathyの実装をかなり修正する必要がありそうな気がしています。</dd>
    <dt>より正確なHTMLの反映</dt>
    <dd>現状は、body要素以下の各要素の<a href="https://developer.mozilla.org/ja/docs/Web/API/Node/textContent">textContent</a>プロパティを使っているだけですが、Amazon Pollyは<a href="http://docs.aws.amazon.com/ja_jp/polly/latest/dg/ssml.html">SSMLをサポートしている</a>ので、例えばHTMLとCSSを加味したSSMLに変換したうえでAmazon Pollyに渡せば、実装者の意図をより正確に読み上げに反映できる可能性があります。</dd>
    <dt>語彙目録(レキシコン)の指定</dt>
    <dd>Amazon Pollyは<a href="http://docs.aws.amazon.com/ja_jp/polly/latest/dg/managing-lexicons.html">語彙目録(レキシコン)の指定をサポート</a>していますので、例えばruby要素をレキシコンに反映することで、単語の読み上げ精度を上げることができると思われます。</dd>
</dl>
