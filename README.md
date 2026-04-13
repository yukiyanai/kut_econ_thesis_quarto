# kut_econ_thesis_quarto

これは、高知工科大学経済・マネジメント学群に提出する卒業論文を[Quarto](https://quarto.org/)を使って書くためのテンプレートです。正しく使うと[このファイル](kut_econ_thesis_Qsample.pdf)のようなフォーマットの文書ができます。自由に利用してください。

- 公開：2026-04-08


以下の5つのファイルを配布します。

- `.qmd`ファイルのテンプレート：[kut_econ_thesis.qmd](kut_econ_thesis.qmd) 
- フォーマットを規定するtex ファイル：[kut_econ_template2.tex](kut_econ_template2.tex)
- bibファイルのサンプル：[myrefs.bib](myrefs.bib)
- latexmk の設定ファイル：[latexmkrc](latexmkrc) 
- 正しくrenderするとできるPDFのサンプル：[kut_econ_thesis_Qsample.pdf](kut_econ_thesis_Qsample.pdf)

詳しい使い方はテンプレート ([kut_econ_thesis.qmd](kut_econ_thesis.qmd) ) に書いてあるので、よく読んで使ってください。

## 準備

### IPAexフォントをインストールする

- 既にインストールされているならこの作業は不要
- インストール方法はテンプレートファイルに書いてある


###  Rで必要なパッケージをインストールする

以下のパッケージが必要なので、（インストールしていない場合は）インストールする。

- knitr
- pacman
- rmarkdown
- base64enc
- digest
- htmltools
- jquerylib
- jsonlite
- markdown
- mime
- rmarkdown
- tinytex
- bookdown
- texreg

これらのパッケージをすべて一挙にインストールしたい場合は、以下のコードを実行する。

```
packs <- c("knitr",
           "pacman", 
           "rmarkdown",
           "base64enc",
           "digest",
           "htmltools",
           "jquerylib",
           "jsonlite",
           "markdown",
           "mime",
           "rmarkdown",
           "tinytex",
           "bookdown",
           "texreg")
install.packages(packs, dependencies = TRUE)
```

卒論テンプレートをrenderするために必要な上記以外のパッケージは、テンプレートを初めてrenderするときに自動的にインストールされる（インターネット接続が必要）。



### LaTeX一式をインストールする


- TeX Live（Linux または Windows）または MacTeX（macOS）をインストールする
  - インストール方法については [TeX Wiki](https://texwiki.texjp.org/?TeX%E5%85%A5%E6%89%8B%E6%B3%95) を参照。

- <s>LaTeX 自体を使う予定がないなら、**tinytex** でもよい。ただし、</s>**既にLaTeXが入っているパソコンに追加でtinytex を入れてはいけない**！
  - tinytex だとうまくいかないことがあるので、TeX Live (MacTeX) を使う。
  - tinytex でインストールした LaTeX がある場合は、以下のコマンドをRの Console で実行してアンインストールする。

```
tinytex::uninstall_tinytex()
```

###  卒論用の R Project を作る

RStudio からいつもどおりプロジェクトを作る。既存のプロジェクトを使ってもかまわない。


### プロジェクトフォルダの中に必要なファイル作る・保存する

1. 卒論本体のQuarto文書（`.qmd`ファイル）を作る
  - テンプレート（`kut_econ_thesis.qmd`）に従って書く
  - ファイル名は自由に付けてよい
  - 本文、分析用コード、図表を作るコードをすべてこのファイルに書く
2. `kut_econ_template2.tex` を1のRmdファイルと同じフォルダ（同じ階層）に保存する
3. `latexmkrc`（拡張子なし）を1のRmdファイルと同じフォルダ（同じ階層）に保存する。自作の`latexmkrc`または`.latexmkrc`を使いたい場合は、このステップを飛ばす（つまり、このファイルを使わない）。
4. `myrefs.bib` を作り、1のRmdファイルと同じフォルダ（同じ階層）に保存する
  - 必ずこのファイル名にする（ファイル名を変える場合は tex テンプレートの修正が必要）
  - ファイル自体はここで配布するものではなく、ZoteroやJabRefなどを使って自分で作る
5. `jecon.bst` を1のRmdファイルと同じフォルダ（同じ階層）に保存する
  - 武田史郎さんが作った文献スタイルファイル
  - [ココ](https://github.com/ShiroTakeda/jecon-bst/) から入手する
    - **誤って HTML ファイルを保存しないように注意**

---

あとは研究して執筆するのみ。

**Enjoy & good luck!**
