---
title: "アクセシビリティもシフトレフト！"
date: 2017-05-18T12:34:45+09:00
draft: false
description: "アジャイル開発やセキュリティ分野で注目されている「シフトレフト」がアクセシビリティでも重要であることを説明しています。"
---

<section>
    <h3>はじめに</h3>
    <p>この記事は<a href="http://accfes.com/seminar_page07.html">アクセシビリティの祭典2017『話題の技術とアクセシビリティ（IoT、VR、AR、音声など）』</a>のトークセッションでお話しようと準備した内容をまとめたものです。</p>
    <p>ここまで、<a href="/ja/accessibility/thinking-about-accssibility-of-iot-systems/">IoT</a>や <a href="/ja/accessibility/organize-issues-of-accessibility-of-virtual-reality/">VRシステム</a>や
        <a href="/ja/accessibility/organize-issues-of-accessibility-of-virtual-assistant/">AI音声アシスタント</a>の事例を通して、それらのシステムのアクセシビリティについて見てきました。</p>
    <p>また、これらの事例から、アクセシブルなシステムが備えるべき<a href="/ja/accessibility/multimodality-architecture/">マルチモダリティ・アーキテクチャを提唱</a>しました。</p>
    <p>そうしたものから見えてくる本質とは、何でしょうか。</p>
    <div><img class="entry-image" alt="[イメージ写真]" src="/images/ja-shift-left-in-accessibility.jpeg" />
        <p class="entry-image-credit">Photo credit: <a href="https://www.flickr.com/photos/thomashawk/6948213923/">Thomas Hawk</a> via <a href="https://visualhunt.com/re/2a31c9">VisualHunt.com</a> / <a href="http://creativecommons.org/licenses/by-nc/2.0/"> CC BY-NC</a>
        </p>
    </div>
</section>

<!--more-->

<section>
    <h3><dfn><a href="https://en.wikipedia.org/wiki/Shift_left_testing" lang="en">シフトレフト</a></dfn>とは</h3>
    <p>ソフトウエア開発において、ソフトウエアやシステムのテストを、プロジェクト・ライフサイクル(工程)のより早い段階で実施しようとするアプローチです(従ってプロジェクト・タイムラインの左に移動します)。</p>
    <p>ソフトウエア開発がウォーターフォール型からアジャイルおよびDevOps手法の導入に変化する中で、イテレーションにおける手作業でのテストの実施は作業負荷となるため、テストの自動化によって頻繁に継続的にテストを実施しようとするアプローチです。</p>
    <p>また最近では、開発したシステムのセキュリティや攻撃への堅牢性を高めるためにも、プロジェクト・ライフサイクルのより早い段階から、繰り返しセキュリティを作り込む作業を繰り返すことが重要であると言われるようになってきました(参考: <a href="https://www.slideshare.net/okdt/owasp-meets-kobe-shift-left">OWASP meets KOBE - コピペで作るシステムの終焉とシフトレフト - </a>)。</p>
    <div><img class="entry-image" alt="[説明図です。プログラムやシステムの開発工程を[方針]→[設計]→[実装]→[テスト]→[リリース]と分け、セキュリティやアクセシビリティの工程をテスト段階からより早期の方針段階で実施(シフトレフト)するように呼びかけています。]" src="/images/ja-shit-left-description.png"></div>
