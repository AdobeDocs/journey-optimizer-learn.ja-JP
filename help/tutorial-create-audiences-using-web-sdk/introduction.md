---
title: Web SDKを使用したオーディエンスの構築
description: このチュートリアルでは、web フォームを通じてユーザーの環境設定を取得し、そのデータをリアルタイムでAdobe Experience Platform（AEP）に送信し、ユーザーの選択内容に基づいてユーザーをターゲットオーディエンスに動的に選定する方法について説明します。 Adobe Tags （Launch）、AEP Web SDK（Alloy.js）、Edge Segmentationを組み合わせることで、株式、債券、預金証明書（CD）に関心のある顧客に対して、即座にパーソナライズされたサービスを提供できます。
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
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
