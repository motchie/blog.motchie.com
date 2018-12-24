---
title: "Amazon Alexaのユーザビリティと新しいパラダイム"
date: 2017-12-22T01:07:53+09:00
draft: false
description: "Amazon Alexaのユーザビリティを考えた結果ユーザビリティの捉え方を変えたほうがいいのではと考えました。"
images: ["/images/main-image-usability-for-amazon-alexa-and-new-paradigm.jpeg"]
---

<section>
    <h3>はじめに</h3>
    <p>この記事は、
        <a href="https://adventar.org/calendars/2332">Amazon Alexa Advent Calendar 2017</a>の22日目の記事です。</p>
    <p>今年の5月に
        <a href="/ja/accessibility/organize-issues-of-accessibility-of-virtual-assistant/">アクセシビリティの祭典でAI音声スピーカーについてお話</a>したり、それを受けて
        <a href="https://accsell.net/podcast/0118.html">AccSellポッドキャストでお話させていただいた</a>りした頃から、主に
        <a href="https://developer.amazon.com/ja/alexa">Amazon Alexa</a>(以下、&quot;Alexa&quot;)をベースに関連資料を読んだり、
        <a href="https://github.com/alexa/alexa-avs-sample-app/wiki/Raspberry-Pi"><abbr title="Alexa Voice Service">AVS</abbr>をRaspberry Piで
        </a>動かしたりしていました。</p>
    <p>ユーザビリティ的にもアクセシビリティ的にも検討する余地が多いなと思っていたところ、
        <a href="https://twitter.com/caztcha/">@caztcha</a>さんが、より広い視点での
        <a href="https://website-usability.info/2017/10/entry_171019.html">
            <abbr title="Voice User Interface">VUI</abbr>ユーザビリティについて記事書かれました</a>。</p>
    <p>この記事についてfacebookでコメントを寄せたところ、そのナレッジをぜひ記事にとcaztchaさんにおっしゃっていただいたことが、この記事のきっかけです。</p>
    <p>と言っても、これは今年の10月頃のお話なのですが、諸事情あってAdvent Calendarの記事になりました。</p>
    <p>caztchaさんの記事をAlexaをベースに読んでいくことを通じて、あらためてAlexaのユーザビリティについて整理して考えていきます。 その結果、従来のユーザビリティ原則の見方を変えざるを得ないと考えるようになりました。
    </p>
    <p>またAlexa界隈で「ユーザビリティ」というと、要望する機能をどのように音声化するかという
        <a href="https://developer.amazon.com/ja/designing-for-voice">音声インターフェース設計</a>が思い浮かびまずが、この記事はAmazon Alexa全体のユーザビリティについて論じていきます。</p>
    <div>
        <img class="entry-image" alt="[イメージ写真]" src="/images/main-image-usability-for-amazon-alexa-and-new-paradigm.jpeg" />
        <p class="entry-image-credit"> Photo by
            <a href="https://visualhunt.com/author/6475d2">portalgda</a> on
            <a href="https://visualhunt.com/re/c28efa">Visualhunt</a> /
            <a href="http://creativecommons.org/licenses/by-nc-sa/2.0/"> CC BY-NC-SA</a>
        </p>
    </div>
</section>

<!--more-->

<section>
    <h3 id="issues">記事の論点</h3>
    <p>caztchaさんの記事は、特定のVUI製品に依存したものではありません。またスマートスピーカー製品自体からVUIまで多くの点について言及されています。caztchaさんの記事の論点のうち、今回取り上げるものの主語を「Amazon Echo」にしたものが以下です。</p>
    <ul>
        <li>Amazon EchoはVUI単体である</li>
        <li>Amazon Echoは見ただけでは、どう操作していいかわかりにくいのでは</li>
        <li>システムの利用に際して、どう使うのか/どんな結果が得られるのかが予想しにくいのでは</li>
        <li>どう操作すればよいか、また操作によって何が起こるかがわかりにくいのでは</li>
    </ul>
