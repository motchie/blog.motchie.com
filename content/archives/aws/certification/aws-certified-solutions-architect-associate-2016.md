---
title: "AWS認定ソリューションアーキテクト–アソシエイト(ASA)に合格しました"
date: 2016-12-30T19:47:33+09:00
draft: false
description: "AWS認定ソリューションアーキテクト–アソシエイトに合格しました。勉強法についてまとめています。"
images: ["/images/main-image-aws-certified-solutions-architect-associate-2016.jpeg"]
---

### はじめに

今月のはじめ、<abbr title="Amazon Web Services">AWS</abbr>認定ソリューションアーキテクト–アソシエイトに合格しました。今年の6月頃から勉強を始めたのですが、半年以上かかってしまいました。

他の方の合格体験や勉強法の記事が多数書かれていますが、今回は勉強法について少し工夫しましたので、その点をお知らせできればと思います。

{{< entry-image src="/images/main-image-aws-certified-solutions-architect-associate-2016.jpeg" credit-name="annazuc" credit-link="https://pixabay.com/en/users/annazuc-224926/" >}}
<!--more-->
### 前提知識や経験など

* AWSアカウントを作って数年になりますが、利用サービスが<abbr title="Elastic Compute Cloud">EC2</abbr>、<abbr title="Simple Storage Service">S3</abbr>とRoute 53など一部にとどまっていました。

* この試験勉強中に、CloudFront、<abbr title="Simple Queue Service">SQS</abbr>、<abbr title="Simple Notification Service">SNS</abbr>を利用する機会がありました。

### 勉強法について

試験勉強として、問題をどんどん解いて覚えていくのが楽かと思っておりますが、他の合格者の方もブログに書いておられる通り、問題集などがほとんどありません。

また「[AWS クラウドサービス活用資料集](https://aws.amazon.com/jp/aws-jp-introduction/)を読む」などの、他の方が薦めておられる勉強法は実践していたものの、[あまり勉強時間が確保できない](/child-rearing/ja-some-ideas-on-self-improvement-for-child-rearing-engineer.html)こともあり、的を絞り切れず時間ばかり経過することが悩みでした。

最終的には、次のような勉強方法で落ち着きました。

#### 基盤とする書籍・問題集

##### [『合格対策　AWS認定ソリューションアーキテクト』](http://www.ric.co.jp/book/contents/book_1043.html)

書籍紹介に「本邦初!」と書かれていますが、上記のように勉強の方法に悩んでいたところに、この本が出版されたのは本当に助かりました。 AWS認定試験やAWSの各サービスについて非常によくまとまっていて、的を絞り込むのに大変助かりました。

私としては、著者の方が[日立インフォメーションアカデミー](https://www.hitachi-ia.co.jp/)の方だということも、親近感として大変大きかったです(笑)

各章ごとに簡単な問題はありますが、実際の試験のレベルよりは大分簡易なもののようで、さらに高度な問題を解いていく必要があります。

#### 参考書

##### [『AmazonWebServices パターン別構築・運用ガイド』](http://www.sbcr.jp/products/4797382570.html)

##### [『Amazon Web Services クラウドネイティブ・アプリケーション開発技法』](http://www.sbcr.jp/products/4797386318.html)

いろいろなブログ記事でも、参考書に挙げられています。私の方も、折に触れて大変参考になりました。

サービスについて学ぶだけであればさらっと読んでしまうようなところ、試験対策として読むと全く違う読み方をするのだなという実感があります。

#### 問題集

##### [AWS Certified Solutions Architect](https://itunes.apple.com/jp/app/aws-certified-solutions-architect/id1059606682?mt=8) (iOS版)

iOSやAndroidで動作する問題集アプリというのはいくつか提供されています。どのアプリがどの程度良いのかなどの検証はできておりませんが、今回はこのアプリのiOS版とタブレットに入れた[Android版](https://play.google.com/store/apps/details?id=com.ionicframework.awsArch)を使いました。

科目(AWSサービス)ごとの問題と、模擬試験、本番試験同様の問題が揃えられています。

問題数はバージョンアップごとに少しずつ増えているようですが、繰り返し勉強していると、同じ問題が頻繁に表示される状況のようでした。ただ、その限られた問題であっても、間違いなく解けるような訓練を繰り返すことは、それなりの力になっている実感はありました。 また、やはり書籍を読む上では気付かなかった、出題される際の観点のようなものを身に着けることができたのは大きかったと思います。

#### 模擬試験

[模擬試験](https://aws.amazon.com/jp/certification/certification-prep/#practice-exam-1)は、試験の1週間前に受験しました。

事前の問題集は、前記のアプリのみ使っていた状況ですが、なんとか合格点に到達することができました。

それまで、ずっと英文の問題集だったため、日本語の問題は新鮮だったことと、出題される中に、問題集にはないサービスが含まれていました。 今振り返ってみると、それらサービスは
[試験ガイド](https://aws.amazon.com/jp/certification/certification-prep/#exam-guide-1)には含まれていたので、試験範囲について、よく確認すべきだったと思います。

本試験に向けては、こうした今までに取り組んでいないサービスに関して基本事項を押さえることと、苦手分野での練習を積むことに注力しました。

模擬試験は有料ですが、場合によっては、(同じ問題が出ることがあるそうですが)本試験直前に再度受験することも視野に入れていました。 結果的に、他の事情も重なり、模擬試験は1回だけで臨むことになりました。

### 今後について

AWS認定試験には他にも種類がありますが、現状、次はシステムアーキテクト・プロフェッショナル(PSA)を目指そうと考えています。

ただ、この記事で紹介した問題集アプリにはプロフェッショナル対応のものがないため、どう勉強していくのか、そこから検討しているところです。
