---
layout: post
title: WN2:LineArtを構成する技術 ③コンテナ・TypeScript・CI/CD
tags:
- WN2:LineArt
---

[前の記事](./2020-08-23-wn2la-architecutre-2.md)

## コンテナ構成

![](../images/20200822/wn2la-architecture-container.png)

nginxを公開し、パスに応じてコンテナ間通信においてWebアプリケーションサーバーとWebSocketサーバーにリバースプロキシされます。

## TypeScriptの構成

共通のinterfaceやclassはcommon/で開発され、WebアプリケーションとWebSocketサーバーのコンテナにストレージとしてマウントされ、モジュールとしてそれぞれに持ち込まれています。

![](../images/20200822/wn2la-architecutre-typescript.png)

## CI/CDの構成

![](../images/20200822/wn2la-architecture-cicd.png)

CI/CDはGitHub Actionsを利用しています。
developブランチにmergeされるとステージングに、masterブランチにmergeされると本番サーバーに自動デプロイされます。


続く