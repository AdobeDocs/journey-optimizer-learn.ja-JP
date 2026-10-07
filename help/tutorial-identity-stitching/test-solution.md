---
title: 解決策のテスト
description: 解決策をテスト
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: b7bad65d-c978-4981-a914-6cb039433c8b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%
---
# ID接続のテスト

このサンプルアプリケーションは、CRM IDがAdobe Experience Platform（AEP）に送信される前に、サーバーサイドでユーザーの資格情報が検証される実際のログインフローをシミュレートします。 ローカルのNode.js サーバーを使用すると、web ページを安全に配信し、基本的な認証ロジックを処理し、Adobe LaunchまたはWeb SDKの機能を妨げる可能性があるブラウザーの制限（ローカルファイルアクセスのブロックやCORS ヘッダーの欠落など）を回避できます。 この設定により、エクスペリエンスが実際の本番環境に近づきます。

## node.jsのインストール

Node.jsがインストールされていない場合は、ここからダウンロードして[ インストールします](https://nodejs.org/)

次のコマンドを実行してインストールを確認します。

`node -v`

`npm -v`

## プロジェクトフォルダーの設定

次のコマンドを使用して、サンプルアプリの新しいディレクトリを作成します

`mkdir aep-demo`

`cd aep-demo`

## プロジェクトの初期化

`npm init -y`

## Express （Web サーバーフレームワーク）のインストール

`npm install express`

## server.js ファイルの作成

```javascript
const express = require('express');
const path = require('path');
const app = express();
const PORT = 3000;

// Serve static files from the current directory
app.use(express.static(__dirname));

app.listen(PORT, () => {
  console.log(`Server is running at http://localhost:${PORT}`);
});
```

## HTML/Assetsを追加

指定したすべての[HTMLおよびCSS ファイル ](assets/login-app-files.zip)をこのフォルダーにコピーします。 AEP Tags スクリプトをコピーして、index.html ファイルの`<head>` セクション内に貼り付けます。

## サーバーの実行

`node server.js`

## テスト

`http://localhost:3000` URLを開きます。 alice/pass123を使用してログインします

## AEP Debuggerの使用

Adobe Experience Platform Debuggerは、web サイトからAdobe Experience Platformに送信されるデータの検証に役立つ強力なブラウザー拡張機能です。 特に、IDMapが正しく設定され、Adobe Web SDK（alloy.js）を介して送信されているかどうかを確認するのに便利です。

ログインイベントのテスト、ID ステッチの検証（ECIDやCRMIDの渡しなど）、AEP Tags ルールおよびData Elementsが期待どおりに実行されていることを確認する場合は、AEP Debuggerを使用します。 送信イベント、ID情報、XDM ペイロードをリアルタイムで可視化し、プロファイルのエンリッチメントとオーディエンスの選定をトラブルシューティングするために不可欠です。

次のスクリーンショットは、ID 「FIN001」が正しく渡されていることを示しています。
![aep-debugger](assets/aep-debugger.png)

## AEPでID ステッチングを検証する手順

* AEPへのログイン
* 顧客/プロファイル/参照に移動します。
* FinWise CRM ID = FIN001を検索
* プロファイルを開き、「ID」セクションを確認します。 CRMIDとECIDの両方が表示されます。   これにより、ふたつのIDが単一のプロファイルにつなぎ合わされていることを確認できます。