</section>
<section>
    <h3>Alexaのフレームワークについて</h3>
    <p>一般に知られているスマートスピーカーであるAmazon Echoは、クラウドベースの音声サービス「Amazon Alexa」によって動作しています。</p>
    <p>Alexaは2つのフレームワークで成り立っています。</p>
    <dl>
        <dt lang="en">Alexa Skills Kit(ASK)</dt>
        <dd>Alexaの「能力」と呼ぶべきSkillを開発するためのフレームワーク</dd>
        <dt lang="en"> Alexa Voice Service(AVS)</dt>
        <dd>Amazon Echoのように、Alexaを利用した音声による入出力を製品で可能にするためのフレームワーク。 マイク、スピーカー、インターネット接続があれば同様の製品を開発ができるとされています。これを利用し、Amazon以外のサードパーティによる製品が多数開発されています。以後、本記事では、こうした製品の汎用的な呼称として「Alexa端末」と表記します。
        </dd>
    </dl>
</section>
<section>
    <h3>Alexaアプリ</h3>
    <p>Alexa端末を購入したユーザーは、それを家庭内の無線LANに参加させたり、自分のAmazon.co.jpアカウントに登録したりするために「Alexaアプリ」を利用します。</p>
    <p>Alexaアプリは、以下の3つの形態で提供されます。</p>
    <ul>
        <li>
            <a href="https://alexa.amazon.co.jp/">Web</a>
        </li>
        <li>
            <a href="https://itunes.apple.com/jp/app/amazon-alexa/id944011620?mt=8">iOSアプリ</a>
        </li>
        <li>
            <a href="https://play.google.com/store/apps/details?id=com.amazon.dee.app&amp;hl=ja">Androidアプリ</a>
        </li>
    </ul>
    <p>このAlexaアプリには上記以外にも多数の機能がありますが、ユーザビリティに関連する機能は以下です。</p>
    <ul>
        <li>発話した指示とAlexaの応答の履歴</li>
        <li>発話の結果録音された自分の声の確認</li>
        <li>発話をAlexaが認識した結果が正しかったかどうかフィードバックを行うリンク</li>
        <li>週間天気予報など、GUIでの表示に適した情報</li>
        <li>Alexaへの指示のサンプル</li>
        <li>Alexaに依頼した買い物リスト、ToDoリスト、リマインダー、アラーム、タイマーなどの状況</li>
        <li>スキルの探索、登録と有効なスキルの管理</li>
        <li>スマートホームスキルの設定と管理</li>
        <li>ヘルプとチュートリアル</li>
    </ul>
    <p>Alexa端末を利用する場合には、コンパニオンアプリとも呼ぶべきAlexaアプリを併用することになりますので、VUI単体ですべてを操作するという不安はなさそうです。</p>
