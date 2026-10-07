---
title: Web SDKを使用したオーディエンスの構築
description: このチュートリアルでは、web フォームを通じてユーザーの環境設定を取得し、そのデータをリアルタイムでAdobe Experience Platform（AEP）に送信し、ユーザーの選択内容に基づいてユーザーをターゲットオーディエンスに動的に選定する方法について説明します。 Adobe Tags （Launch）、AEP Web SDK（Alloy.js）、Edge Segmentationを組み合わせることで、株式、債券、預金証明書（CD）に関心のある顧客に対して、即座にパーソナライズされたサービスを提供できます。
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%
---
# Web SDKを使用したオーディエンスの構築

このチュートリアルでは、web フォームを通じてユーザーの環境設定を取得し、そのデータをリアルタイムでAdobe Experience Platform（AEP）に送信し、ユーザーの選択内容に基づいてユーザーをターゲットオーディエンスに動的に選定する方法について説明します。 Adobe Tags （Launch）、AEP Web SDK（Alloy.js）、Edge Segmentationを組み合わせることで、株式、債券、預金証明書（CD）に関心のある顧客に対して、即座にパーソナライズされたサービスを提供できます。

## このチュートリアルの前提条件

* Adobe Experience Platformへのアクセス

* Adobe Experience Platformの基本コンセプト（プロファイル、オーディエンス、データセット）

* Adobe タグ（Launch）の概要 – データ要素とルールの設定

* JavaScriptの基本的な知識（簡単な関数の読み取りと書き込み）

* ブラウザー開発ツールの使用機能（コンソールおよびネットワークタブ）


## 目標

このチュートリアルの目的は、Adobe Experience Platform（AEP）で3つの異なるオーディエンスを構築して選定することです。

* ストックに興味のある顧客

* 債券に興味のある顧客

* CDに興味のあるユーザー

利用者はweb フォームを通じてプリファレンスを送信し、そのプリファレンスはAdobe Launchを使用してAEP Web SDKから取り込まれ、リアルタイムのオーディエンス評価が可能になります。

## 使用中のツール

* Adobe Experience Platform（AEP）

* Adobe Experience Platform Tags

* AEP Web SDK（Alloy.js）

* AEP Edgeのセグメンテーション

* 環境設定フォームを使用したweb ページ
