---
title: AEPでのID接続
description: 既知のユーザー（CRMID）と匿名の web 訪問者（ECID）の間の ID ステッチを確立し、Adobe Journey Optimizer（AJO）でリアルタイムのパーソナライズ機能とオファー決定支援のための統合プロファイルを有効にします。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 11%
---
# AEPでのID接続

今日の顧客体験では、デバイスとチャネルをまたいでユーザーIDを統合することが重要です。 このユースケースでは、ユーザーのログイン時にキャプチャされた既知のCRM IDを、Adobe Experience Platform（AEP） Web SDKによって生成された匿名のExperience Cloud ID （ECID）にリンクすることにより、Adobe（）でID ステッチを実装する方法を示します。 AEPを利用すれば、これらのIDをリアルタイムで統合し、匿名の行動と認証されたデータの両方にまたがる、より包括的な顧客プロファイルを構築できます。 これにより、Adobe Journey Optimizer（AJO）のようなツール内で、より正確なオーディエンスのセグメンテーション、パーソナライズ、意思決定が可能になります。

## ID ステッチングのチュートリアルに必要なスキル

このチュートリアルを最大限に活用するには、次のことに慣れることが推奨されます。

- **Adobe Experience Platform（AEP）のコアコンセプト**\
  スキーマ、データセット、ID、結合ポリシー、リアルタイムプロファイルの理解。

- **スキーマとID モデリング**\
  プロファイルベースおよびイベントベースのスキーマでID フィールドを設定する機能。

- **Adobe Launch （Tags）とWeb SDK （Alloy.js）**\
  Web SDKを使用してAEPにデータを送信するためのデータ要素とルールの設定の経験。

- **JavaScriptの基本**\
  関数を使用して、ユーザー入力、トリガーイベント、およびデバッグ API呼び出しをキャプチャする作業が容易です。

- **AEP デバッグ ツール**\
  AEP DebuggerとIdentity Graph Viewerを使用して、IDの合成を検証する機能。

- **AEPでのデータ取り込み**\
  サンプルデータのデータセットへのアップロードとデータ品質の確保に関する知識。


