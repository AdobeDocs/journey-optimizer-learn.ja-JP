---
title: Web SDKを使用したオーディエンスの作成
description: このチュートリアルでは、web フォームを通じてユーザーの環境設定を取得し、そのデータをリアルタイムでAdobe Experience Platform（AEP）に送信し、選択に基づいてユーザーをターゲットオーディエンスに動的に選定する方法を学びます。 Adobe Tags （Launch）、AEP Web SDK（Alloy.js）、Edge Segmentation を組み合わせると、株式、債券、預金証明書（CD）に興味があるお客様に、すぐにパーソナライズの機会を提供できます。
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Web SDKを使用したオーディエンスの作成

このチュートリアルでは、web フォームを通じてユーザーの環境設定を取得し、そのデータをリアルタイムでAdobe Experience Platform（AEP）に送信し、選択に基づいてユーザーをターゲットオーディエンスに動的に選定する方法を学びます。 Adobe Tags （Launch）、AEP Web SDK（Alloy.js）、Edge Segmentation を組み合わせると、株式、債券、預金証明書（CD）に興味があるお客様に、すぐにパーソナライズの機会を提供できます。

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

ユーザーは web フォームを通じて環境設定を送信し、それらの環境設定はAdobe Launch を使用してAEP Web SDKを介して取り込まれ、リアルタイムのオーディエンスの選定が可能になります。

## 使用するツール

* Adobe Experience Platform（AEP）

* Adobe Experience Platform タグ

* AEP Web SDK（Alloy.js）

* AEP Edgeのセグメント化

* 環境設定フォームが含まれている web ページ
