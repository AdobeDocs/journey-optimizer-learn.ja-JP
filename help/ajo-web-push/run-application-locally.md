---
title: アプリケーションをローカルで実行
description: サンプルアプリケーションをローカルに設定して、AJOを使用してweb プッシュ通知フローを調べます。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 2635641b-5ae2-4303-bac7-02c3702950f0
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# アプリケーションをローカルで実行

このページでは、サンプルアプリケーションをローカルに設定する方法を説明します。これにより、Adobe Journey Optimizerを使用してweb プッシュ通知フローをテストおよび確認できます。 リポジトリのクローンを作成し、環境変数を設定し、ローカルシステムでアプリケーションを実行します。


次の手順に従って、ローカルシステムでサンプルアプリケーションを実行します。

## &#x200B;1. Node.jsのインストール

システムに&#x200B;**Node.js （バージョン 16以降）**&#x200B;がインストールされていることを確認してください。

[こちらからダウンロードできます：](https://nodejs.org/)

インストールの確認

```node -v```

```npm -v```


## &#x200B;2. リポジトリのクローンを作成

```git clone https://github.com/gbedekar489/ajo-web-push.git```

```cd ajo-web-push```

## &#x200B;3. 依存関係のインストール

```npm install```

## &#x200B;4. 環境変数の設定

ルートディレクトリに.env ファイルを作成し、次を追加します。

```
DATASTREAM_ID=your_datastream_id
ORG_ID=your_org_id
VAPID_PUBLIC_KEY=your_vapid_public_key
APP_ID=your_app_id
DATASET_ID=your_event_dataset_id
PORT=3000
```


ローカルで実行する場合、これらの値は.env ファイルから読み取られます。 実稼動環境（レンダリングなど）では、環境変数として設定されます。
