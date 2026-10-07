---
title: 決定機能を使用したweb オファーのパーソナライゼーション
description: Journey Optimizer（AJO） Decisioningを使用して、Experience Platform（AEP）に組み込まれたオーディエンスセグメンテーションを活用して、web ページ上でパーソナライズされたオファーを配信する方法を説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
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
source-wordcount: '239'
ht-degree: 7%
---
# 決定機能を使用したweb オファーのパーソナライゼーション

このチュートリアルは、Adobe Experience Platform（AEP） Web SDKを使用して以前に作成したオーディエンスセグメンテーション設定に基づいています。 [前のチュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction)では、株式、債券、預金証明書（CD）への関心などのユーザー設定がキャプチャされ、Experience Platform内で個人をターゲットオーディエンスにセグメント化するために使用されました。 このチュートリアルでは、Adobe Journey Optimizer（AJO） Decisioningを使用して、それらのオーディエンスにパーソナライズされた金融オファーをリアルタイムで配信し、エンゲージメントとコンバージョンの両方の成果を向上させることにより、その基盤を構築します。


## このチュートリアルの前提条件

* Experience Platformへのアクセス

* Experience Platformの基本コンセプト（プロファイル、オーディエンス、データセット）

* Journey Optimizerの詳細

* JavaScriptの基本的な知識（簡単な関数の読み取りと書き込み）

* ブラウザー開発ツールの使用機能（コンソールおよびネットワークタブ）


## 目標

このチュートリアルでは、Journey Optimizerを使用して、株式、債券、CDなどのパーソナライズされた投資オファーをweb サイトで配信する方法を説明します。 オーディエンスのセグメンテーションと意思決定戦略を活用することで、各訪問者の好みに基づいて最も関連性の高いオファーを確実に提供する方法を把握できます。

## 使用中のツール

* Adobe Experience Platform（AEP）
* Adobe Journey Optimizer（AJO）
* Adobe Experience Platform Tags
* AEP Web SDK （`Alloy.js`）
* AEP Edgeのセグメンテーション
* オファーを表示するweb ページ
