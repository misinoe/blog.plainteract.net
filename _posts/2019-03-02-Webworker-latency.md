---
layout: post
title: WebWorkerとのpostMessageの遅延はどれくらいか
tags:
- WebWorker
---

WebWorkerとのpostMessageに掛る時間をシンプルに計測する物を作りました。

[https://misinoe.github.io/WebworkerPostmessageTest/](https://misinoe.github.io/WebworkerPostmessageTest/)

開発時間は15分程度。


## 目的

[OffscreenCanvas](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas) を使用するため、 [WebWorker](https://developer.mozilla.org/ja/docs/Web/API/Web_Workers_API) の特性を理解するためのパフォーマンス測定です。

OffscreenCanvas は描画に関わる処理を WebWorker に行わせる事でメインスレッドの負担を減らし、Webサイトのパフォーマンスを向上させる事ができます。

とはいえ、 WebWorkerとのデータのやり取りに主だって使う [Worker.postMessage()](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage) はどれくらいの時間がかかるでしょうか？

もし、 16.67ms より時間がかかる場合、60Hzのディスプレイでは1フレーム以上の遅延が発生するだろうと推測する事ができます。

更に 100ms や、それ以上かかってしまうならば、もはやユーザーのタッチやクリックに反応するグラフィックの描画をWebWorkerに任せる事ができないと言えるでしょう。

それらを明らかにするため測定をします。

[https://misinoe.github.io/WebworkerPostmessageTest/](https://misinoe.github.io/WebworkerPostmessageTest/)


## 結果

* 往復 1ms 以下
  * 大体 0.2 ~ 0.3 ms 程度
* データの量によって多少遅くなる
* また、割り込み処理じゃないので`onmessage`の受け取り側の状況によって多少遅延する
