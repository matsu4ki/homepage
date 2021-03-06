---
title: 'Windows10のVSCodeでvscode Revealが正しく動かなかった問題の解決法'
date: 2019-07-18T05:18:30+09:00
tags: [VSCode, revealjs, extention, markdown]
draft: false
archives: '2019'
author: Amatsuki
---

## TL;DR

### 方法 1

改行コードを`LF`に変える

### 方法 2

拡張機能で`LF`で書かれている部分を`CRLF`で書き直す

## 原因

TL;DR でだいたい判ると思いますが、vscode-reveal のスライド仕切りの`---`がデフォでは`LF`の設定で登録されているのが問題でした。

- [revealjs の改行コード指摘ページ](https://github.com/hakimel/reveal.js/#external-markdown)
- [日本語訳版](https://qiita.com/takayu90/items/0af9bd125e6704803c0d)

## 解決法

普通に使う場合は前者の方を実施したほうがいいと思います。
後者のやり方だと設定ファイルに書かない限り、正しく表示させる作業が毎日必要になります。

### revealjs に読み込ませる改行コードを変える場合

1. 拡張機能の設定画面を開く(`Ctrl + ,`)
2. reveal JS の項目を探し、**Revealjs: Separator**の内容にある`\n`を`\r?\n`に修正する

![変更する場所](/resources/fixed-revealjs-vscode-extention-on-windows10/vscode-reveal-new-line.png)

### VSCode の改行コードを変更する場合

1. VSCode の footer 右にある改行コード`CRLF`をクリック
2. `LF`に変更する

![変更する場所](/resources/fixed-revealjs-vscode-extention-on-windows10/vscode-footer-new-line.png)
