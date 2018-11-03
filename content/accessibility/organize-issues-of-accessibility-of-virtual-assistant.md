---
title: "AI音声アシスタントのアクセシビリティ ― アクセシビリティの祭典2017『話題の技術とアクセシビリティ（IoT、VR、AR、音声など）』事前の論点整理"
date: 2017-05-16T14:00:39+09:00
draft: false
description: "AI音声アシスタントの製品や機能を整理し、どのようなユーザーにどのようなメリットがあるか考察しています。"
---

### はじめに

この記事は<a href="http://accfes.com/seminar_page07.html">アクセシビリティの祭典2017『話題の技術とアクセシビリティ（IoT、VR、AR、音声など）』</a>の事前の論点整理として、「AI音声アシスタント」と呼ばれるもののアクセシビリティについて考察したものです。

{{< entry-image src="/images/organize-issues-of-accessibility-of-virtual-assistant.jpeg" credit-name="Samsung Newsroom" credit-link="https://www.flickr.com/photos/samsungtomorrow/16219738582/" >}}<a href="http://creativecommons.org/licenses/by-nc-sa/2.0/"> CC BY-NC-SA</a>

<!--more-->
<section>
    <h3>製品・サービスの整理</h3>
    <p>ガートナーによれば、<a href="http://www.gartner.com/newsroom/id/3464317">世界のスマートスピーカーの市場規模は、2020年に20億ドルに達すると予想</a>されるなど、 AI音声アシスタントは、まさに「話題の技術」なのだと痛感しています。この調査中にも、いくつものアップデートがあり、情報をまとめる作業に影響しました。
    </p>
    <p>前回の<a href="/accessibility/ja-organize-issues-of-accessibility-of-virtual-reality.html">バーチャルリアリティのアクセシビリティ</a>と同様、「AI音声アシスタント」についても、まずは製品や関連するサービスの整理から始めたいと思います。</p>
    <p>いずれのサービスも、<abbr title="Artificial Intelligence">AI</abbr>にあたる部分はクラウドで提供されているようですが、 ユーザーとのインターフェースに関して、ざっと調べた限りでは、以下の2つに分類できそうです。</p>
    <ol>
        <li>いわゆる「スマートスピーカー」など、独立したデバイスとしても動作するもの</li>
        <li>ハードウェアではなく、スマートフォンのアプリケーションなどとして動作するもの</li>
    </ol>
    <p>今回調べたものの一覧を表「AI音声アシスタント製品やサービスの一覧」に示します。</p>
    <table>
        <caption>AI音声アシスタント製品やサービスの一覧</caption>
        <thead>
            <tr>
                <th>名称</th>
                <th>ベンダ</th>
                <th>提供形態</th>
                <th>アプライアンス</th>
                <th>ハードウェアSDK</th>
                <th>スキルSDK</th>
                <th>指示方法</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><a href="https://www.apple.com/jp/ios/siri/">Siri</a></td>
                <td>Apple</td>
                <td>
                    <ul>
                        <li>iOSの機能</li>
                        <li>macOS の機能</li>
                    </ul>
                </td>
                <td>なし</td>
                <td>なし</td>
                <td><a href="https://developer.apple.com/jp/sirikit/">SiriKit</a></td>
                <td>
                    <ul>
                        <li>音声</li>
                        <li>テキスト</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td><a href="https://assistant.google.com/">Google Assistant</a></td>
                <td>Google</td>
                <td>
                    <ul>
                        <li>Android、Android Wearの機能</li>
                        <li>iOSアプリケーション</li>
                        <li>Google Alloチャット</li>
                    </ul>
                </td>
                <td><a href="https://madeby.google.com/home/">Google Home</a></td>
                <td><a href="https://developers.google.com/assistant/sdk/">Google Assistant SDK</a></td>
                <td><a href="https://developers.google.com/actions/develop/sdk/">Actions SDK</a></td>
                <td>
                    <ul>
                        <li>音声</li>
                        <li>テキスト</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td><a href="https://developer.amazon.com/ja/alexa">Alexa</a></td>
                <td>Amazon</td>
                <td>ハードウェア</td>
                <td>
                    <ul>
                        <li>
                            <a href="https://www.amazon.com/Amazon-Echo-Bluetooth-Speaker-with-WiFi-Alexa/dp/B00X4WHP5E">Amazon Echo</a></li>
                        <li><a href="https://www.amazon.com/All-New-Amazon-Echo-Dot-Add-Alexa-To-Any-Room/dp/B015TJD0Y4">Amazon Echo Dot</a></li>
                        <li>
                            <a href="https://www.amazon.com/dp/B01J24C0TI">Amazon Echo Show</a></li>
                    </ul>
                </td>
                <td><a href="https://developer.amazon.com/ja/alexa-voice-service">Alexa Voice Service</a></td>
                <td><a href="https://developer.amazon.com/ja/alexa-skills-kit">Alexa Skills Kit</a></td>
                <td>音声</td>
            </tr>
            <tr>
                <td><a href="https://www.microsoft.com/ja-jp/windows/cortana">Cortana</a></td>
                <td>Microsoft</td>
                <td>
                    <ul>
                        <li>Windows 10その他のOS機能</li>
                        <li>iOS、Androidのアプリケーション</li>
                        <li>スマートスピーカー</li>
                    </ul>
                </td>
                <td>
                    <a href="http://www.harmankardon.com/invoke.html">Harman Kardon Invoke</a>
                </td>
                <td><a href="http://cortanadevicesdksignup.azurewebsites.net/">Cortana Devices SDK</a></td>
                <td><a href="https://developer.microsoft.com/en-us/windows/projects/campaigns/cortana-skills-kit">Cortana Skills Kit

