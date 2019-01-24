# MarkdownとPandocの指針

研究に活きるMarkdownとPandocの使い方を紹介します．

## Markdownとは <!-- {{{ -->

[Markdown](https://ja.wikipedia.org/wiki/Markdown)は，軽量[マークアップ言語](https://ja.wikipedia.org/wiki/マークアップ言語)の一種などと説明されるが，あまり詳しいことは気にしなくてよい．  
ものすごくざっくり言うと，"Markdownとは，コマンド(のようなもの)で文字の大きさや書式を指定する書き方"のことである．

一応，コマンドのようなもので書式を指定するので，**Markdownを使いこなすために覚えなければいけないことは多少ある．**  
ただ，その覚えなければいけないこと(文法だと思ったらよい)は，かなり少ないし，しかも直感的なので，想像以上に簡単だと思う．  
習うより慣れろの精神で，まずは[チュートリアル](http://www.markdowntutorial.com/lesson/1/)してみるのが良いだろう．

<!-- }}} -->

## Markdownのメリット <!-- {{{ -->

Markdownは，以下の様な素晴らしい点がある．

いちいちボタンをクリックしなくても，太字や斜体などの文字装飾ができる  
: Wordだと，わざわざマウスを動かして，文字を選択して`Ctrl-I`とか斜体ボタンを押して，もともと編集していた場所に戻って…というクソ以下の手順があるが，Markdownでは，この単語を斜体にしたいなーと思ったら，**置換機能などで一気に書式を変換できる．**

文字だけで構成されるので，置換や検索が簡単  
: 上記にも例示したように，すべて文字だけで構成されているので，**置換を使った書式の指定や，斜体の単語だけ検索(遺伝子名のチェックなどにものすごく便利)などが可能になる．**

アウトラインで書く習慣がつく  
: [Whitesides研の論文の書き方](https://www.chem-station.com/blog/2009/12/whitesides_group_writing_a_pa.html)や近藤滋が推奨するように，アウトラインとして論文を書くのが良いとされているが，Markdownは，アウトライン的に(構造的/階層的に)書くように出来ているので，頭を整理しながら文章が書ける．

これ以外にも，

- Gitで管理できる
- プレーンテキストなので，プログラムを組んで複雑なテキスト処理もできる
- ファイルサイズが小さい
- ドキュメントのデファクトスタンダードになっている
- HTML記法も使える
- HTMLコメントの挿入ができる
- Introduction, Result, Discussion... (もちろんもっと細かい区分でも)をファイルを分けて書けるので，フォルダの整理がしやすい
- etc.

と，良いことが本当にたくさんある．

<!-- }}} -->

## 初心者がMarkdownに心配すること <!-- {{{ -->

本当に覚えられるのか  
: 想像以上に簡単です．

