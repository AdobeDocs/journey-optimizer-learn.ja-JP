---
title: ソリューションのテスト
description: ソリューションのテスト
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: b7bad65d-c978-4981-a914-6cb039433c8b
source-git-commit: 71b42350370d12ce677bf075d8b48edcbe541ab4
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# ID のステッチのテスト

このサンプルアプリケーションでは、CRM ID がAdobe Experience Platform（AEP）に送信される前に、ユーザーの資格情報がサーバーサイドで検証される、実際のログインフローをシミュレートします。 ローカルの Node.js サーバーを使用すると、web ページを安全に提供し、基本的な認証ロジックを処理し、Adobe Launch や web SDKの機能に干渉する可能性のあるブラウザー制限（ローカルファイルへのアクセスのブロックや CORS ヘッダーの欠落など）を回避できます。 このセットアップにより、実際の実稼動環境に近いエクスペリエンスが得られます。

## node.js のインストール

Node.js がインストールされていない場合は、ダウンロードして [&#x200B; ここからインストールしてください &#x200B;](https://nodejs.org/)

次のコマンドを実行してインストールを確認します。

`node -v`

`npm -v`

## プロジェクトフォルダーの設定

次のコマンドを使用して、サンプルアプリ用の新しいディレクトリを作成します

`mkdir aep-demo`

`cd aep-demo`

## プロジェクトの初期化

`npm init -y`

## Express （Web サーバ・フレームワーク）のインストール

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

指定されたすべての [HTMLと CSS ファイル &#x200B;](assets/login-app-files.zip) をこのフォルダーにコピーします。 AEP タグ スクリプトをコピーして、index.html ファイルの `<head>` セクション内に貼り付けます。

## サーバーの実行

`node server.js`

## テスト

`http://localhost:3000` の URL を開きます。 alice/pass123 を使用してログインします。

## AEP Debugger の使用

Adobe Experience Platform Debuggerは、Web サイトからAdobe Experience Platformに送信されるデータを検証するのに役立つ強力なブラウザー拡張機能です。 identityMap が正しく設定され、Adobe web SDK（alloy.js）経由で送信されているかどうかを確認するのに特に便利です。

ログインイベントのテスト、ID ステッチの検証（ECID と CRMID の受け渡しなど）、AEP タグルールおよびデータ要素が期待どおりに実行されていることを確認する場合は、AEP Debugger を使用します。 発信イベント、ID 情報および XDM ペイロードをリアルタイムで可視化します。これは、プロファイルのエンリッチメントとオーディエンスの選定をトラブルシューティングするために重要です。

次のスクリーンショットは、ID 「FIN001」が正しく渡されていることを示しています。
![aep-debugger](assets/aep-debugger.png)

## AEPでの ID ステッチを検証する手順

* AEPにログインします
* 顧客/ プロファイル /参照に移動します。
* FinWise CRM ID = FIN001 を検索
* プロファイルを開き、「ID」セクションを確認します。 CRMID と ECID の両方がリストされます。   これにより、2 つの ID が単一のプロファイルにステッチされたことが確認されます。
* ジャーニーもトリガーされます。ジャーニーレポートを表示して、これを確認します
* ![&#x200B; ジャーニーレポート &#x200B;](assets/journey-triggered-report.png)


