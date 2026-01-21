---
title: AJO Decisioning を使用して配信されるAdobe Journey Optimizer（AJO）オファーにフリークエンシーキャップを実装します
description: このチュートリアルでは、AJO Decisioning を使用して提供されるオファーのフリークエンシーキャップを有効にすることで、既存のAdobe Journey Optimizer（AJO）の実装を拡張します。 フリークエンシーキャップで使用されるインプレッションとインタラクションイベントをキャプチャする方法の概要を説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# AJO Decisioning を使用して配信されるAdobe Journey Optimizer（AJO）オファーにフリークエンシーキャップを実装します

このチュートリアルでは、Adobe Journey Optimizerのオファーにフリークエンシーキャップを適用し、ユーザーが同じオファーを経時的に見る頻度を制御する方法について説明します。

Adobe Journey Optimizerは、Adobe Web SDKを通じて decisioning.propositionDisplay イベントと decisioning.propositionInteract イベントをキャプチャし、Adobe Experience Platform（AEP）の XDM スキーマにマッピングすることで、オファーのインプレッションとインタラクションを正確にトラッキングし、フリークエンシーキャップを有効にして、オファーがユーザーに表示される頻度を制限できます。

## このチュートリアルの前提条件

先に進む前に、Web サーフェスに対してアクティブにオファーを提供している Decisioning を使用して有効なAdobe Journey Optimizer キャンペーンがあることを確認してください。

このチュートリアルでは、オファー配信が既に機能していることを前提としており、フリークエンシーキャップ動作の設定と検証にのみ焦点を当てています。