文字だけのファイルって，図は入れられるの?  
: [図の挿入](https://gist.github.com/Tatzyr/3847141)も簡単です．

じゃあ表は入れられる?  
: [楽勝です](https://qiita.com/zakuroishikuro/items/f33929eab9d55c5bd073)．

論文書くためにはReferenceも入れなきゃだけど，さすがに無理でしょ?  
: Referenceを自動で作成する方法があります(後述)．  
  (でもHTMLファイルにはできないのが残念．)

でもボスにはWordファイルにして渡すし...  
: [Wordファイル，PDFファイル，HTMLファイルへの変換](https://qiita.com/sky_y/items/80bcd0f353ef5b8980ee)は一瞬でできます．  
  なんなら，[PowerPointファイル](https://qiita.com/sky_y/items/f38db5dd69720e5ca0cf)だって作れます(マジで)．  
  当然，挿入した図は，WordやPDF，HTMLでも正しく挿入されます．

数式を入れたいけど無理よね  
: [LaTeX記法による数式記述](https://qiita.com/Kumassy/items/5b6ae6b99df08fb434d9#式の書き方)ができるし，Wordに変換しても問題なく表示されます．  
  HTMLではできないけど...

目次くらい自動で入れられないのか  
: Wordファイルではできないけど，[HTMLファイルとPDFファイルなら目次の自動作成](https://www.yamamanx.com/pandoc-pdf-latex-header/)ができます．

さすがに分子式は無理でしょ  
: 追加のプラグインは必要ですが，[分子式だって記述](https://qiita.com/Kumassy/items/5b6ae6b99df08fb434d9#分子式を書く)できます．

ページ数の挿入は?  
: 当然できます．

やっぱり覚えるのが面倒...  
: 覚えた時間は簡単に取り返せるくらい，書くスピードが上がります(体験者談)．

Markdownと，後述するPandocを用いることで，サクサクプロトコル，覚書などが書けるようになります．  
(論文もサクサク書けるようになりたいけど，個人的な能力の問題でできない)  
論文を書くために必要十分の機能がMarkdownとPandocには備わっているので，安心してWordから乗り換えましょう．

<!-- }}} -->

## Markdownの勉強方法 <!-- {{{ -->

1. [チュートリアル](http://www.markdowntutorial.com/lesson/1/)をしましょう．  
   チュートリアルが終われば，基本的な文法は勉強が終わっています．  
2. [このへん](http://www.grkt.com/2013/01/14/1422)や[このへん](https://qiita.com/tbpgr/items/989c6badefff69377da7)を読んで，チュートリアルの復習をしましょう．  
3. わからないことは[ググりましょう](https://www.google.co.jp/search?q=markdown%20%E6%94%B9%E8%A1%8C%20%E6%96%87%E6%B3%95)．  
4. あとは，[HackMD](https://hackmd.io)や[Simplenote](https://simplenote.com)などに登録して，自分用のメモをMarkdownでガシガシ書いていきましょう．
5. [Atom](https://atom.io)に[Markdownプレビューワのプラグインをいれて](https://qiita.com/kouichi-c-nakamura/items/5b04fb1a127aac8ba3b0)，日常生活にMarkdownを取り入れましょう．

日常使いする文には，Markdown Previewerがあると便利です．  
[こんな感じでググって](https://www.google.co.jp/search?q=markdown%20previewer%20software)，自分に合うものを探しましょう．

<!-- }}} -->

## Pandocとは <!-- {{{ -->

さて，上述の方法だけでは，MarkdownをWordファイルやPDFファイルに変換することは出来ません．  
Markdownの変換のデファクトスタンダードになっているのが，[Pandoc](https://pandoc.org)です．  
日本語の詳しい情報は[日本Pandocユーザ会](http://sky-y.github.io/site-pandoc-jp/)に詳しいです．

Pandocとは，ざっくりいうと，MarkdownやHTML，Wordなどのファイルを，異なる形式のファイルに変換するソフトのことです．  
今回はMarkdownからの変換しか扱いませんが，HTMLからの変換なども便利です．

<!-- }}} -->

## Pandocの導入 <!-- {{{ -->

1. [インストール方法は自分で調べましょう](https://www.google.co.jp/search?q=pandoc%20%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%20%E6%96%B9%E6%B3%95)．
2. 初心者向けの記事[たとえば](https://qiita.com/sky_y/items/5fd5c9568ea550b1d7af)を読みましょう(これ以外にも自分で[ググりましょう](https://www.google.co.jp/search?q=pandoc%20%E5%88%9D%E5%BF%83%E8%80%85))．

<!-- }}} -->

## Pandocで本記事と同じ様式のHTMLを作る <!-- {{{ -->

Pandocは，もう使える状態であるとします．  

Pandocを用いてMarkdown -> HTML変換をしましょう．
HTMLファイルでドキュメントを残す利点は，

- 誰が見ても(ほぼ)同じ見た目にできる
- デフォルトではウェブブラウザによって閲覧されるので，故意でないかぎり，文章の変更ができない
- 新しくメモ帳などでの閲覧がされないので，アプリを開きすぎなくて済む
- スマホでも読める
- ボスのような古い人間でも，開いて読むことができる!

などなどあるので，マスターして損はない．

まず，CSSをダウンロードしましょう．  
CSSとは，HTMLファイルの見た目を制御する枠組みのような存在である．  
たとえば，"表だけ見た目を変えたい"というときがあったとする．  
いちいち，HTMLファイルそのものに見た目を制御する命令を書いていると，HTML中で表の見た目を記載している部分を**すべて**変更しなければいけなくなる．  
CSSでは，"表に関して，こういう見た目にせよ"という枠組みを与えるので，CSSだけ変更すれば，HTML中のすべての表の見た目を変えられる．

能書きはこのくらいにして，実際のCSSファイルだが，`html_sample_in`フォルダに，本記事と同じ様式にできるCSS(`original_ishibashi.css`)がある．  
おなじフォルダに，`sample1.md`というファイルがある[引用元](https://qiita.com/salchu/items/da81122ed50b35feda4d)．  
このHTMLが入っている`GuideForMarkdown`というディレクトリを，自分の環境にコピーしてきて，`html_sample_in`に入ってほしい．  
このフォルダの内部で以下のコマンドを実行する．

```sh
pandoc -S -s --self-contained -t html5 -f markdown -c ./original_ishibashi.css -o ../html_sample_out/sample1.html ./sample1.md
```

これにより，HTMLファイルが，`html_sample_out`フォルダ内に，`sample1.html`として生成されたはずである．  
開いてみて，おーーMarkdownからキレイにHTMLができたーー!という実感を持ってほしい．

あとは，コマンドをよく見て，オプションを勉強すれば，HTMLの作成はお手の物である．

<!-- }}} -->

## Pandocで論文を書きWordファイルにする <!-- {{{ -->

なにはともあれ，変換して，凄さを理解したほうがいい．  
下記コマンドを，`docx_sample_in`フォルダ内で実行してみてほしい．  
すると，`docx_sample_out`フォルダに，Wordファイルが生成されている．  
初めて使ったら，マジで感動すると思う．


```sh
> pandoc -f markdown -t docx -S --reference-docx ./reference.docx --bibliography ./citations.bib --csl ./apa.csl -o ../docx_sample_out/sample.docx ./1_title.md ./2_abstruct.md ./3_intro.md ./4_exp-proc.md ./5_result.md ./6_discussion.md ./7_figs-tables.md ./8_references.md
```

<details><summary>もともとのマークダウンファイルの中身は本当に文字だけしか入っていない</summary> <!-- {{{ -->

```
# E and ID proteins regulate cell chirality and left-right asymmetric development in *Drosophila*

Tomoki Ishibashi^1^, Ryo Hatori^1^, Reo Maeda^2^, Mitsutoshi Nakamura^1^, Tomohiro Taguchi^2^, Yoko Matsuyama^1^, and Kenji Matsuno^1\*^  
^1^ Department of Biological Sciences, Osaka University, 1-1 Machikaneyama-cho, Toyonaka, Osaka 560-0043, Japan; ^2^ Department of Biological Science and Technology, Tokyo University of Science, Noda, Chiba, Japan  
^\*^ Corresponding author. Tel.: +81-6-6850-5805; Fax: +81-6-6850-5805  
E-mail addresses: Kenji Matsuno: kmatsuno@bio.sci.osaka-u.ac.jp  
Short title: E and ID regulate left-right asymmetry  
Keywords: E protein, Id protein, Left-right asymmetry, Myosin ID, Cell chirality.

\clearpage

## Abstruct

How left-right (LR) asymmetry forms in the animal body is a fundamental problem in Developmental Biology.
While the mechanisms for LR asymmetry are well studied in some species, they are still poorly understood in invertebrates.
We previously showed that the intrinsic LR asymmetry of cells (designated as cell chirality) drives LR asymmetric development in the *Drosophila* embryonic hindgut, although the machinery of the cell chirality formation remains elusive.
Here, we found that the *Drosophila* homolog of the *Id* gene, *extra macrochaetae* (*emc*), is required for the normal LR asymmetric morphogenesis of this organ.
Id proteins, including Emc, are known to interact with and inhibit E-box-binding proteins (E proteins), such as *Drosophila* Daughterless (Da).
We found that the suppression of da by wild-type *emc* was essential for cell chirality formation and for normal LR asymmetric development of the embryonic hindgut.
*MyosinID* (*MyoID*), which encodes the *Drosophila* Myosin ID protein, is known to regulate cell chirality.
We further showed that Emc-Da regulates cell chirality formation, in which Emc functions upstream of or parallel to MyoID.
Abnormal Id-E protein regulation is involved in various human diseases.
Our results suggest that defects in cell shape may contribute to the pathogenesis of such diseases.

## Introduction

### Left-right asymmetry in animals

Many animals show the directional LR asymmetry in their body structures and functions. Mechanisms of LR asymmetric development have been the one of central question in Developmental Biology [@Levin2005].
The molecular mechanisms of the LR asymmetric development have been well studied, although mostly in vertebrates [@Blum2018; @Kimelman2012; @Riechmann2001].
For example, in some vertebrates, the LR symmetry is first broken by an LR directional flow of extra-embryonic fluid, which is induced by ciliary rotation in the node or its equivalent tissue in early embryos [@Yoshiba2014].
In contrast, in invertebrates the mechanisms of LR-asymmetry formation remain unclear, although a few excellent studies have unveiled basic concepts behind the directional LR asymmetry formation in nematodes, snails, and *Drosophila* [@Blum2018; @Kuroda2009;@Okumura2008; @Speder2007].
Some invertebrate species develop LR asymmetric body structures using mechanisms arising from the intrinsic chirality of blastomeres or cells in tissues, which is distinct from the mechanism used in vertebrates, indicating that the processes for directional LR symmetric development diverged in evolution [@Blum2018; @Inaki2018; @Okumura2008].

Several organs in *Drosophila* also show a directional LR asymmetric morphology [@Hayashi2001; @Hozumi2006; @Ligoxygakis2001; @Pascual2004; @Speder2006].
Among these organs, the embryonic gut is the first to exhibit an LR asymmetric shape during development [@Campos-Ortega2015; @Hayashi2001; @Ligoxygakis2001].
The embryonic hindgut shows the simple morphology exhibiting the stereotypic LR asymmetry, in which a monolayer epithelial tube bends like a hook at its most anterior part (Fig. 1A).
At an early stage of embryonic development (stage 12), the hindgut is LR symmetric and bends toward the ventral side of the embryo (Fig. 1A).
At the next stage of development (stage 12-13), the hindgut rotates anticlockwise 90°, which causes the hindgut to curve rightward and to be LR asymmetric (Fig. 1A) [@Hayashi2001; @Hozumi2006].
Neither cell division nor apoptosis is involved in this rotation [@Campos-Ortega2015].
Moreover, the embryonic hindgut epithelial tube, but not the surrounding visceral muscles, is sufficient for this rotation [@Hozumi2006; @Nakamura2013].
Thus, LR asymmetric cell deformation of the hindgut epithelial cells themselves may contribute to the hindgut rotation.

### Cell chirality

In agreement with this idea, we previously reported that the epithelial cells of the embryonic hindgut exhibit an LR-asymmetric shape in their apical surface before hindgut rotation [@Hatori2014; @Inaki2016; @Inaki2018a; @Inaki2018; @Taniguchi2011].
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Experimental Procedures

### *Drosophila* strains and genetic crosses

*Canton-S* was used as the wild-type (WT) strain.
The following mutants were used: *emc^tink^*, a null allele induced by ethyl methanesulfonate in this study;
*emc^AP6^*, an amorphic allele [Bloomington #36544; @Ellis1994];
*emc^2^*, a hypomorphic allele [Kyoto DGRC #101588; @Ellis1990].

Mutations on the first and second chromosome were balanced with *FM7c, P{ftz/lacC}YH1* and *CyO, P{en1}wg^en11^*, respectively.
Mutations on the third chromosome were balanced with _TM3, P{ftz-lacZ.ry^+^}TM3, Sb^1^ ry^\*^_, *TM6B, P{iab-2(1.7)lacZ}6B, Tb^1^*, or *TM3, P{GAL4-twi.G}2.3, P{UAS-2xEGFP}AH2.3, Sb^1^ Ser^1^*.
All genetic crosses were performed at 25 °C on a standard *Drosophila* culture medium.

### Staining of embryos

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Results

### *emc* is required for LR-asymmetric development of the embryonic hindgut

Sample equation $E = mc^2$.
You can write block-style equation.
$$f(\theta) = e^{-i\theta} = \cos \theta + i \cdot \sin \theta$$

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Result 2

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Discussion

### Discussion 1

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Discussion 2

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Figures and Tables

### Figure 1

![](./img/fig1.jpg)  
**Fig. 1.** ***emc*** **mutant embryos show defects in LR asymmetric development of the embryonic hindgut.**  
(A)
Schematic showing the LR asymmetric development of the *Drosophila* embryonic hindgut as viewed from the dorsal side.
The hindgut has an LR symmetric shape bending dorsally (left) at stage 12, and then undergoes a counterclockwise (broken arrow) rotation from late stage 12, consequently bending to the right at stage 13 (right).
(B-C)
The hindgut (orange) of wild-type embryos at stage 12 (B) and stage 13 (C).
(D-I)
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Figure 2

![](./img/fig2.jpg)  
**Fig. 2. Figure Title.**  
(A)
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
(B)
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Table S1

| *emc* expression in the hindgut | stage 11   | stage 12   | stage 14   |
| ------------------------------: | :--------- | :--------- | :--------- |
| +                               | 11         | 4          | 0          |
| +/-                             | 1          | 13         | 7          |
| -                               | 0          | 0          | 14         |
| **TOTAL**                       | **12**     | **17**     | **21**     |

**Table S1**
The expression of *emc* was detected by *in situ* hybridization using an antisense probe for *emc* (see Figure 2).
The numbers of embryos showing *emc* signals in the hindgut primordium and hindgut are shown.
+, strong signal;
+/-, weak signal;
-, no signal.

## References
```

---
</details>
<!-- }}} -->

<!-- }}} -->