</section>
<section>
    <h3>設計段階でのアクセシビリティ</h3>
    <p><a href="/ja/accessibility/thinking-about-accssibility-of-iot-systems/">IoT</a>の記事にも書いていますが、セキュリティとアクセシビリティは、その性質において似ている部分があると、以前から考えていました。</p>
    <p>両者の共通点を挙げてみると:</p>
    <ul>
        <li>どちらも、きちんと実装しないと、金銭的損害や人的損害、事故や損害賠償などの引き金になりかねません</li>
        <li>しかしながら、どちらも、開発・実装が終わったあとの作業と捉えられるケースが多くあります</li>
        <li>したがって、特に開発費や開発期間に余裕がない場合は、優先度を下げたり、後回しにされがちです</li>
    </ul>
    <p>セキュリティの分野においてシフトレフトの重要性が議論され、その確保や実装がシステム開発の設計段階から必要であるように、アクセシビリティの確保も、設計段階などの、より早期の段階からの取り組みが重要であると考えます。</p>
    <p>ここまで見てきた事例についても、あきらかに、システムの設計段階から考慮しておかなければ確保できないアクセシビリティがありました。</p>
    <dl>
        <dt>電源の状態をLEDランプだけで知らせるIoTデバイス</dt>
        <dd>機器あるいは回路の設計段階で、電源の状態を複数のモダリティで提供するよう考慮する必要があります。</dd>
        <dt>ヘッドトラッキング機能付きHMDを使うVRシステム</dt>
        <dd>システムの設計段階から、少なくとも3次元サウンドを併用して、複数のモダリティを確保する必要があります。</dd>
        <dd>当然、コンテンツもそれに合わせて制作する必要があります。</dd>
        <dt>音声のみで指示を出し、音声でフィードバックを返すスマートスピーカー</dt>
        <dd>スマートフォン・アプリなど、別のモダリティで同等の入出力が行える設計である必要があります。</dd>
    </dl>
    <p>皆様おなじみの<abbr title="Web Content Accessibility Guidelines">WCAG</abbr>2.0あるいはJIS X 8341-3では、まずアクセシビリティ方針を立て、次にアクセシビリティ設計を行うように求めています。また、実装においても、ビジュアルデザインの段階では前景色・背景色に関する達成基準が存在することはよく知られていますが、 Webアプリケーションの設計段階から考慮しなければ達成できない基準が複数存在します。例として:
    </p>
    <ul>
        <li>
            <a href="http://waic.jp/docs/UNDERSTANDING-WCAG20/time-limits-required-behaviors.html">達成基準 2.2.1 タイミング調整可能</a>
        </li>
        <li>
            <a href="http://waic.jp/docs/UNDERSTANDING-WCAG20/minimize-error-identified.html">達成基準 3.3.1 エラーの特定</a>
        </li>
        <li>
            <a href="http://waic.jp/docs/UNDERSTANDING-WCAG20/minimize-error-suggestions.html">達成基準 3.3.3 エラー修正の提案</a>
        </li>
        <li>
            <a href="http://waic.jp/docs/UNDERSTANDING-WCAG20/minimize-error-suggestions.html">達成基準 3.3.4 エラー回避 (法的、金融、データ)</a>
        </li>
    </ul>
    <p>以上より、アクセシビリティの確保においては、対象がコンテンツであろうとシステムであろうと、設計段階から考慮しておくことが必要です。</p>
</section>
<section>
    <h3>しかし実際は...</h3>
    <p>ひるがえって現場を見てみると、設計段階からアクセシビリティが考慮されていない事例が多数あります。</p>
    <ul>
        <li>マルチモダリティではないシステム</li>
        <li>コンテンツはアクセシビリティを考慮しているが、Webアプリケーションの仕様としてJIS X 8341-3:2016が求める要素を備えていないシステム</li>
        <li>Webサイトリニューアルの競争入札仕様書が、そもそもアクセシビリティの確保・向上を仕様に盛り込んでいない</li>
        <li>JIS X 8341-3が、コンテンツ制作後の<abbr title="Quality Assurance">QA</abbr>としての試験を求めているためか、アクセシビリティは制作後に考慮するという誤解</li>
    </ul>
</section>
<section>
    <h3>ということで...アクセシビリティもシフトレフト！</h3>
    <p>もちろんこれまでも、<a href="https://www.borndigital.co.jp/book/5388.html">デザイニングWebアクセシビリティ</a>などにおいて、 コンテンツ制作の戦略策定や要件定義の段階からのアクセシビリティ配慮の重要性については知られていました。
    </p>
    <p>しかしながら今回は、Webコンテンツではなく、いわゆるインターネットを利用して提供されるシステムのアクセシビリティというお題をいただきましたので、 その分野における、設計段階からのアクセシビリティ確保という課題に関して、システム開発と同じように、セキュリティと同様に考えてみてはという提案です。
    </p>
    <p>ということで、今日から「アクセシビリティもシフトレフト！」を標語にできればと思います。</p>
</section>