</a></td>
                <td>
                    <ul>
                        <li>音声</li>
                        <li>テキスト</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td><a href="https://clova.ai/ja">Clova</a></td>
                <td>LINE</td>
                <td>
                    <ul>
                        <li>モバイルアプリケーション</li>
                        <li>スマートスピーカーなど</li>
                    </ul>
                </td>
                <td>
                    <ul>
                        <li>WAVE</li>
                        <li>FACE</li>
                    </ul>
                </td>
                <td>Clova Interface Connect</td>
                <td>Clova Extension Kit</td>
                <td>音声?</td>
            </tr>
        </tbody>
    </table>
</section>
<section>
    <h3>AI音声アシスタントの主要な機能や利点</h3>
    <p>前掲の表から、現状のAI音声アシスタントの主要な機能や利点は、以下が考えられます。</p>
    <ul>
        <li>音声での「呼びかけ」で使える(特定のキーワードを「名前」とし、毎回そのキーワードで呼びかける)</li>
        <li>指示語を含む自然言語をある程度柔軟に解釈する</li>
        <li>回答ごとにユーザーの好みを記憶し、次回以降の回答への反映</li>
        <li>(スピーカーなどの場合)ハンズフリーで操作できる</li>
        <li>呼びかけて達成できる機能が豊富</li>
        <li>同じ機能をモバイルアプリを起動して呼び出すのに比べ、操作のステップが少ない</li>
        <li>(一部のサービスは)呼びかけて達成できる機能を「スキル」と呼び、そのSDKを解放することで、サードパーティの参加を促し裾野を広げる</li>
        <li>(一部のサービスは)各種デバイスへの組込もSDKとして開放することで、サードパーティの参加を促す</li>
    </ul>
