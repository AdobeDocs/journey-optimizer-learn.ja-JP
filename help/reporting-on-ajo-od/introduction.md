---
title: AJO Decisioning を使用して配信されたAdobe Journey Optimizer（AJO）オファーのトラッキングとレポート
description: このチュートリアルでは、気温などのコンテキストデータに基づいてパーソナライズされたオファーを提供する、既存のAdobe Journey Optimizer（AJO）の実装を拡張します。 インプレッションとインタラクションイベントをキャプチャし、Journey Optimizer内でレポート用にデータを準備する方法の概要を説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: bfeab1e933f2a510506c0ecf911df41e66cb959b
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# AJO Decisioning を使用して配信されたAdobe Journey Optimizer（AJO）オファーのトラッキングとレポート

このユースケースでは、Adobe Journey Optimizer（AJO）で配信されるオファーのレポートおよびパフォーマンス分析を有効にすることに重点を置いています。 オファーが状況に応じて（天気や場所などの）シグナルに基づいてパーソナライズおよび配信される場合、インプレッションとユーザーインタラクションの両方をトラッキングして有効性を評価することが不可欠です。

Adobe Web SDKを介して decisioning.propositionDisplay イベントと decisioning.propositionInteract イベントをキャプチャし、それらをAdobe Experience Platform（AEP）の構造化された XDM スキーマにマッピングすることで、オファーレベルのエンゲージメントデータを分析できるようになります。 その後、このデータをCustomer Journey Analytics（CJA）で使用して、ダッシュボードを作成したり、クリックスルー率（CTR）などの主要指標を測定したり、様々なオーディエンスセグメントやコンテキスト条件におけるオファーのパフォーマンスを比較したりできます。

目標は、パーソナライズされたオファーのパフォーマンスに関する明確なデータ駆動型のインサイトを提供し、将来の意思決定戦略を伝えることです。



![reporting-dashboard](assets/dashboard-reporting.png)


## このチュートリアルの前提条件

始める前に、[ リアルタイムの天気データを使用したオファーのパーソナライズ」チュートリアルを完了してください。](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction) 次のような基本的なコンポーネントがすべて確立されます。

- Web SDKの統合
- Adobe Journey Optimizer（AJO）でのオファー設定
- 天気や温度などのコンテキスト属性を使用した決定
- Web ページでのリアルタイムオファーレンダリング

このチュートリアルでは、その実装に直接基づいて、Journey Optimizerでのレポートや分析用にオファーのインプレッションやインタラクションをキャプチャすることに特に重点を置いています。
