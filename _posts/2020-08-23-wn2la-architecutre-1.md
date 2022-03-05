---
layout: post
title: WebNote2:LineArtを構成する技術 ①全体編
tags:
- WebNote2:LineArt
---

WebNote2:LineArtがどのような技術で構築されているかについてご紹介します。

## 技術スタック

### サーバー/インフラ
* VPS
* Docker

### XaaS
* AWS S3
* Firebase Authentication
* reCAPTHCA v3

### DB/KVS
* MongoDB
* Redis

### フロントエンド/バックエンド
* Next.js
* TypeScript
* React
* material-ui

### クライアントサイド
* TypeScript
* socket.io-client
* three.js

### サーバーサイド
* TypeScript + Node.js
* ts-node-dev + ts-node
* socket.io

### CI/CD
* GitHub Actions


## この構成について

羅列した技術スタックだけを見ると、何かすごい事してるなという関心又は何故こんな事をしているんだという疑問が浮かぶかもしれません。
それについては、ソフトウェアエンジニアが1人趣味で運用しているという背景を考察すると納得できると思います。

* ランニングコストの最小化
  - コスト増は自分お小遣い減
  - スケールアウトはしない(させない)
* 運用人的コストを最小化する
  - 修正やアップデートを楽にこなせるようにする
  - 自動化しておく
* チャレンジ
  - 仕事ではできないナレッジの拡大と追求の舞台にする
  - ユーザーの居る環境でプロダクション品質を磨く
  - 開発を楽しむ！


これらに加えて、前代・前々代のサービスの成功した点、または失敗した事項を踏襲し現行の構成に反映されています。

[続く](/wn2la-architecture-2)