## 一旦，PDFも作ってみる <!-- {{{ -->

PDFの方は，ちょっと調教が足りないので，あまり良い見た目に調整できていない．  
でもひとまず，下記コマンドを使うと，`docx_sample_out`フォルダに，PDFファイルが生成される．  
ここでのコツは，最初にメタデータにタイトルや著者情報を記載し，`1_title.md`や`2_abstruct.md`を読み込ませずに`0_metadata`を読み込ませるところにある．  
これにより，LaTeXぽい美しいPDFができる．  
なんかTableの見た目が間違っているのだが，これはどうすればいいのか．

```sh
pandoc -f markdown -t latex -V geometry:margin=3cm -V geometry:a4paper --toc -S --bibliography ./citations.bib --csl ./apa.csl -o ../docx_sample_out/sample.pdf ./0_metadata ./3_intro.md ./4_exp-proc.md ./5_result.md ./6_discussion.md ./7_figs-tables.md ./8_references.md
```

<!-- }}} -->

## `.bib`ファイルの作成 <!-- {{{ -->

Referenceの自動作成は，本当に素晴らしい機能である．  
これは，`--bibliograpy`オプションで設定する`.bib`ファイルによって，自動生成される．  
ここでは，`.bib`ファイルの作成方法を説明する．

[Mendeley](https://www.mendeley.com/)というソフトをダウンロードする．  
これは，論文管理ソフトで論文情報を収集してくれる．  
適当に，論文をMendeleyに放り込んでいこう．  
使い方は[調べよう](https://www.google.co.jp/search?q=mendeley%20%E4%BD%BF%E3%81%84%E6%96%B9)．  
それだけでは，号数などの情報が不足しているので，放り込んだ論文を全選択して，右クリック→`Update Details`をクリックする．  
これによって，doiなどを含めた，沢山の情報がゲットできる．  
このとき，自動収集された情報が間違っていることがある．  
松野研だと，Hatori 2014の論文にエラーが生じる．  
そこらへんは，自分でチェックしておこう．  
あと，メニューから，`Preference` → `Document Details`を選び，`Document Type`の`Journal Article`の`Citation Key`にチェックをいれておこう．  
最後に，論文を全選択して，右クリック→`Export`をクリックし，BibTex(`bib`)フォーマットで好きな場所に保存する．

これで，引用に必要な`.bib`ファイルは手に入った．

<!-- }}} -->

