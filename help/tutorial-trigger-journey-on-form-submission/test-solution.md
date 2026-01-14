---
title: ソリューションのテスト
description: フォーム送信時にメールを送信するジャーニーを作成
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00Z
jira: KT-20014
source-git-commit: 319b1cd4a037807a944e5fb6438e47b5fcf4c1c4
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# ソリューションのテスト


ソリューションのテスト
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## サンプルアセットのデプロイ

Node.js がインストールされていない場合は、ダウンロードして [ ここからインストールしてください ](https://nodejs.org/)

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

* [project-root.zip](assets/project-root.zip) を解凍し、`trigger-journey` フォルダーに配置します。

* `public` フォルダー内に `trigger-journey` というフォルダーを作成します。
* 適切な値で `.env` ファイルを更新します。 これらの値は、HTTP Source接続の作成時にダウンロードした cURL コマンドから使用できます。
* [index.zip](assets/index.zip) の内容を `public` フォルダーに解凍します

## サーバーの実行

`trigger-journey` ディレクトリにいることを確認します。
コマンドを実行します `node server.js`
ブラウザーで [web ページ ](http://localhost:3000/)
フォームに入力して送信します。 ジャーニーがトリガーされ、フォームに入力されたメール ID にメールが送信されます。


