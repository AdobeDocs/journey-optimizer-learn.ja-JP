---
title: コードベースのエクスペリエンスチャネルを作成
description: AJOのチャネル設定では、web、メール、モバイルアプリ、その他のデジタルタッチポイントなど、特定のチャネルを使用してパーソナライズされたコンテンツ（オファーなど）を配信する方法を定義します。
role: User
feature: Decisioning
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: a7247b19-877b-4f62-b4d1-1c3a762b3433
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%

---

# コードベースのエクスペリエンスチャネルを作成

Adobe Journey Optimizer（AJO）のコードベースのエクスペリエンス [!UICONTROL  意思決定 ] は、クライアントサイドのJavaScriptを使用して、パーソナライズされたオファーを web ページに直接配信できるようにする設定です。 このアプローチでは、事前定義済みのテンプレートや視覚的なレイアウトツールを使用する代わりに、Adobe web SDK（`Alloy.js`）を使用してオファーをレンダリングするタイミングと場所を開発者が完全に制御できます。

![create-channel](assets/cbe-channel.png)
