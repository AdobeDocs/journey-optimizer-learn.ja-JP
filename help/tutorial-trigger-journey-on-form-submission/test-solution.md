---
title: 解決策をテスト
description: フォーム送信時にメールを送信するジャーニーを作成
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00Z
jira: KT-20014
exl-id: 9b4a3e0c-d153-4a6b-a7de-b926bd669f6a
source-git-commit: d4cc60f4448caec92f704026783e2bbe029427f5
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# 解決策をテスト


解決策をテスト
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## サンプルアセットのデプロイ

Node.jsがインストールされていない場合は、ここからダウンロードして[ インストールします](https://nodejs.org/)

次のコマンドを実行してインストールを確認します。

`node -v`

`npm -v`

## プロジェクトフォルダーの設定

次のコマンドを使用して、サンプルアプリ用の新しいディレクトリを作成します。

`mkdir trigger-journey `

`cd trigger-journey`

## プロジェクトの初期化

`npm init -y`

## 必要なフレームワークのインストール

`npm install express dotenv axios cors`

## アセットファイルをコピー

* [project-root.zip](assets/project-root.zip)の内容を`trigger-journey` フォルダーに解凍して配置します。

* `trigger-journey` フォルダーに`public`という名前のフォルダーを作成します
* `.env` ファイルを適切な値で更新します。 これらの値は、HTTP Source接続の作成時にダウンロードされたcURL コマンドから使用できます。
* [index.zip](assets/index.zip)の内容を`public` フォルダーに解凍します

## サーバーの実行

`trigger-journey` ディレクトリにいることを確認してください。
コマンドを実行する `node server.js`
ブラウザーを[web ページに誘導します](http://localhost:3000/)
フォームに入力して送信します。 ジャーニーがトリガーされ、フォームに入力したメール IDにメールが送信されます。