## `.csl`ファイルの準備 <!-- {{{ -->

CSLファイルは，論文ごとの引用様式が書かれたファイルである．  
たとえば，NatureとCellの論文の引用の仕方が違うが，これは，CSLファイルで自動生成可能である．  
`.bib`ファイルを使って引用の自動生成を行うためには，CSLも必要である．  
幸いなことに，CSLは，ダウンロード可能である．

[MendeleyのCSL編集サイト](https://csl.mendeley.com/about/)に行き，好きなCSLを探す．  
検索窓に，NatureやCellなど，投稿したい雑誌名を入れてもいいし，投稿したい雑誌に規定があれば，規定に合うCSLをさがす(たとえばAPAなど)．  
ほしいCSLがみつかったら，`View style`をクリックする．  
移動したページの末尾に，`CSL code`というテキストがあるので，それを全コピーして，好きな場所に`apa.csl`など適当な名前で保存する．

これで`.csl`ファイルも手に入った．  
これだけあれば，引用の自動生成ができてしまう!!!

<!-- }}} -->

## リファレンス`docx`の作成 <!-- {{{ -->

引用の自動生成が出来るとなると，もうかなり良いのだが，ボスに渡すにあたって，少しだけ見た目をキレイにしておこう．  
pandocでは，生成されるWordファイルの見た目を，だいたい決めておくことができる．  
見た目をまたコードで命令すると面倒なのだが，素晴らしいことに，pandocはWordファイルのまま，見た目を決められる．  
今回は，自分が常用しているスタイルをまとめた`reference.docx`を使った．  
詳しくは，[Pandoc User's Guide](http://sky-y.github.io/site-pandoc-jp/users-guide/)の`--reference-docx`の項を読もう．

ここまで，ざっくりとMarkdownを使って論文を書き，人に渡す状態に持っていく方法論をしょ迂回してきた．  
基本的には習うより慣れろなので，自分で使いこなすのが一番だとおもう．  
慣れてくると，[ここ](https://www.clear-code.com/blog/2018/9/13.html)にかかれているような方法で，[template](https://github.com/jgm/pandoc/wiki/User-contributed-templates)をダウンロードして使ったりもできる．

<!-- }}} -->

