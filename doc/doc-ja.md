# 想定している使い方

SATySFiのテキストモードでHTMLを出力するときに使用してください。

言語はhtmlを指定してください。

例えばこのように感じです。


```
satysfi <input>.saty --text-mode "html" -o <output>.html
```


# このリポジトリにあるパッケージ

- stdjahtml.satyh-html
- code.satyh-html
- itemize.satyh-html
- url.satyh-html

# 提供コマンド

## stdjahtml.satyh-html

module StdJaHTML

- `direct \ref : [string] inline-cmd` : ラベルの参照をします。
- `direct \figure : [string?; inline-text; block-text] inline-cmd` : 画像を貼れます。
- `direct +section : [string?; inline-text; block-text] block-cmd` : 節です。
- `direct +subsection : [string?; inline-text; block-text] block-cmd` : 小節です。
- `direct +p : [inline-text] block-cmd` : 段落です。
- `direct +pn : [inline-text] block-cmd` : 段落です。
- `direct \emph : [inline-text] inline-cmd` : 強調できます。

## code.satyh-html

module Code

- `direct +code : [string] block-cmd` : ブロックでのコードです。`class`は`code-display`です。
- `direct +console : [string] block-cmd` : ブロックでのコンソールです。`class`は`console-display`です。
- `direct \code : [string] inline-cmd` : インラインでのコードです。`class`は`code-inline`です。
- `direct \console : [string] inline-cmd` : インラインでのコンソールです。`class`は`console-inline`です。
- `direct \d-code : [string] inline-cmd` : ブロックでのコードをインラインで書けます。`class`は`code-display`です。

## itemize.satyh-html

module Itemize

- `val listing : text-info -> itemize -> string` : 箇条書きのhtmlコードを返します。
- `direct +listing : [itemize] block-cmd` : ブロックの箇条書きです。
- `direct \listing : [itemize] inline-cmd` : インラインの箇条書きです。
- `val enumerate : text-info -> itemize -> string` : 数字付き箇条書きのhtmlコードを返します。
- `direct +enumerate : [itemize] block-cmd` : ブロックの数字付き箇条書きです。
- `direct \enumerate : [itemize] inline-cmd`: インラインの数字付き箇条書きです。

## url.satyh-html

module Url 

- `direct \href : [string; inline-text] inline-cmd` : ハイパーリンクです。
- `direct \url : [string] inline-cmd` : URLを表示したいときに
