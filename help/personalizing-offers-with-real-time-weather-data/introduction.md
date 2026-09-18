---
title: Web SDK とリアルタイム天候データを使用した Adobe Journey Optimizer でのオファーのパーソナライズ
description: このチュートリアルでは、リアルタイムコンテキストデータと Adobe Web SDK Personalization API を使用して、Adobe Journey Optimizer で天候に応じた動的なオファーを配信する方法を示します。 Web サイトから Adobe Experience Platform に天候属性（気温や条件など）を渡し、それらをイベントスキーマにマッピングして、決定ルールやランキング式で使用してページ読み込み時にオファーをパーソナライズする方法を学びます。 リアルタイムの環境コンテキストでデジタルエクスペリエンスを強化したいと考えているマーケターや開発者に最適です。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10
jira: KT-18258
exl-id: f40dd541-470c-4f42-8181-eb1c277ebaa3
source-git-commit: b4cf9b677c6bc142e1013649db16b3a70b405052
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
