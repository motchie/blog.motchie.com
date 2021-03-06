---
title: "Alexaでメールを読み上げられるスキル「音声メールM」リリースしました"
date: 2018-02-15T22:07:18+09:00
draft: false
description: "2017年末から個人的に開発していたMicrosoftオンラインサービス(Outlook.com、Exchange Online、Office 365)のメールを読み上げるAlexaスキルが公開されました。"
images: ["/images/main-image-alexa-voice-mail-m.png"]
---

<section>
    <h3>はじめに</h3>
    <p>本日、私が開発したAlexaスキル「音声メールM」が審査を通過して公開になりました。</p>
    <p>「Alexaスキル」は、<a href="/ja/amazon-alexa/usability-for-amazon-alexa-and-new-paradigm/">以前の記事</a>でもご紹介しましたが、 Amazon Echoなどのスマートスピーカーに対して追加できる「能力」であり、スマートフォンにおけるアプリのようなものです。</p>
    <p>「音声メールM」は、Alexaスキルの「アカウントリンク」機能を利用し、Microsoftオンラインサービス(<a href="https://outlook.live.com/owa/">Outlook.com</a>、<a href="https://products.office.com/ja-jp/exchange/exchange-online">Exchange Online</a>、<a href="https://products.office.com/ja-jp/business/office">Office 365</a>)のメールアドレスに届いたメールの冒頭を読み上げることができます。今のところ、届いたメールを読み上げることが可能で、メールの送信はできません。</p>
    <p>Alexa Appのスキルページにて、しばらくは「新着」に、以後は[仕事効率化]カテゴリーかキーワード「音声メール」で検索いただければ見つけていただけます。</p>
    <p>この記事では、スキルの簡単な使い方をご紹介します。</p>
    <div>
        <img class="entry-image" alt="[イメージアイコン]" src="/images/main-image-alexa-voice-mail-m.png" />
    </div>
</section>

<!--more-->

<section>
    <h3>前提</h3>
    <section>
        <h4>アカウントリンク</h4>
        <p>このスキルをご利用いただくには、「アカウントリンク」の操作が必要です。</p>
        <ol>
            <li>Alexa Appの[スキル]で[音声メールM]を検索します。</li>
            <li>「有効にする」ボタンをクリックします。</li>
            <li>スキルの画面が別ウィンドウに表示されますので、[Microsoftアカウント / 職場または学校アカウントでサインイン]ボタンをクリックします。</li>
            <li>Microsoftオンラインサービスのログイン画面が表示されますので、お持ちのアカウントでログインしてアカウントをリンクさせます。 </li>
            <li>[音声メールM が正常にリンクされました。]と表示されればアカウントリンクに成功しました。このウィンドウを閉じることができます。</li>
        </ol>
    </section>
</section>
<section>
    <h3>使い方</h3>
    <p>Alexaに話かけてメールの内容を読み上げてもらいましょう。</p>
    <section>
        <h4>「アレクサ、音声メールを開いて」</h4>
        <p>未読メールの件数を読み上げます。</p>
    </section>
    <section>
        <h4>「アレクサ、音声メールを開いて未読メールをチェック」</h4>
        <p>アカウントの未読メールの件数を読み上げ、その後未読メールの受信日時、件名、本文を1通ずつ読み上げます。</p>
        <ul>
            <li>未読メールは、Outlookの「受信トレイ」のみを対象としています。</li>
            <li>「優先受信トレイ」には対応していないため、「その他」にある低優先フォルダ内の未読メールも対象になります。</li>
            <li>本文はHTMLメールであってもテキストのみで、いくつかの記号を削除し、最大でも冒頭の250文字程度を読み上げます。</li>
            <li>読み上げられるメールの数は最大で25通です。</li>
            <li>読み上げた未読メールを既読にすることは行っていません。現時点ではメールの送信には対応していません。</li>
        </ul>
    </section>
    <section>
        <h4>「アレクサ、今日のメール/昨日のメール/先週月曜日のメールをチェック」</h4>
        <p>指定された日付のメールを最新のものから順に読み上げます。ここでは、未読/既読を区別していません。</p>
        <ul>
            <li>ここで対象となるメールは、Outlookの「受信トレイ」のみを対象としています。</li>
            <li>「優先受信トレイ」には対応していないため、「その他」にある低優先フォルダ内のメールも対象になります。</li>
            <li>読み上げる内容、本文の読み上げルール、メールの送信に対応していない点は未読メールと同じです。</li>
        </ul>
    </section>
</section>
<section>
    <h3>スキルのお問い合わせなど</h3>
    <p>スキルを利用されるうえでのお問い合わせやフィードバックについては、Alexa Appのスキル画面からフィードバックを送信いただけます。</p>
</section>
