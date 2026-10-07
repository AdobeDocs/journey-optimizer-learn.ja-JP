---
title: Web SDK とリアルタイム天候データを使用した Adobe Journey Optimizer でのオファーのパーソナライズ
description: このチュートリアルでは、リアルタイムコンテキストデータと Adobe Web SDK Personalization API を使用して、Adobe Journey Optimizer で天候に応じた動的なオファーを配信する方法を示します。 Web サイトから Adobe Experience Platform に天候属性（気温や条件など）を渡し、それらをイベントスキーマにマッピングして、決定ルールやランキング式で使用してページ読み込み時にオファーをパーソナライズする方法を学びます。 リアルタイムの環境コンテキストでデジタルエクスペリエンスを強化したいと考えているマーケターや開発者に最適です。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00.000Z
jira: KT-18258
exl-id: f40dd541-470c-4f42-8181-eb1c277ebaa3
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 43%
---
# ユースケースの説明

Adobe Journey Optimizer（AJO）の気象関連データを活用したオファーにより、実際のリアルタイムの環境条件にもとづいて顧客体験をパーソナライズできます。 天候は、コンテクストを示す強力なシグナルです。 人々のニーズや行動は、天候に応じて変化します。 気象データを利用する：

顧客のムードや環境に合わせた適切なオファーを提供します

暑い日には、冷たい飲み物やAC ユニットのオファーを示します。 雨の日には、上着や傘を宣伝しましょう

天候に応じたオファーの例


![weather-offers](assets/offers-use-case.png)



## このチュートリアルの前提条件

* Experience Platformへのアクセス：

* Adobe Experience Platform Tagsの基本。

* Experience Platformの基本コンセプト（プロファイル、オーディエンス、データセット）。

* Journey Optimizerの詳細。

* JavaScriptの基本的な知識（簡単な関数の読み取りと書き込み）。

* ブラウザー開発ツール （コンソールおよびネットワークタブ）の使用機能。
