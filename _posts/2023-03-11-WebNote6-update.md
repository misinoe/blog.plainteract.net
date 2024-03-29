---
layout: post
title: WebNote6アップデート 2023年3月11日
tags:
- WebNote
---

本日WebNote6に追加のアップデートを行いました。

https://webnote.plainteract.net/

変更点は次の通りです。

## 不具合の修正

* 左のドロワーが重なって表示される意図しない挙動を修正しました。
* `CTRL + Space` 等のショートカットキーを入力すると、外観設定が初期化される不具合を修正しました。


## ユーザー一覧とテキストチャット

* アプリケーションツールバーから、ユーザー一覧とテキストチャットが開く事ができるようになりました。
* 右ドロワーの背景色を半透明 `0.85` に設定しました。
* チャットを通じて、システムメッセージの表示が行われる場合があります。

## アイコンの変更

残り時間と同時接続者数のアイコンを、`@mui/icon-material` の物に変更しました。

## アカウントボタン

* メニューがアプリケーションツールバーより前面に表示されるように変更しました。
* メニューから、ログインしているユーザーIDとLevelの確認ができるようになりました。

## テキストチャット

* テキストチャットがログに記録されるようになりました。
* テキストチャットの未読数が表示されるようになりました。

## ハッシュ化アルゴリズムの変更

* `ipHash` の計算アルゴリズムをより強化されました。
* これにより以前と表示されるIDが変更されます。

## 法務対応

* 法務対応のため、全てのストロークデータとチャットのデータに対して、発信者を特定する事が可能な識別子とUnixtimeが記録されるようになりました。
* ログの保持期間が延長されました
  - アクセスログ: 約1週間 -> 約4週間
  - ゲームのログ: 約2週間 -> 約4週間
