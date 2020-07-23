---
layout: post
title: WebNoteからWN2:LineArtに色を引き継ぐ
tags:
- WebNote
- WN2:LineArt
---

## 1. WebNoteのゲーム画面を開く

[https://webnote.plainteract.net/room/2](https://webnote.plainteract.net/room/2)


## 2. アドレスバーで次のスクリプトを実行

```js
javascript:(()=>{let o=JSON,t=[];for(let l=0;l<12;l++){let r=0|o.parse(localStorage["tool-"+l]).value.color;t.push("#"+r.toString(16).padStart(6,"0"))}prompt("Please copy",o.stringify(t))})();
```

* ブラウザのセキュリティ設計により、アドレスバーにコピー＆ペーストすると先頭の「javascript:」の部分が削除されたりします。手動で入力してください。

上手く行くと「please copy」というプロンプトが表示されます。

カラーコード一覧をメモ帳等にコピペし控えて下さい。


## 3. WN2:LineArtのゲーム画面を開く

[https://lineart.plainteract.net/canvas/room2](https://lineart.plainteract.net/canvas/room2)


## 4. アドレスバーで次のスクリプトを実行

```js
javascript:(()=>{let e=JSON,r=e.parse,t=localStorage,l="tool-preset-v9",o=r(prompt("Please paste here")),a=r(t[l]);for(let e=0;e<6;e++){let r=a.presets[e],t=parseInt(o[e].slice(1),16);r.color=t,r.rgba={b:255&t,g:t>>8&255,r:t>>16&255,a:1}}t[l]=e.stringify(a),alert("Done!"),location.reload()})();
```

上手く行くと次は「Please paste here」のプロンプトが表示されます。先程控えたカラーコード一覧をここに貼り付けて実行して下さい。

## 5. おわり

全行程が上手く行くと、「Done!」と表示されページがリロードされます。

色が移植されているはずです。
