---
title: 決定機能を使用したweb オファーのパーソナライゼーション
description: Journey Optimizer（AJO） Decisioningを使用して、Experience Platform（AEP）に組み込まれたオーディエンスセグメンテーションを活用して、web ページ上でパーソナライズされたオファーを配信する方法を説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 7d812f589172c5052a1e9bfcf6a99d0769a6c2c7
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# 決定機能を使用したweb オファーのパーソナライゼーション

このチュートリアルは、Adobe Experience Platform（AEP） Web SDKを使用して以前に作成したオーディエンスセグメンテーション設定に基づいています。 [前のチュートリアル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction)では、株式、債券、預金証明書（CD）への関心などのユーザー設定がキャプチャされ、Experience Platform内で個人をターゲットオーディエンスにセグメント化するために使用されました。 このチュートリアルでは、Adobe Journey Optimizer（AJO） Decisioningを使用して、それらのオーディエンスにパーソナライズされた金融オファーをリアルタイムで配信し、エンゲージメントとコンバージョンの両方の成果を向上させることにより、その基盤を構築します。


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
