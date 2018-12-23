---
title: "バーチャルリアリティのアクセシビリティ ― アクセシビリティの祭典2017『話題の技術とアクセシビリティ（IoT、VR、AR、音声など）』事前の論点整理"
date: 2017-05-14T00:16:29+09:00
draft: false
description: "バーチャルリアリティのアクセシビリティについて、関連用語を整理しながら、狭義と広義のそれぞれについて検討しています。"
---

### はじめに

この記事は<a href="http://accfes.com/seminar_page07.html">アクセシビリティの祭典2017『話題の技術とアクセシビリティ（IoT、VR、AR、音声など）』</a>の事前の論点整理として、バーチャルリアリティおよび関連分野のアクセシビリティについて考察したものです。

{{< entry-image src="/images/organize-issues-of-accessibility-of-virtual-reality.jpeg" credit-name="insidethemagic" credit-link="https://www.flickr.com/photos/insidethemagic/14769682616/" >}} [ CC BY-NC-ND](http://creativecommons.org/licenses/by-nc-nd/2.0/)

<!--more-->

### バーチャルリアリティの2種類の定義について

バーチャルリアリティ関連の分野を調べていると、用語の定義が複数あることに気づきました。それらを整理して「バーチャルリアリティ」の定義を広義と狭義の二通りとします。

まず「狭義のバーチャルリアリティ」は、最近話題になっていてる、製品化され販売されている[Microsoft HoloLens](https://www.microsoft.com/ja-jp/hololens)や[Oculus Rift](https://www.oculus.com/rift/)などで、 それが<abbr title="Virtual Reality">VR</abbr>であろうと<abbr title="Mixed Reality">MR</abbr>であろうと、主に視覚と聴覚を利用してバーチャル空間を構築し、そのバーチャル空間に対してハンドジェスチャーや音声(ボイスコマンド)によって指示を出しています。

また、Googleの[Daydream](https://vr.google.com/daydream/)や[Cardboard](https://vr.google.com/intl/ja_jp/cardboard/)などは、スマートフォンをソースとして、ディスプレイの代わりに<abbr title="Head Mounted Display">HMD</abbr>を利用していて 「モバイルVR」と呼ばれます。

これは現在主流の定義であり、例えばVRと(<abbr title="Augmented Reality">AR</abbr>や<abbr title="Augmented Virtuality">AV</abbr>を含む)<abbr title="Mixed Reality">MR</abbr>の区別は「自分の手が見えるかどうか」「視界全てをバーチャルにするか、現前の空間にバーチャルを重ねるか」といった、視覚をベースに区別されているようです(例: [MRとは？ HoloLensのハードウェア／機能／アプリ動作／ユーザー操作 - Build Insider](http://www.buildinsider.net/small/hololens/001))

次に「広義のバーチャルリアリティ」は、研究分野での定義です。例えば[日本バーチャルリアリティ学会による定義](https://vrsj.org/about/virtualreality/)では、人間の五感すべてを拡張し、さらに様々な工夫で、よりリアルに近い臨場感のある環境を構築することを含んだ定義となっています。実際に、研究レベルでは触覚など、人間の臨場感に重要な様々な感覚の拡張を目指して研究が進められています。

バーチャルリアリティのアクセシビリティについて考察するとき、当然ながら狭義のバーチャルリアリティと広義のバーチャルリアリティでは全く状況が異なりますので、まずそれぞれの関連用語を整理したのちに、それぞれのアクセシビリティについて考察することにします。

### バーチャルリアリティ(<span lang="en">virtual reality</span>)

#### 定義(広義)

<blockquote cite="https://vrsj.org/about/virtualreality/" title="日本バーチャルリアリティ学会 » バーチャルリアリティとは">
    <p>みかけや形は原物そのものではないが，本質的あるいは効果としては現実であり原物であること</p>
</blockquote>
<blockquote cite="https://ja.wikipedia.org/wiki/%E3%83%90%E3%83%BC%E3%83%81%E3%83%A3%E3%83%AB%E3%83%AA%E3%82%A2%E3%83%AA%E3%83%86%E3%82%A3" title="バーチャルリアリティ - Wikipedia">
    <p>現物・実物（オリジナル）ではないが機能としての本質は同じであるような環境を、ユーザの五感を含む感覚を刺激することにより理工学的に作り出す技術およびその体系。</p>
</blockquote>

<blockquote cite="http://hapticdesign.org/designer/file006_tachi/" title="舘 暲（東京大学） テレイグジスタンスの提唱者が語る“未来の世界”のつくり方 | HAPTIC DESIGN">
    <p>コンピューターでつくったバーチャルな空間に自分が居るように感じるのがVR。</p>
</blockquote>

#### バーチャルリアリティの分野

##### テレイグジスタンス(<span lang="en">Telexistence</span>;遠隔臨場感)

<blockquote cite="http://telexistence.net/" title="SIG TX">
    <p>テレイグジスタンスは，人間が現前に現存する空間とは別の空間を，高い臨場感をもって体験し行動することを可能とするとともに，自己の存在感をその空間へ拡張するもの</p>
</blockquote>
<blockquote cite="https://ja.wikipedia.org/wiki/%E3%83%86%E3%83%AC%E3%82%A4%E3%82%B0%E3%82%B8%E3%82%B9%E3%82%BF%E3%83%B3%E3%82%B9" title="テレイグジスタンス">
    <p>遠隔地にある物（あるいは人）があたかも近くにあるかのように感じながら、操作などをリアルタイムに行う環境を構築する技術およびその体系のこと</p>
</blockquote>
<blockquote cite="http://hapticdesign.org/designer/file006_tachi/" title="舘 暲（東京大学） テレイグジスタンスの提唱者が語る“未来の世界”のつくり方 | HAPTIC DESIGN">
    <p>遠隔地など自分がいま居る場所と別の場所（実世界）にあるアバターを繋ぐのがテレイグジスタンスです</p>
</blockquote>

##### テレプレゼンス(<span lang="en">Telepresence</span>)

<blockquote cite="http://www.weblio.jp/content/%E3%83%86%E3%83%AC%E3%83%97%E3%83%AC%E3%82%BC%E3%83%B3%E3%82%B9" title="テレプレゼンスとは - IT用語辞典 Weblio辞書">
    <p>テレプレゼンスとは、遠隔地のメンバーとその場で対面しているかのような臨場感を提供する技術のことである。特に、高品質な音声や高解像度の映像などを駆使した、遠隔地のメンバー同士で会議を催すためのシステムを指すことが多い。</p>
</blockquote>

##### テレイマージョン(Teleimmersion)

<blockquote cite="https://www.jgn.nict.go.jp/jgn2_archive/japanese/08-library/meeting_doc/data/ws-08/jgn2-ehara.pdf" title="Teleimmersion Environment over JGN2">
    <p>
        遠隔地にいる人々があたかも同じ部屋にいるかのように自然な対話の実現（高臨場感通信）</p>
</blockquote>

#### 複合現実(MR; <span lang="en">Mixed Reality</span>)

<blockquote cite="https://ja.wikipedia.org/wiki/%E8%A4%87%E5%90%88%E7%8F%BE%E5%AE%9F" title="複合現実 - Wikipedia">
    <p>現実空間と仮想空間を混合し、現実のモノと仮想的なモノがリアルタイムで影響しあう新たな空間を構築する技術全般を指す。ミクスト・リアリティ、複合現実感とも。拡張現実(AR) と拡張仮想 (AV) を包含する概念である。</p>
</blockquote>
<blockquote cite="http://courses.cs.vt.edu/cs5754/lectures/AR-MR.pdf" title="Augmented and mixed reality(AR & MR), Doug Bowman">
    <p lang="en">Refers to a system that combines real and virtual objects and information.</p>
</blockquote>

#### 拡張現実(AR; <span lang="en">Augmented Reality</span>)

<blockquote cite="http://courses.cs.vt.edu/cs5754/lectures/AR-MR.pdf" title="Augmented and mixed reality(AR & MR), Doug Bowman">
    <p lang="en">Refers to a system in which the user views and acts within an enhanced version of the real world. The enhancements are virtual (computer- generated), and can include objects orinformation.</p>
</blockquote>

#### 拡張仮想(AV; <span lang="en">Augmented Virtuality</span>)

<blockquote cite="https://ja.wikipedia.org/wiki/%E6%8B%A1%E5%BC%B5%E7%8F%BE%E5%AE%9F" title="オーグメンテッドバーチャル - Wikipedia">
    <p>仮想世界に現実の情報をオーバーレイさせるものである。</p>
</blockquote>

#### 狭義のバーチャル・リアリティのアクセシビリティについて

現在製品化されている、視覚または聴覚を作り出し・拡張するバーチャル・リアリティ製品の場合、視覚が十分に働かないユーザーにとってアクセシブルではないと考えます。

「モバイルVR」などは特にですが、情報提供の方法が本質的に通常のディスプレイと大差ないため、同じくスクリーンリーダーが必要と思われます。 すなわち、カーソルのような概念を導入して、視覚的に提供される情報について、現在の注目点であるカーソルの現在位置で提供される情報をすべて音声などで伝える必要があると考えます。

また「閃光を利用しない」など、そもそもそもUIとして最低限守るべき事項も存在します。

バーチャルリアリティでは、視覚的に提供される情報がWebよりも膨大であることを考えると、「アクセシブルなVR」の実現には大変な労力が伴うことが予想されます。

これは、現在製品化されている、視覚を利用して現実の拡張や情報提示する拡張現実(AR)や拡張仮想(AV)も、情報の提示の仕方によっては同様であると考えられます。

もう少し発展して、Googleの[Omnitone](http://googlechrome.github.io/omnitone/#home)のような立体音響技術で、音声での代替情報を臨場感をもって提供したり、モーションキャプチャーが可能なシステムの場合、グローブのようなものでバーチャル世界のオブジェクトに手で触れた際の「手触り」フィードバックや、オブジェクトを叩いた音などの音のフィードバックなどがあれば、インタラクションがさらに「マルチモーダル」になると思われます。

しかし、個別の実装である製品におけるアクセシビリティについて、Webと同様に考えることが妥当なのかについては、議論の余地があると考えます。

例えば、[JALによるHoloLens活用事例](http://press.jal.co.jp/ja/release/201604/002643.html?Fa=1)は航空機エンジニアの養成用とのことです。

{{< youtube GjZgI2oDcwM >}}

このシステムで、果たしてすべての情報に対する代替情報の提供は必要でしょうか。

Webは、そもそも情報の利用にあたって利用者を選ばないメディアであるため、コンテンツを正しく実装することでアクセシビリティを高めることができます。

他方、VRやMRは「情報システムのUI実装の一形式」であるとすると、以降ユーザビリティの定義と同様の議論が成り立つと考えられます。

つまり情報システムにはそもそも目的がありターゲットユーザーが存在します。 MRのターゲットユーザーの想定にあたっては、ターゲットユーザーの可能なこと・不可能なことも洗い出されていると想定されます。

ここで、例えば「ターゲットユーザーは十分な視力を持っていること」という前提があれば、そのシステムでは視力が十分ではないユーザーへの代替情報の提供は必要ないと考えるケースはあり得ます。逆に、ターゲットユーザーの中で、必要とされる感覚が十分ではないユーザーをサポートする必要があれば、代替情報などの提供を通じて(いわゆる「合理的配慮」の範囲内で)アクセシブルである必要があると思われます。

つまり、現在製品化されている、HMDなどの個別の製品の個別の実装を取り出してアクセシビリティを議論するのではではなく、VR/MRなどを利用して構築されるサービスのデザインの問題ではないかと思われます。

#### 広義のバーチャルリアリティのアクセシビリティについて

広義のバーチャルリアリティに関しては、基本的にすべての感覚をバーチャル空間に拡張し、特に物に触れた感覚である触覚が拡張されるため、私たちが普段生活しているリアル空間で生活できている限り、バーチャル空間でも不自由なく活動することができると考えられます。

また[東京大学 舘研究室](http://tachilab.org/jp/)では、「バーチャルリアリティは本質的にはテレイグジスタンスと同じである」という概念のもと、遠隔地という別世界において自分の分身となる「分身ロボット」の開発を通じて、[遠隔就労や障害者の就労に関するビジョンが示されています](http://hapticdesign.org/designer/file006_tachi/) 。

つまり、視覚・聴覚だけでなく触覚、運動平衡感覚などがすべて伝えられ、かつ個々の利用者の感覚器や障害に合わせたインターフェースを持つ広義のバーチャルリアリティの世界では、そのシステム自身が支援技術であるだけでなく、身体の能力を飛躍的に向上させるパワードスーツのように機能すると考えられます。
