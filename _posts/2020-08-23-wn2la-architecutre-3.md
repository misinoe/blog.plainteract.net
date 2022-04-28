---
layout: post
title: WebNote2:LineArtを構成する技術 ③コンテナ・TypeScript・CI/CD
tags:
- WebNote
---

[前の記事](/wn2la-architecutre-2)

## コンテナ構成

![](../images/2020-08-22/wn2la-architecture-container.png)

nginxを公開し、パスに応じてコンテナ間通信においてWebアプリケーションサーバーとWebSocketサーバーにリバースプロキシされます。

## TypeScriptの構成

共通のinterfaceやclassはcommon/で開発され、WebアプリケーションとWebSocketサーバーのコンテナにストレージとしてマウントされ、モジュールとしてそれぞれに持ち込まれています。

![](../images/2020-08-22/wn2la-architecutre-typescript.png)

## CI/CDの構成

![](../images/2020-08-22/wn2la-architecture-cicd.png)

CI/CDはGitHub Actionsを利用しています。
developブランチにmergeされるとステージングに、masterブランチにmergeされると本番サーバーに自動デプロイされます。

