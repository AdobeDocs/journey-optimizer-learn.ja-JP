---
title: AI モデルトレーニング用Adobe Web SDKとのオファーインタラクションのキャプチャ
description: この記事では、Adobe Experience Platform web SDK（alloy.js）を使用したユーザーインタラクションデータ（オファーのインプレッション数やクリック数など）のキャプチャに重点を置いています。 このデータは、Adobe Journey Optimizer（AJO）で AI モデルをトレーニングし、ユーザーの行動とコンテキストシグナルに基づいてオファーをインテリジェントにランク付けするための基盤となります。
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: dfb280df3453e7811dffd95b9af664b873a9af31
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 7%

---


# AI モデルトレーニング用Adobe Web SDKとのオファーインタラクションのキャプチャ

この記事では、JavaScript コードで alloy （&quot;sendEvent&quot;, ...）を直接呼び出し、Adobe Experience Platform web SDKを使用してオファーインタラクションイベント（インプレッション数やクリック数など）をキャプチャする方法について説明します。 このデータはAEPに取り込まれ、Adobe Journey Optimizer（AJO）の AI モデルのトレーニングに使用され、リアルタイムの行動に基づくよりスマートなオファーランキングを実現します。

## 前提条件

開始する前に、次の点を確認します。

- Adobe Web SDK拡張機能がインストールされた動作中のAdobe Experience Platform Launch プロパティ。

- AEP サンドボックスに設定およびマッピングされた [ データストリーム ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)。

- Launch がデプロイされている web サイト。


## オファーインタラクションイベント用のスキーマとデータセットの作成

エクスペリエンスイベントを収集するには、まずこれらのイベントを送信するデータセットを作成する必要があります。

この [ 記事で説明している手順に従って、必要なスキーマとデータセットを作成します ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)

## AEPでのデータストリームの作成

![data-stream](assets/ai-model-data-stream.png)
データストリームへのAdobe Experience Platform サービスの追加
![data-stream-service](assets/data-stream-service.png)

## Web SDKを使用したAdobe Experience Platform タグの設定

拡張機能の設定で、

作成したデータストリームを使用するようにAdobe Experience Platform Web SDK拡張機能を設定する