</section>
<section>
    <h3>メンタルモデルについて</h3>
    <p>ユーザーが生物学的あるいは日常生活で得てきた経験や知識が活かせる
        <abbr title="User Interface">UI</abbr>は、使いやすいと言われます。それは、これから操作する対象物の操作や、その結果の振る舞いに対する予測が立つためです。逆に、ユーザーが過去の経験から予測した内容に反する振る舞いが対象物に見られると、フラストレーションを感じます。
    </p>
    <p>ここで重要になる「メンタルモデル」について
        <a href="http://http://www.loftwork.jp/people/staff/hiroki_tanahashi.aspx">棚橋弘季さん</a>は、かつて次のように説明されました。</p>
    <blockquote cite="http://www.coprosystem.co.jp/marketingblog/2011/11/22.html">
        <p>人は未知の状況において行動を起こす際、必ず「こうしたらこうなるはずだ」という予測を立てた上で自身の行動を選択します。簡単にいうと、この「こうしたらこうなるはず」というイメージがメンタルモデルです。未知のモノを使う際にも「このボタンを押すとこうなるのでは？」といったように何らかの操作方法に関するメンタルモデルをイメージした上で操作してみるわけです。</p>
        <p>このとき、メンタルモデルと実装モデルが一致していれば、ユーザーは自分の思ったとおりの結果を得ることができます。しかし、反対にメンタルモデルと実装モデルにギャップがあった場合、使い方を間違えていて思ったとおりの結果が得られなかったり、なんとか使えた場合でも使っていてイライラするなどの不満を感じたりします。もっとひどい場合はそもそも思っていた用途で使うモノではなかったなんてこともありえます。…</p>
    </blockquote>
    <p>このメンタルモデルの重要性について、
        <a href="https://www.nngroup.com/people/jakob-nielsen/">Jakob Nielsen</a>は、次のように表現しています。</p>
    <blockquote cite="https://www.nngroup.com/articles/mental-models/" lang="en">
        <p>Mental models are one of the most important concepts in human–computer interaction (HCI). Indeed, we spend a good deal of time covering their design implications in our full-day training course on
            <a class="new" href="https://www.nngroup.com/courses/hci/" title="Nielsen Norman Group training seminar: detailed course description">User Interface Principles</a>.</p>
    </blockquote>
    <p>ここまで予備知識をつけたうえで、caztchaさんの記事を読んでみます。</p>
    <blockquote cite="https://website-usability.info/2017/10/entry_171019.html">
        <p>VUI におけるインタラクションのトリガーはユーザーの発話であり、入力時にフィーチャーされる機能は基本的にマイクだけです。UI の中に他の視覚的な手がかりが無い (または少ない) ことが多く、Jacob Nielsen の 10 Usability Heuristics で言うところの「Recognition rather than recall (記憶に依存せず、そこにあるものを見て認識できるようにする)」の担保が不十分になりがちです。つまりシステムの利用に際して、どう使うのか/どんな結果が得られるのかが予想しにくく、ユーザーは根拠
            (自信) のないメンタルモデルに全面的に依拠せざるを得ない、という状況に陥りやすいと言えそうです。</p>
    </blockquote>
    <p>このご指摘は、メンタルモデルに関する複数の示唆を含んでいると考えます。Alexa端末をメンタルモデルで考えると、このデバイスに類似したものはこれまで存在していなかったため、過去の経験をそのまま応用することが難しいと考えられます。そのため、ユーザーは新たな体験として、過去の経験を複数組み合わせて端末の使い方を習得していく必要があると考えられます。</p>
    <p>Alexa端末のメンタルモデルをどう考えていけばよいか「過去の経験を複数組み合わせる」視点から、視覚と触覚から形成されるメンタルモデルと聴覚と発話から形成されるメンタルモデルとに分けて考えたいと思います。</p>
    <section>
        <h4>視覚と触覚から形成されるメンタルモデル</h4>
        <p>
            <a href="http://www.jnd.org/" lang="en">Donald Norman</a>は、著書
            <a href="https://www.nngroup.com/books/design-everyday-things-revised/" lang="en">
                <cite>The Design of Everyday Things</cite>
            </a>で、
            <span lang="en">&quot;Principles of user interface design&quot;</span>を示しています。ここに
            <span lang="en">&quot;The visibility principle&quot;</span>が含まれています。</p>
        <dl lang="en">
            <dt>The visibility principle</dt>
            <dd>The design should make all needed options and materials for a given task visible without distracting the user with extraneous or redundant information. Good designs don't overwhelm users with alternatives or confuse with unneeded information.</dd>
        </dl>
        <p>これが「視覚と触覚から形成されるメンタルモデル」の核心であると言ってよいと思います。</p>
        <p>これから設計するユーザーインターフェースが、
            <span lang="en">&quot;The visibility principle&quot;</span>を兼ね備えるために用いられる概念が「シグニファイア(
            <a href="https://www.jnd.org/dn.mss/signifiers_not_affordances.html" lang="en">&quot;signifiers&quot;</a>)」と理解しています。</p>
        <p>かいつまんでご説明すると、設計対象となるハードウェアやソフトウェアのインターフェースを、手に取ったり目で見た際にユーザーに形成されるメンタルモデルが、設計上想定している「デザインモデル」と乖離して使いにくくならないよう、対象物の形状やユーザーインターフェースのデザイン、ボタン等のオブジェクトの形状、ラベル等を工夫することを指します
            <sup>
                <a href="#fn1" id="r1">[1]</a>
            </sup>。</p>
        <p>ひるがえって、
            <a href="https://www.amazon.co.jp/Amazon-Echo-New%E3%83%A2%E3%83%87%E3%83%AB-%E3%80%81%E3%83%81%E3%83%A3%E3%82%B3%E3%83%BC%E3%83%AB-%E3%83%95%E3%82%A1%E3%83%96%E3%83%AA%E3%83%83%E3%82%AF/dp/B071ZF5KCM">Amazon Echo</a>を例にAlexa端末の形状・外観やユーザーインターフェースを見てみると:</p>
        <ul>
            <li>マイクとスピーカー</li>
            <li>マイクのミュートボタン</li>
            <li>セットアップボタン</li>
            <li>状態を表示するリング状の
                <abbr title="Light Emitting Diode">LED</abbr>
            </li>
        </ul>
        <p>以上で、この状況では、とても
            <span lang="en">&quot;The visibility principle&quot;</span>を満たしているとは言えないと判断される場合もあると思われます。</p>
        <p>なお、アメリカ等で販売されている
            <a href="https://www.amazon.com/Amazon-Echo-Show-Alexa-Enabled-Black/dp/B01J24C0TI">Echo Show</a>や
            <a href="https://www.amazon.com/Amazon-VN94DQ-Introducing-Echo-Spot/dp/B073SQYXTW">Echo Spot</a>にはディスプレイが搭載されており、Alexaアプリでのみ表示される、GUI表示が必要なもの(週間天気など)を表示できるほか、テレビ電話機能にも利用されています。</p>
        <p>それでは、Alexa端末はユーザビリティが低いのかという点については、次節
            <a href="#hear">「聴覚と発話から形成されるメンタルモデル」</a>で考えていきます。</p>
        <section>
            <h5>リクエストの方法について</h5>
            <p>記事の中で</p>
            <blockquote cite="https://website-usability.info/2017/10/entry_171019.html">
                入力時にフィーチャーされる機能は基本的にマイクだけです。UI の中に他の視覚的な手がかりが無い (または少ない) ことが多く...
            </blockquote>
            <p>という記述があります。</p>
            <p><span lang="en">&quot;AVS Documentation&quot;</span>の
                <a href="https://developer.amazon.com/ja/docs/alexa-voice-service/audio-hardware-configurations.html#applications">「一般的なアプリケーションのサンプル」</a>では、Alexa端末のリクエスト受付方法として、次の3タイプが示されています。</p>
            <ul>
                <li lang="en">Push-to-talk</li>
                <li lang="en">Tap-to-talk</li>
                <li>音声起動(ウェイクワード)</li>
            </ul>
            <p>例えば、Amazon Echoは既定で音声起動(ウェイクワード)をサポートしており、そのワードは、端末ごとに変更が可能です。執筆時点で
            </p>
            <ul>
                <li lang="en">&quot;Alexa&quot;</li>
                <li lang="en">&quot;Amazon&quot;</li>
                <li lang="en">&quot;Echo&quot;</li>
                <li lang="en">&quot;Computer&quot;</li>
            </ul>
            <p>というウェイクワードに変更が可能です。</p>
            <p>これ以外に、Amazon Echoシリーズは
                <span lang="en">Tap-to-talk</span>に変更する方法も用意されています。そのほか、執筆時点での具体例としては:</p>
            <dl>
                <dt>外出先を想定したAlexa端末</dt>
                <dd>
                    <a href="https://www.amazon.com/dp/B01BH83OOM">Amazon Tap</a>など、外出先での利用を想定したデバイスは、
                    <span lang="en">Push-to-talk</span>が既定のようです。&quot;AVS Documentation&quot;では、ほかにスマートウォッチ等のウェアラブル機器も想定されています。</dd>
                <dt>
                    <a href="https://www.amazon.com/Alexa-Voice-Remote-Amazon-Echo/dp/B01E9AHU8Q" lang="en">Alexa Voice Remote for Amazon Echo and Echo Dot</a>
                </dt>
                <dd>Amazon Echoとの距離が遠い場合、周囲が騒がしい場合、発話が困難なユーザー向けに、Amazon EchoやEcho Dot用のBluetoothリモコンが用意されています。マイクのボタンをタップし、リクエストを発話します。</dd>
                <dt>スマートフォンアプリからのリクエスト</dt>
                <dd>
                    <a href="https://itunes.apple.com/jp/app/ally-for-alexa-voice-services/id1195730692?mt=8">Ally</a>や
                    <a href="https://itunes.apple.com/jp/app/astra-for-alexa-voice-services/id1173026689?mt=8">Astra</a>などのアプリケーションでは、画面上のボタンをタップしてからリクエストを発話します。</dd>
            </dl>
            <p>以上のように、少なくともAlexa端末では、音声起動(ウェイクワード)以外のリクエスト開始方法があります。</p>
            <p>「ボタンを押して話しかける」既存UIで考えると、既存メンタルモデルは、トランシーバーなど(
                <a href="https://ja.m.wikipedia.org/wiki/プッシュ・ツー・トーク" lang="en">Push To Talk</a>)でしょうか。</p>
            <p>ただし、そうは言ってもハードウェアのボタン1つだけであり、このボタンでAlexaの全機能やオプションが把握できる状況ではありません。</p>
        </section>
    </section>
    <section>
        <h4 id="hear">聴覚と発話から形成されるメンタルモデル</h4>
        <blockquote cite="https://website-usability.info/2017/10/entry_171019.html">
            つまりシステムの利用に際して、どう使うのか/どんな結果が得られるのかが予想しにくく、ユーザーは根拠 (自信) のないメンタルモデルに全面的に依拠せざるを得ない、という状況に陥りやすいと言えそうです。
        </blockquote>
        <p>Alexa端末の外観やリクエスト受付がクリアされたところで、いよいよ聴覚と発話から形成されるメンタルモデルについて考えます。</p>
        <p>「ユーザーは会話を通じてAlexa端末とコミュニケーションできます」と言っても、執筆時点では、人間のように自由に会話ができません。理解できることは限られており、会話の形式にもルールがあります。</p>
        <p>Alexaが理解できることは、端的には
            <a href="https://www.amazon.co.jp/gp/help/customer/display.html?nodeId=201608460">ビルトイン機能</a>と、エンドユーザーが
            <a href="https://www.amazon.co.jp/b/ref=nav__ksg?ie=UTF8&amp;node=5262653051">Amazon.co.jp</a>からインストールした スキルということになります。
        </p>
        <p>このうち、Alexaの「能力」である スキルがどんどん増やせることがAlexaの特長の一つとして挙げられているものの、現状自分のアカウントでどのような スキルが利用できるかについては、記憶やAlexaアプリでの確認に頼ることになります。ここを指して
            <q cite="https://website-usability.info/2017/10/entry_171019.html">システムの利用に際して、どう使うのか/どんな結果が得られるのかが予想しにく</q>い側面はあると思われます。</p>
        <p>ただ、これは言わばスマートフォンとスマートフォンアプリの関係と同じと考えられるのではと思います。 ユーザーのスマートフォンは、共通の基本機能はありますが、その大半はユーザーが選択したスマートフォンアプリで構成されます。 そのため、スマートフォンアプリの導入時点で「どう使うのか/どんな結果が得られるのか」理解しているものの積み重ねが、スマートフォンの機能の大半を占めるとも考えられそうです。
        </p>
        <p>同じくスマートフォンのメタファーで考えると、ユーザーが、自分のスマートフォンにインストールしている全アプリの全機能を把握し利用しているというケースも考えにくいです。それは「たくさんのアプリをインストールしたものの、覚えて利用するのはごく一部」という状況と考えられ、必ずしもNormanの言う
            <q>all needed options and materials for a given task visible</q>でなくても、特段ユーザビリティに問題ない可能性もあります。</p>
        <p>つまり、Alexaとスキルの関係も、上記スマートフォンとスマートフォンアプリと同じモデルで考えることができると考えます。自分のAlexa端末で利用できるスキルは、ビルトインスキルはあるものの、大半はユーザーが自ら導入したものになります。この前提では、ユーザーは自分のAlexa端末にどのような指示をすればどのような結果が得られるかについては、大半は理解していると考えられます。</p>
        <p>またスマートフォンアプリと同じく、ユーザーがビルトインおよび自分が導入したスキルを含め、すべての指示を記憶していないケースが多くあると考えられます。この点に関して、Alexaアプリでは、使える指示を「試してみよう！」として定期的に表示しています。</p>
        <figure>
            <img class="entry-image" src="/images/ja-usability-for-amazon-alexa-image-try-saying.jpeg" alt="「試してみよう！」には「『アレクサ、カレンダーに忘年会を追加して』忙しい年末も、カレンダーを連携すれば音声で楽々スケール管理できます」と書かれている" />
            <figcaption style="text-align: center;">図: iOS版Alexaアプリで「試してみよう！」での様子</figcaption>
        </figure>
        <p>また、音声での指示の途中で気づいた不足しているスキルについて、
            <a href="https://www.amazon.com/b?node=13727921011">Amazon.com: Alexa Skills</a>では
            <span lang="en">&quot;Alexa, recommend some skills.&quot;</span>、
            <span lang="en">&quot;Alexa, help me relax.&quot;</span>などのスキルをサジェストするスキルを提示しており、音声でスキルを追加する方法があるようです。
        </p>
    </section>
