---
title: オーディエンスの作成
description: ユーザーの投資環境設定（株式、債券、CD）に基づくAJO オーディエンスの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---


# ユーザーの投資環境設定（株式、債券、CD）に基づくAJO オーディエンスの作成

このチュートリアルでは、web フォームを通じてユーザーの環境設定を取得し、そのデータをリアルタイムでAdobe Experience Platform（AEP）に送信し、選択に基づいてユーザーをターゲットオーディエンスに動的に選定する方法を学びます。 Adobe Tags （Launch）、AEP Web SDK（Alloy.js）、Edge Segmentation を組み合わせることで、株式、債券、預金証書（CD）に興味があるお客様に対して、即時にパーソナライズの機会を提供できます。

## このチュートリアルの前提条件

* Adobe Experience Platformへのアクセス

* Adobe Experience Platformの概念（プロファイル、オーディエンス、データセット）の基本的な理解

* Adobe タグ（Launch）の知識 – データ要素とルールの設定

* JavaScriptの基本的な知識（簡単な関数の読み取りと書き込み）

* ブラウザー開発ツールを使用する機能（「コンソール」タブと「ネットワーク」タブ）


## 目標

このチュートリアルの目的は、Adobe Experience Platform（AEP）で 3 つの異なるオーディエンスを作成し、選定することです。

* Stock に関心のあるお客様

* 社債に関心のあるお客様

* CD に関心のあるお客様

ユーザーは web フォームを通じて環境設定を送信し、これらの環境設定はAdobe Launch を使用してAEP Web SDKを介して取り込まれ、リアルタイムのオーディエンスの選定が可能になります。

## 使用するツール

* Adobe Experience Platform（AEP）

* Adobe Experience Platform タグ

* AEP Web SDK（Alloy.js）

* AEP Edgeのセグメント化

* 環境設定フォームが含まれている web ページ





