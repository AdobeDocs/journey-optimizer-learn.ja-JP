---
title: Decisioning を使用して web オファーをパーソナライズ
description: Journey Optimizer（AJO） Decisioning を使用し、Experience Platform（AEP）に組み込まれたオーディエンスセグメント化を活用して、パーソナライズされたオファーを web ページで提供する方法を説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 0c42bf9a9af53bf80a14d904733ae0c1f03be0ee
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Decisioning を使用した web オファーのパーソナライズ

このチュートリアルは、Adobe Experience Platform（AEP） web SDKを使用して以前に作成したオーディエンスセグメント化の設定に基づいています。 [ 前のチュートリアル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction) では、ユーザーの環境設定（株式に対する関心、債券、預金証書（CD）など）が取得され、Adobe Experience Platform（AEP）内で個人をターゲットオーディエンスにセグメント化するために使用されました。 このチュートリアルでは、その基盤に基づき、Adobe Journey Optimizer（AJO） Decisioning を使用して、パーソナライズされたオファーをリアルタイムでこれらのオーディエンスに提供し、エンゲージメントとコンバージョンの両方の成果を高めます。

以下のリンクを使用して、パーソナライズされたAJO オファーをライブでテストできます。
[ ライブデモを表示するには、ここをクリックしてください ](https://gbedekar489.github.io/finwise/welcome.html) — ページには、投資の好みに基づいてリアルタイムのオファーが表示されます。

## このチュートリアルの前提条件

* Adobe Experience Platformへのアクセス

* Adobe Experience Platformの概念（プロファイル、オーディエンス、データセット）の基本的な理解

* Adobe Journey Optimizerに精通していること

* JavaScriptの基本的な知識（簡単な関数の読み取りと書き込み）

* ブラウザー開発ツールを使用する機能（「コンソール」タブと「ネットワーク」タブ）


## 目標

このチュートリアルでは、Adobe Journey Optimizer（AJO）を使用して、web サイト上で株式、債券、CD などパーソナライズされた投資オファーを提供する手順を説明します。 オーディエンスのセグメント化と判定戦略を活用することで、各訪問者の好みに基づいて最も関連性の高いオファーを確実に表示する方法を学びます。

## 使用するツール

* Adobe Experience Platform（AEP）
* Adobe Journey Optimizer（AJO）
* Adobe Experience Platform タグ
* AEP Web SDK（Alloy.js）
* AEP Edgeのセグメント化
* オファーを表示する web ページ
