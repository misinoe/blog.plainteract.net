---
layout: post
title: WebNote6アップデート 2023年2月26日
tags:
- WebNote
---

本日WebNote6にアップデートを行いました。

https://webnote.plainteract.net/

過去ログの表示に互換性があります。

変更点は次の通りです。


## Levelについて

全てのユーザーの `Level` 情報を開示するようになりました。
この値は、そのユーザーがどの程度システムやコミュニティに安全であるか、目安となる数値です。
`Level` の値に応じて使用できる機能が解除されます。

### Levelの表示場所

* 各種ツールを使用した時に表示されるIDの接頭詞に省略表示されます。Level1の人の例: `1.abcdef123456` 
* 部屋の右ドロワー内、利用者一覧に `Level` が表示されます。
* ログイン後、アカウント画面にて自分の `Level` の基本値を確認することができます。

### Levelによる機能の開放

WebNote6では各ツールを使用するために、必要なLevelの調整が行われています。

#### 従来の解除方法

* ペン: 誰でも使用可能
* ブラシ: 誰でも使用可能
* エアブラシ: ログインが必要
* サーフェース: ログインが必要
* テキスト: ログインが必要
* イメージ: ログインが必要

#### 今後の解除方法

* ペン: 誰でも使用可能
* ブラシ: 誰でも使用可能
* エアブラシ: Level2以上が必要
* サーフェース: Level3以上が必要
* テキスト: Level2以上が必要
* イメージ: Level3以上が必要

また同時接続数の多い部屋では、書き込み可能エリアが `Level` によって変動するよう調整される場合があります。

### Levelの昇降格

* 非ログインユーザーは基本値がLevel0として取り扱われます。
* ログインするとそのアカウントにLevel1の基本値が付与されます。
* システムやコミュニティにおける安全性が確認されると、上位レベルに昇格されることがあります。
* 素行が悪かったり、危険性が確認されると、下位レベルに降格されるか、Level0が設定される場合があります。

Levelの昇降格は機械が自動的に、又は運営者が手動で変更を行う場合があります。

#### 昇降格の基準

`Level` はそのユーザーがシステムやコミュニティに安全であるかの目安となる数値です。
明確な基準はありませんが、以下の要素を考慮し安全性を評価、 `Level` の昇降格操作が行われます。

* 利用規約に違反していないか
* システムを適切な目的で利用しているか
  - 絵を描いているか
  - 適切なコミュニケーションを行っているか
* 利用期間
* バックグラウンド
* アクティビティ
* 可視性


## 機能追加

* テンキーに対応しました。
  - Num[1]~[9]により、ツールを切り替えれるようになりました。
* 複数タブを開いている時、ツールの設定値がシームレスに連携されるようになりました。

## 仕様変更

* カンバスに表示されるIDの仕様が変更されました。
  - フォントサイズを調整、デザインを変更し視認性を向上しました。
  - IDの接頭辞に省略した `Level` の値が表示されます。Level1の人の例: `1.abcdef123456`
* 右ドロワー、接続ユーザー一覧に、ユーザーの `Level` が表示されるようになりました。
