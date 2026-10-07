---
title: 解決策をテスト
description: フォーム送信時にメールを送信するジャーニーを作成
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00.000Z
jira: KT-20014
exl-id: 9b4a3e0c-d153-4a6b-a7de-b926bd669f6a
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 1%
---
# 解決策をテスト


解決策をテスト
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## サンプルアセットのデプロイ

Node.jsがインストールされていない場合は、ここからダウンロードして[&#x200B; インストールします](https://nodejs.org/)

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
