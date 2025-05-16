---
title: AEPでの ID の組み合わせ
description: 既知のユーザー（CRMID）と匿名の web 訪問者（ECID）の間の ID ステッチを確立し、Adobe Journey Optimizer（AJO）でリアルタイムのパーソナライゼーションと Offer Decisioning のための統合プロファイルを有効にします。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 2%

---


# ユースケースの説明

最新の顧客体験では、デバイスやチャネルをまたいでユーザー ID を統合することが重要です。 このユースケースでは、ユーザーのログイン時に取得された既知の CRM ID を、Adobe Experience Platform Web SDKで生成された匿名のExperience Cloud ID （ECID）にリンクすることで、Adobe（AEP）で ID ステッチを実装する方法を示しています。 これらの ID をリアルタイムで結び付けることで、AEPは、匿名の行動と認証済みのデータの両方にまたがる、より完全な顧客プロファイルを作成できます。 これにより、Adobe Journey Optimizer（AJO）などのツール内で、より正確なオーディエンスのセグメント化、パーソナライゼーションおよび意思決定が可能になります。

