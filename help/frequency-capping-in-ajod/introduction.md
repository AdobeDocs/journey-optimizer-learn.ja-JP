---
title: AJO Decisioningを介して配信されるAdobe Journey Optimizer（AJO）オファーに対する頻度キャッピングを実装する
description: このチュートリアルでは、AJO Decisioningを使用して提供されるオファーに対する頻度キャッピングを有効にすることで、既存のAdobe Journey Optimizer（AJO）の実装を拡張します。 頻度の上限で使用されるインプレッションとインタラクションイベントをキャプチャする方法の概要を示します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
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
source-wordcount: '214'
ht-degree: 7%
---
# AJO Decisioningを介して配信されるAdobe Journey Optimizer（AJO）オファーに対する頻度キャッピングを実装する

このチュートリアルでは、Adobe Journey Optimizerのオファーに頻度キャッピングを適用して、ユーザーが同じオファーを表示する頻度を制御する方法を説明します。

このチュートリアルでは、気象条件に基づくオファーのパーソナライズに関する[ チュートリアル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)に従って、AJO キャンペーンを既に設定していることを前提としています

decisioning.propositionDisplayおよびdecisioning.propositionInteract イベントをAdobe Web SDKを通じてキャプチャし、それらをAdobe Experience Platform（AEP）のXDM スキーマにマッピングすることで、Adobe Journey Optimizerはオファーインプレッションとインタラクションを正確に追跡でき、頻度の上限を設定してユーザーにオファーを表示する頻度を制限することができます。

## このチュートリアルの前提条件

続行する前に、Web サーフェスにオファーをアクティブに配信するDecisioningを使用して、有効なAdobe Journey Optimizer キャンペーンがあることを確認してください。

このチュートリアルでは、オファー配信が既に機能していることを前提としており、頻度の上限を設定および検証することに焦点を当てています。




