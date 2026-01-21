---
title: AJO キャンペーンのフリークエンシーキャップの有効化
description: Adobe Journey Optimizerのフリークエンシーキャップは、個々のオファーレベルで適用され、オファーのインプレッションとクリックイベントの両方をキャプチャします。 これには、Adobe Web SDKを使用してトラッキング decisioning.propositionDisplay イベントと decisioning.propositionInteract イベントをトラッキングし、Adobe Experience Platformで更新された XDM エクスペリエンスイベントスキーマにマッピングする必要があります。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# AJO キャンペーンのフリークエンシーキャップの有効化

オファーにフリークエンシーキャップを適用するには、次の手順を実行します。

## イベントスキーマの更新

* 次に示すように、フィールドグループを追加して、既存のイベントスキーマを更新します
* ![event-schema](assets/schema.png)

## オファーのフリークエンシーキャップの更新


* ![オファー](assets/offer-capping.png)

## オファーにトラッキングトークンを追加

フォールバックオファーを追加して、キャンペーンで使用する決定ポリシーを編集
![ フォールバック ](assets/fallback.png)

trackingToken と ItemID を追加するには、左側のナビゲーションで「決定ポリシー」アイコンをクリックし、決定ツリーをドリルダウンして、itemID と trackingToken を選択します。

以下に示すように、オファーを含む div に項目 ID とトラッキングトークンを追加します
![id-and-tracking-token](assets/id-and-tracking-token.png)

これにより、レンダリングされた各オファーにデータトラッキングトークンが含まれます。これは、正確なインプレッションおよびクリックイベントの追跡に不可欠です。


変更したキャンペーンをアクティブ化します。


## インプレッションとトラッキングイベントの送信

既存のJavaScript コードを変更し、Adobe web SDKを使用して、オファーのインプレッションとインタラクションイベントを取得してAdobe Experience Platformに送信します。 ここで提供される [ サンプルコード ](capture-impression-click-events.md) を参照してください。


