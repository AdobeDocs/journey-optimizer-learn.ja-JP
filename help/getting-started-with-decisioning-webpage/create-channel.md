---
title: コードベースのエクスペリエンスチャネルを作成
description: AJOのチャネル設定では、web、メール、モバイルアプリ、その他のデジタルタッチポイントなど、特定のチャネルを使用してパーソナライズされたコンテンツ（オファーなど）を配信する方法を定義します。
role: User
feature: Decisioning
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
source-git-commit: a675979bc590190e0481e63efbc2cfd30752b7c0
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 0%

---


# コードベースのエクスペリエンスチャネルを作成

Adobe Journey Optimizer（AJO）のコードベースのエクスペリエンス決定は、クライアントサイド JavaScriptを使用して、パーソナライズされたオファーを web ページに直接配信できるようにする設定です。 このアプローチでは、事前定義済みのテンプレートや視覚的なレイアウトツールを使用する代わりに、Adobe web SDK（Alloy.js）を使用してオファーをレンダリングするタイミングと場所を開発者が完全に制御できます。

![create-channel](assets/cbe-channel.png)