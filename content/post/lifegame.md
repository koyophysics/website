---
title: Processingでライフゲーム
slug: lifegame
date: '2018-06-27'
tags:
    - "ライフゲーム"
    - "Processing"
categories:
    - "作ってみた"
image: "/img/lifegame/1.png"
description: "ライフゲームってご存知ですか？まるで生きているかのような振る舞いをする、とても興味深いプログラムです。"
author: H崎
draft: false
comments: true
---

## きっかけ
いつものように、物理部で数学の勉強してたのですが(ｵｲ)、そこにいた準部員の一人が「ライフゲームって知ってる？」と発言したことが発端です。  
僕自身、全く知らなかったので、即興でProcessingでコードを書くことに。  
残念ながら謎のバグのせいで、その日の物理部では完成しませんでしたが、家に帰って完成させたので紹介します。

## ライフゲームとは？

<div class="movie-wrap">
  <iframe width="854" height="480" src="https://www.youtube.com/embed/ZOkm867AleM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

ルールはいたって簡単。  

> 誕生  
> 死んでいるセルに隣接する生きたセルがちょうど3つあれば、次の世代が誕生する。  
> 生存  
> 生きているセルに隣接する生きたセルが2つか3つならば、次の世代でも生存する。  
> 過疎  
> 生きているセルに隣接する生きたセルが1つ以下ならば、過疎により死滅する。  
> 過密  
> 生きているセルに隣接する生きたセルが4つ以上ならば、過密により死滅する。  
> (Wikipedia引用)

これだけです。
一つずつのセルに対して、８近傍の状態を調べて次の世代を決定するというプログラムを組めば良いわけです。

## ソースコード
<script src="https://gist.github.com/hamataku/76b7a566c9f2287ef79b731d0d618970.js"></script>

注意としては、ControlP5というライブラリを使用しているので、
スケッチ＞ライブラリをインポート＞ライブラリを追加
から、インストールしてください。

ライフゲーム単体だけであれば、もっと短くて済みますが、他の機能として、

- 消去、書き込み機能
- スピード変更機能
- グライダー銃をプリセット

を追加。ちょっと長くなってしまいました。（頑張ればもうちょっと短くなると思いますが）

このプログラムは全てのマスに対して８近傍の数を調べる総当たり方式ですが、他にもビットボードと呼ばれるビット演算で次の世代を決定するという方式もあるようなので、余裕があれば挑戦してみたいと思います。