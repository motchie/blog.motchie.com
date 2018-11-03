---
title: "JIS X 8341-3:2010 達成基準7.3.1.5の日本語実装と「やさしい日本語」の研究"
date: 2015-12-21T00:00:00+09:00
draft: false
description: "WCAG 2.0およびJIS X 8341-3:2010の達成基準3.1.5「読解レベル」について、日本での実装を考えます。Web Accessibility Advent Calendar 2015の20日目の記事です。"
---
### はじめに

この記事は、[Web Accessibility Advent Calendar 2015](http://www.adventar.org/calendars/719)の20日目の記事です。

この記事では、JIS X 8341-3:2010の制定以来、僕がずっと悩んできた達成基準7.3.1.5の日本語での実装方法について、研究した内容を書きたいと思います。

Webアクセシビリティと言うと、マークアップに関する話題がほとんどという印象がありますが、より本質的に[「理解可能なコンテンツ」](http://waic.jp/docs/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head)とするための方法を探ります。

{{< entry-image src="/images/main-image-implementing-wcag-sc315-readability-in-japanese320w.jpg" credit-name="Chasing Daisy" credit-link="https://www.flickr.com/photos/chasingdaisy/5843303770/" >}}
<!--more-->
### 達成基準の内容

まず、達成基準7.3.1.5とはどのような達成基準でしょうか。[WAICによる日本語訳](http://waic.jp/docs/WCAG20/Overview.html#meaning-supplements)には以下のように書かれています。

{{%blockquote "http://waic.jp/docs/WCAG20/Overview.html#meaning-supplements" %}}**3.1.5 読解レベル:** テキストが前期中等教育レベルを超えた読解力を必要とする場合は、補足コンテンツ又は前期中等教育レベルを超えた読解力を必要としない版が利用できる。 (レベル AAA){{% /blockquote %}}

ウェブサイトのコンテンツで、書かれているテキスト(文章)が難解である場合に、その文章の、よりやさしい表現による代替コンテンツを用意せよと書かれています。その代替コンテンツは、要約版などの補足コンテンツか、コンテンツ全体の情報を含む版かを選べるようです。

"Understanding WCAG 2.0"には、[この達成基準に関する意図](http://waic.jp/docs/UNDERSTANDING-WCAG20/meaning-supplements.html#meaning-supplements-intent-head)が記載されています。

{{%blockquote "http://waic.jp/docs/UNDERSTANDING-WCAG20/meaning-supplements.html#meaning-supplements-intent-head" %}}

コンテンツは、可能な限り明快かつ簡潔に書かれているべきである。この達成基準の意図は以下の通りである：

- 難解又は複雑な文章を理解しやすくするために、補足的コンテンツを提供すること。
- そのような補足的コンテンツがどういうときに必要なのかを示す**テスト可能な基準**を定めること。
{{% /blockquote %}}

JIS X 8341-3:2010 およびその基礎である[WCAG 2.0](http://www.w3.org/TR/WCAG20/)では、各達成基準は「テスト可能」である必要があります。
この「テスト可能性」の定義についてWAICのサイトでは{{% q "http://waic.jp/docs/jis2010-understanding/#h2_WebAllyIntro" %}}ツールあるいは専門家によって客観的に判断できるので，適合性評価が可能（なはず）{{% /q %}}と説明されています。

達成基準7.3.1.5は「文章の読みやすさ」に関する達成基準であり、達成基準である以上、それは「テスト可能」である必要があります。今回の達成基準では、そのテスト可能性はどのようにあるべきなのでしょうか。順に考えます。

<dl>
<dt>対象のコンテンツが難解かどうかの判断</dt>
<dd>達成基準に「テキストが前期中等教育レベルを超えた読解力を必要とする場合は」と書かれているので、対象のコンテンツが「前期中等教育レベルを超えた読解力を必要とするほど難解かどうか」の判断がまず必要です。
別の言い方をすれば、この達成基準7.3.1.5を「適用」とすべきか「非適用」とすべきかを判断する基準が必要です。</dd>
<dt>読みやすくしたコンテンツが、本当に読みやすいのか否かの検証</dt>
<dd>テキストが前期中等教育レベルを超えた読解力を必要とした場合、代替コンテンツ(同じ情報を持つ読みやすい版)を用意するか、読みやすい要約を用意します。最後に、用意したコンテンツが読みやすいのか検証するための試験が必要になります。</dd>
</dl>

さすがは達成等級AAAです、文章の読みやすさなんて、どう判断するんだろうか...と思いながら&quot;Understanding WCAG 2.0&quot;を読みます。解説の前半を要約すると次のようになります。

- この達成基準は、読字障害のある利用者の助けとなる(専門知識を持つ高学歴の読者も含め)
- 文章の難しさは、その理解に必要な教育水準から説明される
- 文章をそれ以上読みやすくできない場合、かつ、中学校の教育レベルを超える読解力が必要な場合は補足的コンテンツが必要となる
- よく使われる単語で構成される短い文章は理解しやすく、長い又はなじみのない単語を用いた文章や、長い文章には読解力が必要である

ふむふむ...結局、読みやすさの評価はどうするのかな? と思って読み進めると、関連しそうなのは以下の内容です。

- 読みやすさ(リーダビリティ: readability)は、ウェブページ上の文章から抽出した節を解析することで測定することができる
- 教育者(資格のある教師など)は、文章を読むのに必要とされる教育レベルをローカルの教育標準に従って測定することができる。
- コンテンツのリーダビリティは、抽出した節にリーダビリティの計算式を適用することで判断できることもある
- 多くの言語のリーダビリティ計算式は、単語数、単語長、文の長さと数などからスコアを算出している
- いくつかの言語では、人気のあるソフトウェアのスペルチェック機能でリーダビリティ評価が可能である

具体的な「前期中等教育レベルを超えた読解力を必要とするほど難解かどうか」の判断は、ツールまたは教師のスキルによって行うことができるそうです。

[実装方法](http://waic.jp/docs/UNDERSTANDING-WCAG20/meaning-supplements.html#meaning-supplements-techniques-head)を見ると、「読みやすくする」は、単にテキストの修正だけでなく、
図・シンボルや写真を用いたり、音声化したり、手話バージョンを提供したりすることも含まれているようです。これはこれで視野を広げるよい情報ですが、当初の達成基準からは離れている気もします。
というのも、情報は理解しやすくなるかもしれませんが、「中学校の教育レベルを超える読解力が必要かどうか」の判断がいつまでたってもできません。

注記に関連しそうな記述がありました。

{{% blockquote "http://waic.jp/docs/UNDERSTANDING-WCAG20/meaning-supplements.html#meaning-supplements-techniques-head" %}}

...読み書きと理解に問題を抱えたすべての人の能力に合致する文章を書くことは不可能だろうといわれている。最も明快で、かつ最も簡易な言葉遣いを用いることが非常に望ましいが、
WCAG ワーキンググループではそれが達成されているかどうかを検証する方法を見つけることができなかった。
読解レベルを用いているのは、明快な文章を推奨する達成基準にテスト可能性を持たせるためである。
認知の障害の種類や程度によっては、補足的コンテンツを提供することが効果的な実装方法の一つとなりえる。
{{% /blockquote %}}

これは、文章の読みやすさを「最も読みやすい文章とせよ」という達成基準ではなく、「中学校の教育レベル」のように少しレベルを上げたことに対する注釈のように読めます。
同時に、この解説や実装方法周辺の状況を見ると、読解レベルの設定そのものが難しいのではという印象も受けました。

例えばこの問題を正面から取り上げている実装方法は[G153](http://waic.jp/docs/WCAG-TECHS/G153.html)ですが、ここを見ても状況は同じでした。
訳注として{{% q %}}以下は英語における留意点であると考えられ、日本語の場合には当てはまらないものも含まれているかもしれません。{{% /q %}}と書いていただいています。

どうやら、達成基準7.3.1.5について、日本語での実装については未検討のようです。新たな研究分野が見つかるとワクワクします。「日本語文章の読みやすさの計測」について、少し調べることにしました。

### 文章の読みやすさの計測について
#### 英文でのリーダビリティ指標
文章の読みやすさ(リーダビリティ)について調べていると、どうも英語圏ではかなり古くから取り組まれており、かなり進んでいるようです。

最も有名なものが[<cite>Why Johnny Can't Read?: And What You Can Do About It</cite>](http://www.amazon.co.jp/Why-Johnny-Cant-Read-About/dp/0060913401)の著者で知られる、作家でリーダビリティ専門家である[Rudolf Flesch](https://en.wikipedia.org/wiki/Rudolf_Flesch)が提唱した<dfn><abbr title="Flesch reading-ease score">FRES</abbr></dfn>です。

FRESは、英文の表現や意味ではなく、1文あたりの平均単語数や1単語あたりの平均音節数などを利用して算出される読みやすさの指標です。次のような計算式で算出されます。

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mn>206.835</mn>
  <mo>-</mo>
  <mn>1.015</mn>
  <mo>&InvisibleTimes;</mo>
  <mfenced>
    <mfrac>
      <mi>total words</mi>
      <mi>total sentences</mi>
    </mfrac>
  </mfenced>
  <mo>-</mo>
  <mn>84.6</mn>
  <mo>&InvisibleTimes;</mo>
  <mfenced>
    <mfrac>
      <mi>total syllables</mi>
      <mi>total words</mi>
    </mfrac>
  </mfenced>
</math>

この指標では、最高ポイントが100になり、読みやすい文章ほどスコアが高くなります。スコアが60～70が
<q lang="en">easily understood by 13- to 15-year-old students</q>とのことで、ちょうど「前期中等教育レベル」に合致します。

同じFleschと教育学者[J. Peter Kincaid](https://en.wikipedia.org/wiki/J._Peter_Kincaid)が1975年に開発した
<dfn><abbr title="Flesch–Kincaid grade level">FKGL</abbr></dfn>はFRESの拡張で、計算式から「そのテキストは(米国の)どの学年であれば理解できるのか」を算出することができます。次のような計算式で算出されます。

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mn>0.39</mn>
  <mo>&InvisibleTimes;</mo>
  <mfenced>
    <mfrac>
      <mi>total words</mi>
      <mi>total sentences</mi>
    </mfrac>
  </mfenced>
  <mo>+</mo>
  <mn>11.8</mn>
  <mo>&InvisibleTimes;</mo>
  <mfenced>
    <mfrac>
      <mi>total syllables</mi>
      <mi>total words</mi>
    </mfrac>
  </mfenced>
  <mo>-</mo>
  <mn>15.59</mn>
</math>

この指標は、スコアが8.0の場合は、8年生が理解できる文書であることを意味します。

FRESおよびFKGLとも、テスト文書内の各単語の音節を把握する必要があり、これが計算機での算出には処理が重いとして、音節の必要ない[<dfn><abbr title="Automated readability index">ARI</abbr></dfn>](https://en.wikipedia.org/wiki/Automated_readability_index)など様々な指標が公開されていますが、
Microsoft OutlookとMicrosoft Wordが上記FRESおよびFKGLの算出をサポートしていて簡単に扱えるからか、[<dfn>"Understanding WCAG 2.0"</dfn>](http://waic.jp/docs/UNDERSTANDING-WCAG20/meaning-supplements.html#meaning-supplements-resources-head)の関連リソースにも登場するなど、よく利用されているようです。

Webサービスとして利用できるツールとしては、[Readability-Score.com](https://readability-score.com/)や[The Readability Test Tool](http://read-able.com/)があるようです。

#### 日本語でのリーダビリティ指標

日本語にも、FRESやFKGLのような、文体などの情報をもとに算出されるリーダビリティ指標はあるのでしょうか。

比較的よく参照されているのが、情報処理学会に投稿された論文[建石由佳, 小野芳彦, 山田尚勇: <cite>日本文の読みやすさの評価式</cite>](http://id.nii.ac.jp/1001/00037773/)です。

この論文では、過去の日本語リーダビリティに関する論文の手法の長所・短所を分析した結果、日本語文章の読みやすさの要因を次の4つとしています。

1. 文の平均の長さ(文字)
2. 各文字種(英字、ひらがな、漢字、カタカナ)の連(同一文字種の文字の一続き)の相対頻度
3. 文字種ごとの連の平均長さ
4. 読点の数の句点の数に対する比

論文では、これらの4つの要因を主成分分析を用いて特徴となる成分を抽出し、10変数を用いた線形式を導き出し、その後式を簡略化して、次のような6変数による式を導いています。

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mrow><mi>RS</mi><mo>=</mo></mrow>
  <mrow>
  <mo>-</mo>
  <mn>0.12</mn>
  <mo>&times;</mo>
  <mi>1s</mi>
  </mrow>
  <mrow>
  <mo>-</mo>
  <mn>1.37</mn>
  <mo>&times;</mo>
  <mi>1a</mi>
  </mrow>
  <mrow>
  <mo>+</mo>
  <mn>7.4</mn>
  <mo>&times;</mo>
  <mi>1h</mi>
  </mrow>
  <mrow>
  <mo>-</mo>
  <mn>23.18</mn>
  <mo>&times;</mo>
  <mi>1c</mi>
  </mrow>
  <mrow>
  <mo>-</mo>
  <mn>5.4</mn>
  <mo>&times;</mo>
  <mi>1k</mi>
  </mrow>
  <mrow>
  <mo>-</mo>
  <mn>4.67</mn>
  <mo>&times;</mo>
  <mi>cp</mi>
  </mrow>
  <mrow>
  <mo>+</mo>
  <mn>115.79</mn>
  </mrow>
  <mspace depth="20px" />
</math>

ここで、<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>RS</mi></math>は評価、<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>1s</mi></math>は文の平均の長さ(文字数)、<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>1a</mi></math>はアルファベット連の平均の長さ(文字数)、
<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>1h</mi></math>はひらがな連の平均の長さ(文字数)、<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>1c</mi></math>は漢字連の平均の長さ(文字数)、<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>1k</mi></math>はカタカナ連の平均の長さ(文字数)、
<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>cp</mi></math>は句点あたりの読点の数を表します。

FRESやFKGLは、Microsoft Wordでサポートされていました。この建石論文の評価式については、最近Node.jsで書かれた[textstat](http://efcl.info/2015/11/20/textlint5.0.0/#textstat)にてプラグイン[textstat-plugin-ja](https://github.com/azu/textstat-plugin-ja)の機能として実装されました。
よって、これを用いることで機械的なチェックが可能です。

建石論文の評価式は、ちょうど英文におけるFRESのように、読者に関係のない評価式になっていました。これに対し、長岡技術科学大学の柴崎教授がサイトで公開されている[リーダビリティー公式](http://readability.nagaokaut.ac.jp/research/html/modules/pico/index.php?content_id=10)は、小学1年生から中学3年生までの学年を判定することができる式になっています。

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mi>Y</mi><mo>=</mo><mo>-</mo><mn>0.148</mn><mo>&InvisibleTimes;</mo><mo>&InvisibleTimes;</mo><msub><mi>x</mi><mn>1</mn></msub><mo>+</mo><mn>1.585</mn><mo>&InvisibleTimes;</mo><msub><mi>x</mi><mn>2</mn></msub><mo>-</mo><mn>0.117</mn><mo>&InvisibleTimes;</mo><msub><mi>x</mi><mn>3</mn></msub><mo>-</mo><mn>0.126</mn><mo>&InvisibleTimes;</mo><msub><mi>x</mi><mn>4</mn></msub><mo>+</mo><mn>15.581</mn>
  <mspace depth="20px" />
</math>

ここで、<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Y</mi></math>は学年、
<math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>x</mi><mn>1</mn></msub></math>は文章中の平仮名の割合、
<math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>x</mi><mn>2</mn></msub></math>は1文の平均述語数、
<math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>x</mi><mn>3</mn></msub></math>は1文の平均文字数、
<math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>x</mi><mn>4</mn></msub></math>は1文の平均文節数を表します。

また、柴崎教授らのリーダビリティー・リサーチ・ラボでは、[日本語リーダビリティー測定](http://readability.nagaokaut.ac.jp/readability)を公開されており、前記の式を用いたテキストの判定が可能です。
このツールを用いて、リーダビリティ値が10以下であれば、そのテキストは中学校3年生のレベルになっていると言えます。

ということで、大変長い旅でしたが、当初の目的であった「前期中等教育レベルを超えた読解力を必要とするほど難解かどうか」をツールを用いて判断するめどがついてきました。

### さらに対応が望まれる実装方法を考える: やさしい日本語

ここまで、英語、日本語と、文章の読みやすさを計測する方法を調べてきました。もともと、JIS X 8341-3:2010の達成基準を満たす実装方法を調べるところから出発しているため、客観的な読みやすさの計測に力を入れてきました。

しかし、調べれば調べるほど、モヤモヤがおさまりません。なぜでしょうか。ここまでの公式にあるとおり、これらの指標は文章に含まれる文字種に大きな影響を受けます。また、二重否定や婉曲表現、複雑な係り受けなど、文章表現には一切触れていません。

客観的・機械的な計測は無理かもしれないけど、根本的に表現や内容を書き換えるアプローチはないのだろうか...。また、少し旅に出ることにしました。

#### やさしい日本語

調査の結果わかったことが、<dfn>「やさしい日本語」</dfn>を使う活動がこれにあたるということです。「やさしい日本語」は、主に行政が発信する災害などの情報について、普段使われている言葉を外国人にもわかるように配慮した、簡単な日本語のことです。 

当初[弘前大学人文学部 社会言語学研究室](http://human.cc.hirosaki-u.ac.jp/kokugo/)から始まった活動とのことですが、東日本大震災以降、全国の自治体のサイトにて、やさしい日本語を使った情報発信が行われているようです。

書き換えの例:

<dl>
<dt>津波災害から身を守るためには「日頃の備え」と「迅速な避難」が必要です。</dt>
<dd><ruby>津波<rt>つなみ</rt></ruby>から<ruby>自分<rt>じぶん</rt></ruby>を<ruby>守<rt>まも</rt></ruby>るためには「ふだんの<ruby>準備<rt>じゅんび</rt></ruby>」と
「<ruby>早<rt>はや</rt></ruby>い<ruby>避難<rt>ひなん</rt></ruby>(<ruby>早<rt>はや</rt></ruby>く<ruby>逃<rt>に</rt></ruby>げること)」が<ruby>必要<rt>ひつよう</rt></ruby>です。</dd>
</dl>

既存の文書をやさしい日本語に書き換えるためのルールや基準が公開されています。

- [「やさしい日本語」](http://human.cc.hirosaki-u.ac.jp/kokugo/EJyasashisa-kijyun.html)におけるやさしさの基準について
- [「やさしい日本語」にするための12の規則](http://human.cc.hirosaki-u.ac.jp/kokugo/EJ9tsukurikata.ujie.htm)

取り組みとしては自治体の災害対策が主流ですが、NHKによる[NEWS WEB EASY](http://www3.nhk.or.jp/news/easy/)のような、やさしい日本語によるニュースサイトや、[MATCHA](http://mcha-easy.com/)のようなWebマガジンにも広がりを見せています。

よって、難解な文章を達成基準7.3.1.5をより高いレベルで適合とするには:

1. 「やさしい日本語」のルールに基づいて全面的に書き換える
2. 柴崎教授らの[日本語リーダビリティー測定](http://readability.nagaokaut.ac.jp/readability)で検証を行う

という作業を行うことが、「さらに対応が望まれる実装方法」だと考えます。

### 参考リンク

- [読みやすさを考える](http://www.amudesu.co.jp/legibility/legi-index.html)
- [伝わるデザイン｜研究発表のユニバーサルデザイン](http://tsutawarudesign.web.fc2.com/)
- [読みやすさの評価指標（1） - 読書的な何か。](http://doksyo-tek.hatenablog.com/entry/2015/05/01/093751)
- [読みやすさの評価指標（2） - 読書的な何か。](http://doksyo-tek.hatenablog.com/entry/2015/05/19/104050)
- <cite>[William H. DuBay, The Principles of Readability](http://www.impact-information.com/impactinfo/readability02.pdf)</cite>

### <time datetime="2015-12-21">明日</time>は!

<time datetime="2015-12-21">明日12月21日</time>は、[WEBTENNA](http://www.adventar.org/users/6654)さんによる「色について（仮）」です。お楽しみに!