</section>
<section>
    <h3>AI音声アシスタントのアクセシビリティ</h3>
    <p>では、こうしたAI音声アシスタントのアクセシビリティについては、どのように考えればよいでしょうか。</p>
    <p>Webアクセシビリティ基盤委員会は、<a href="http://waic.jp/docs/jis2010/understanding/201008/#h2_WebAllyIntro">『Webアクセシビリティ概論』</a>の中で、「多様なユーザー」について下記を挙げています。</p>
    <blockquote cite="http://waic.jp/docs/jis2010/understanding/201008/#h2_WebAllyIntro">
        <dl>
            <dt>特別な配慮を必要としないユーザ</dt>
            <dd>（健康な成年男子など）</dd>
            <dt>感覚機能に配慮すべきユーザ</dt>
            <dd>
                <ul>
                    <li>視覚に頼れないユーザ</li>
                    <li>視力に配慮すべきユーザ</li>
                    <li>聴覚に頼れないユーザ</li>
                    <li>聴力に配慮すべきユーザ</li>
                </ul>
            </dd>
            <dt>運動機能や体格に配慮すべきユーザ</dt>
            <dd>
                <ul>
                    <li>車椅子利用者</li>
                    <li>手が使えないユーザ</li>
                    <li>動作に配慮すべきユーザ</li>
                    <li>筋力の弱いユーザ</li>
                    <li>発話に配慮すべきユーザ</li>
                    <li>左利きユーザ</li>
                    <li>小さい／大きいユーザ</li>
                </ul>
            </dd>
            <dt>認知機能に配慮すべきユーザ</dt>
            <dd>
                <ul>
                    <li>初心者／熟練者</li>
                    <li>理解が苦手なユーザ</li>
                    <li>日本語・外国語が読めないユーザ</li>
                </ul>
            </dd>
            <dt>そのほか</dt>
            <dd>デモグラフィック（社会的）や文化的な差異に対して配慮すべき場合</dd>
        </dl>
    </blockquote>
    <p>以降、この分類を基に、AI音声アシスタントの利用にメリットがある利用者、そうではない利用者について考察します。</p>
    <p>まずは、いわゆる「スマートスピーカー」と呼ばれるアプライアンスでのユースケースで検討します。</p>
    <dl>
        <dt>特別な配慮を必要としないユーザ</dt>
        <dd>利用できる機能・サービスは限定的ながら、ハンズフリーで利用できる点はメリットがあると考えられます。</dd>
        <dt>視覚に頼れないユーザ / 視力に配慮すべきユーザ</dt>
        <dd>支援技術なしで画面が利用できない/困難であるユーザーにとってはメリットがあると考えられます。</dd>
        <dt>聴覚に頼れないユーザ / 聴力に配慮すべきユーザ</dt>
        <dd>音声以外の入出力チャネルがない場合は、そもそも利用できない/利用が困難と思われます(音量を大きくしてカバーする?)</dd>
        <dt>発話に配慮すべきユーザ</dt>
        <dd>音声以外の入出力チャネルがない場合は、そもそも利用できない/利用が困難と思われます</dd>
        <dt>運動機能や体格に配慮すべきユーザ(それ以外)</dt>
        <dd>キーボード入力やマウス入力に比べ、ハンズフリーで利用できる点がメリットになると考えられます。</dd>
        <dt>認知機能に配慮すべきユーザ</dt>
        <dd>PCやタブレットなどの初心者にとっては、より簡単に機能やサービスが利用できるメリットがあると考えられます。</dd>
        <dd>理解が苦手なユーザーも、状況によっては、PCやタブレットを利用するよりメリットがあると考えられます。</dd>
        <dd>言語に関しては、ユーザーの母国語がサポートされている場合は、特に問題にならないと考えられますが、指示文が平易な単語であるかは配慮が必要と思われます。</dd>
        <dt>そのほか</dt>
        <dd>社会的/文化的な差異に対しては、AI音声アシスタントのスキル側での配慮が求められるケースが考えられます。</dd>
    </dl>
<p>「スマートスピーカー」として提供されていないケースにおいては、上記に加え、AI音声アシスタント機能を起動するまでのプロセスが追加になると考えられます。従って、「ハンズフリー」が完全なハンズフリーでなくなったり、機能を起動するまでの間の追加の操作は、PCやスマートフォンなどの支援技術を利用する必要があります。
</p>

<h3>AI音声アシスタントをよりアクセシブルにするには</h3>
<p>それでは、上記を踏まえ、よりアクセシブルなAI音声アシスタントには、何が求められるでしょうか。その点については、<a href="http://accfes.com/seminar_page07.html">当日</a>お話できればと思います。お楽しみに！</p>
