TeXでスライドを書きたいというのは良くあることです。
宗教上の理由だとか、お気に入りのエディタで書きたいとか。
ともきさんは動きのないシンプルなプレゼンが好きだったり、Emacsで書きたかったりするのでそうしています。

まず、この記事はUbuntu 14.04を前提にお話することにします。
Linuxを初めて入れるという方には、Xubuntu 14.04をオススメします。
他のLinuxでもあまり変わらないはずですが、バージョンが古いと動かないかもしれません。

# インストール
まず、以下のパッケージをインストールしておきます。

- texlive-base
- texlive-science
- texlive-xetex
- texlive-latex-extra
- texlive-fonts-recommended
- latex-beamer
- latexmk
- fonts-vlgothic
- imagemagick

```
sudo apt-get install texlive-base texlive-science texlive-xetex \
                     latex-beamer latexmk texlive-latex-extra fonts-vlgothic \
                     texlive-fonts-recommended imagemagick
```

# サンプル

ファイル構成は以下のようにします。

```
.
├── img
│   └── python.png
├── library.bib
├── main.py
├── Makefile
└── slide.tex
```

# 画像の変換
まず、TeXに画像を貼るにあたって画像をpdfに変換します。
具体的には以下のコマンドを使用します。

```
convert img/python.png img/python.pdf
```

mogrifyを使うと一気に変換できるかもしれないです。

あとは、Sampleをながめてください。
latemk -pvcという機能があって、継続ビルド(ファイルの変更を監視)できるので便利です。
僕のMakefileでは make pvcとやると起動できます。


