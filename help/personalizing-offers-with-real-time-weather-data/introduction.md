---
title: Web SDKを使用した、Adobe Journey Optimizerのリアルタイム天気データによるオファーのパーソナライズ
description: このチュートリアルでは、リアルタイムのコンテキストデータとAdobe Web SDK Personalization API を使用して、動的で天気を認識したオファーをAdobe Journey Optimizerで配信する方法について説明します。 Web サイトからAdobe Experience Platformに天気属性（気温や条件など）を渡し、それらをイベントスキーマにマッピングして、決定ルールやランキング式で使用してページ読み込み時にオファーをパーソナライズする方法を学びます。 リアルタイムの環境コンテキストでデジタルエクスペリエンスを強化したいと考えているマーケターや開発者に最適です。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: d46c5a922b8448f57b8a730188284294c3caba96
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 1%

---

# ユースケースの説明

Adobe Journey Optimizer（AJO）の天候関連のデータを使用してオファーを提供すると、企業は、実際のリアルタイムの環境条件に基づいてカスタマーエクスペリエンスをパーソナライズできます。 天気は強力なコンテクストシグナルです。 人々のニーズや行動は天候によって変わります。 天気データを使用：

     顧客のムードや環境に合わせた適切なオファーを提供する。
    
     暑い日に、冷たい飲み物や AC ユニットのオファーを表示します。 雨の日には、ジャケットや傘を宣伝してください 

![ 天気予報オファー ](assets/offers-use-case.png)