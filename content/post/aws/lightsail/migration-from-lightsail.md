---
title: 'Light Sailからの移行'
date: 2019-04-16T04:52:33+09:00
draft: false
archives: '2019'
author: matsu4ki
tags: ['AWS', 'Hugo']
---

## 移行しました

AWS の 「Light Sail + WordPress」 でブログを立ててましたが、WordPress がだるすぎたので AWS の ~~[AWS Amplify + Hugo]に移行しました。~~

<div class="notification">
※現在は「GitHub Pages + Hugo」の構成です
</div>

GitHub Pages とかをそのまま使うのも良かったけど、AWS のサービスを触ってみたかったのでこっちで立ててみました。

Hugo に移って最初に記事書いていて思うけど、やっぱ**Markdown**が最強なんだわ。<br>
スラスラ書ける 😎

一応 WordPress でも Markdown で書けるプラグイン 📕 は少し出てたけど、

「めっちゃこれいいやん」

みたいなプラグインは見当たりませんでした 😥

## Hugo で辛かったこと

- `AWS Amplify`を利用する場合は、git の submodule を使ってはいけない
- `draft`は下書き機能で、`false`にしないと記事が表示されないこと。<br>(これを忘れててずっと表示されないぞおおおお！ってなってました。あほや)
- テーマが崩れるときがある

## 追記

結局上記のいろいろな問題で萎えて、止まってました。現在は GitHub-pages に移して動かしてます。草も生えるし無料だし特に重要じゃない homepage だったらこっちでいいね。
`AWS Amplify`触ってたのは勉強もかねてだったので、それはそれでよかったです。
`AWS AMplify`はまた別の機会に使いたいです 🥴
