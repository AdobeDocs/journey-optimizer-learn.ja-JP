---
title: AEPでの ID の組み合わせ
description: 既知のユーザー（CRMID）と匿名の web 訪問者（ECID）の間の ID ステッチを確立し、Adobe Journey Optimizer（AJO）でリアルタイムのパーソナライゼーションと Offer Decisioning のための統合プロファイルを有効にします。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
source-git-commit: 96d9d525a3d9be399f7fa229b67166acf8130721
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 1%

---

# ユースケースの説明

最新の顧客体験では、デバイスやチャネルをまたいでユーザー ID を統合することが重要です。 このユースケースでは、ユーザーのログイン時に取得された既知の CRM ID を、Adobe Experience Platform Web SDKで生成された匿名のExperience Cloud ID （ECID）にリンクすることで、Adobe（AEP）で ID ステッチを実装する方法を示しています。 これらの ID をリアルタイムで結び付けることで、AEPは、匿名の行動と認証済みのデータの両方にまたがる、より完全な顧客プロファイルを作成できます。 これにより、Adobe Journey Optimizer（AJO）などのツール内で、より正確なオーディエンスのセグメント化、パーソナライゼーションおよび意思決定が可能になります。

## Id ステッチチュートリアルに必要な 🧠 スキル

このチュートリアルを最大限に活用するには、次の点に関する知識をお勧めします。

- **Adobe Experience Platform（AEP）の中心概念**\
  スキーマ、データセット、ID、結合ポリシーおよびリアルタイムプロファイルに関する知識。

- **スキーマと ID のモデリング**\
  プロファイルベースおよびイベントベースのスキーマで ID フィールドを設定する機能。

- **Adobe Launch （Tags）および Web SDK（Alloy.js）**\
  Web SDKを使用してAEPにデータを送信するためのデータ要素とルールのセットアップ経験。

- **JavaScriptの基本**\
  ユーザー入力、トリガーイベントおよびデバッグ API 呼び出しをキャプチャする機能の操作に慣れています。

- **AEP デバッグツール**\
  AEP デバッガーと ID グラフビューアを使用して、ID ステッチを検証する機能。

- **AEPでのデータ取得**\
  サンプルデータのデータセットへのアップロードとデータ品質の確保に関する知識。