</section>
<section>
    <h3>ユーザビリティの新しいパラダイム</h3>
    <p>ここまで、<a href="#issues">caztchaさんの記事の論点</a>から始まり、Normanのユーザビリティ原則やメンタルモデルをベースにAlexaについて考えてきました。</p>
    <p>ただ、ここまで見てくると、1つの疑問がわきます。すなわち、Amazon Echo単体ではなくAlexa端末とAlexaアプリをセットで捉えていくと、それほどユーザビリティ上問題がないのではないか？という点です。</p>
    <p>例えば記事にあったNielsenの&quot;Ten Usability Heuristics&quot;にある&quot;Recognition rather than recall&quot;で考えると、確かにAlexa端末自体には備わっていませんが、Alexaアプリでは確認することができます。</p>
    <p>同様にNormanの<span lang="en">&quot;The visibility principle&quot;</span>についても、Alexa端末自体ではとても確認できませんが、Alexaアプリでは確認することができます。</p>
    <p>こうした歴史のあるユーザビリティ理論は、工業製品やGUIソフトウェアといった、それ自体で完結しているもののユーザビリティ研究から生まれた原則と推測されます。しかし、今回のAlexaはじめ、例えば無線LANアクセスポイントとコンパニオンアプリといったように、複数のコンポーネントで1つのシステムを構成するものが増えてきています。そうした、複数コンポーネントによるシステムのユーザビリティ評価では、そのうちの単体を捉えてユーザビリティを議論するのは危険である可能性を考えています。</p>
    <p>これはちょうど、以前私がアクセシビリティの分野で提唱した
        <a href="/ja/accessibility/multimodality-architecture/">マルチモダリティ・アーキテクチャ</a>と状況が同じです。これも同じく、複数のコンポーネントで1つのシステムが構成される場合に、その中の個別の要素ではなく、システム全体として複数のモダリティをサポートすることで、アクセシビリティを評価した方がよいと思われます。
    </p>
    <p>加えて、先ほど書いたように、システムの持つ機能に関しても従来と変わってきました。すなわち、従来のユーザビリティ理論が基礎とする工業製品やGUIソフトウェアは、設計段階からユーザーが利用するまで、およそ機能が変わらないと考えられます。したがって、それらの理論は、その機能を如何にユーザーに伝えるかに苦心した結果と解釈されます。</p>
    <p>ところが、スマートフォンやAlexa端末などは、標準機能はあるものの、ユーザーが機能を追加することができ、その過程でユーザーは個々の機能を理解し納得して追加していくことになります。したがって、工場で実装された機能とは、ユーザーの理解がその点で全く異なります。</p>
    <p>そうして追加された機能の状況がシステムのコンポーネントによって明らかとなり、その主要な使い方が確認できれば、これもユーザビリティ上問題が少ない可能性を考えています。</p>
    <p>以上、Alexaのユーザビリティを考えていくと、ユーザビリティの捉え方が変わったというお話でした。</p>
</section>
<section>
    <h3>脚注</h3>
    <p id="fn1">
        <a href="#r1">[1]</a> 「シグニファイア」と「アフォーダンス」の関係および「誤解されたアフォーダンス」等については、同じくcazchaさんの
        <a href="https://website-usability.info/2006/08/entry_060820.html">アフォーダンスを意識する</a>あるいは
        <a href="http://blog.livedoor.jp/lunarmodule7/archives/3283889.html">アフォーダンスからシグニファイアへ</a>等をご参照ください
    </p>
</section>
