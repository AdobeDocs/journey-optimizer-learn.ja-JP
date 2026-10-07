---
title: コードベースのエクスペリエンスチャネルの構築
description: AJOのチャネル設定では、web、電子メール、モバイルアプリなど、デジタル接点を通じて、オファーなどのパーソナライズされたコンテンツがどのように配信されるのかを定義できます。
role: User
feature: Decisioning
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: a7247b19-877b-4f62-b4d1-1c3a762b3433
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%
---
# コードベースのエクスペリエンスチャネルの構築

Adobe Journey Optimizer （AJO） [!UICONTROL Decisioning]でのコードベースのエクスペリエンスは、クライアントサイドのJavaScriptを使用して、パーソナライズされたオファーをweb ページに直接配信できるようにする設定です。 このアプローチでは、定義済みのテンプレートやビジュアルレイアウトツールに依存するのではなく、Adobe Web SDK （`Alloy.js`）を使用してオファーをレンダリングするタイミングと場所を開発者が完全に制御できます。

![create-channel](assets/cbe-channel.png)