## それ以外のtips <!-- {{{ -->

- Markdownは，HTML記法も使えるので，コメントの挿入ができる．
    - `<!-- コメント．読み込まれない． -->`という文法で書いたコメントは，`.md`上では読めるが，WordやPDFには変換されない．
    - 自分のためのメモなどに便利
    - たとえば，`<!-- ここにxxの論文を引用しつつ書き足す -->`とかのコメントを入れる．
- IntroductionやResultをファイルを分割して書いた方が管理がしやすい．
    - もちろんまとめて書いても問題はない
    - Gitを使って管理するなら，分割されてるほうが良い
    - 雑誌によっては，マテメソの位置が変わるので，分割しているほうが，順番の入れ替えが簡単
- 図は別フォルダに別途用意するほうがよい
    - Wordだと，ファイルに図が埋め込まれるので，容量が大きくなってしまう
    - Markdown上では図は参照する形でしか書かないので，容量は小さいママ
    - 本文だけ書き換えても，参照する図は同じなので，容量も小さく，見た目も揃う
    - 図の変更や順番の入れかえも簡単になる
- vimだと，[citation.vim](https://github.com/rafaqz/citation.vim)を使えば，citation keyの挿入が簡単になる

<!-- }}} -->

<!-- vim: set foldmethod=marker : -->
