---
title: Decisioning を使用した web オファーのパーソナライズ
description: Journey Optimizer（AJO） Decisioning を使用し、Experience Platform（AEP）に組み込まれたオーディエンスセグメント化を活用して、パーソナライズされたオファーを web ページで提供する方法を説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 7d812f589172c5052a1e9bfcf6a99d0769a6c2c7
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 2%

---

# Decisioning を使用した web オファーのパーソナライズ

このチュートリアルは、Adobe Experience Platform（AEP） web SDKを使用して以前に作成したオーディエンスセグメント化の設定に基づいています。 [ 前のチュートリアル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction) では、株式に対する興味、債券、預金証書（CD）などのユーザー環境設定が取得され、Experience Platform内で個人をターゲットオーディエンスにセグメント化するために使用されました。 このチュートリアルでは、その基盤に基づき、Adobe Journey Optimizer（AJO） Decisioning を使用して、パーソナライズされたオファーをリアルタイムでこれらのオーディエンスに提供し、エンゲージメントとコンバージョンの両方の成果を高めます。


## このチュートリアルの前提条件

* Experience Platformへのアクセス

* Experience Platformの概念（プロファイル、オーディエンス、データセット）の基本的な理解

* Journey Optimizerに精通していること

* JavaScriptの基本的な知識（簡単な関数の読み取りと書き込み）

* ブラウザー開発ツールを使用する機能（「コンソール」タブと「ネットワーク」タブ）


## 目標

このチュートリアルでは、Journey Optimizerを使用して、web サイト上で株式、債券、CD などパーソナライズされた投資オファーを提供する手順を説明します。 オーディエンスのセグメント化と判定戦略を活用することで、各訪問者の好みに基づいて最も関連性の高いオファーを確実に表示する方法を学びます。

## 使用するツール

* Adobe Experience Platform（AEP）
* Adobe Journey Optimizer（AJO）
* Adobe Experience Platform タグ
* AEP Web SDK（`Alloy.js`）
* AEP Edgeのセグメント化
* オファーを表示する web ページ
