---
title: コードベースのエクスペリエンスチャネルの構築
description: AJOのチャネル設定では、web、電子メール、モバイルアプリなど、デジタル接点を通じて、オファーなどのパーソナライズされたコンテンツがどのように配信されるのかを定義できます。
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
source-wordcount: '97'
ht-degree: 0%

---

# コードベースのエクスペリエンスチャネルの構築

Adobe Journey Optimizer （AJO） [!UICONTROL Decisioning]でのコードベースのエクスペリエンスは、クライアントサイドのJavaScriptを使用して、パーソナライズされたオファーをweb ページに直接配信できるようにする設定です。 このアプローチでは、定義済みのテンプレートやビジュアルレイアウトツールに依存するのではなく、Adobe Web SDK （`Alloy.js`）を使用してオファーをレンダリングするタイミングと場所を開発者が完全に制御できます。

![create-channel](assets/cbe-channel.png)
