---
title: AJO キャンペーンの頻度キャップを有効にする
description: Adobe Journey Optimizerの頻度キャッピングは、個々のオファーレベルで適用され、オファーインプレッションとクリックイベントの両方を取得する必要があります。 そのためには、Adobe Web SDKを使用してトラッキング decisioning.propositionDisplayおよびdecisioning.propositionInteract イベントを作成し、Adobe Experience Platformで更新されたXDM Experience Event スキーマにマッピングする必要があります。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21
jira: KT-18526
exl-id: 34027499-0037-4ea1-813b-51be15eafe24
source-git-commit: d4cc60f4448caec92f704026783e2bbe029427f5
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%
---
# AJO キャンペーンの頻度キャップを有効にする

オファーに頻度キャップを適用するには、次の手順を実行します。

## イベントスキーマの更新

* 次に示すように、フィールドグループを追加して、既存のイベントスキーマを更新します
* ![event-schema](assets/schema.png)

## オファーの頻度キャップを更新します


* ![オファー](assets/offer-capping.png)

## オファーにトラッキングトークンを追加

フォールバックオファーを追加して、キャンペーンで使用される決定ポリシーを編集します
![ フォールバック ](assets/fallback.png)

トラッキングトークンとItemIDは、左側のナビゲーションの決定ポリシーアイコンをクリックし、決定ツリーをドリルダウンしてitemIDとtrackingTokenを選択することで追加できます。

次に示すように、アイテム IDとトラッキングトークンをオファーを含むdivに追加します
![id-and-tracking-token](assets/id-and-tracking-token.png)

これにより、レンダリングされた各オファーにデータトラッキングトークンが含まれるようになり、正確なインプレッションとクリックイベントのトラッキングに不可欠です。


変更したキャンペーンをアクティブ化します。


## インプレッションおよびトラッキングイベントの送信

既存のJavaScript コードを変更して、オファーのインプレッションおよびインタラクションイベントをキャプチャし、Adobe Web SDKを使用してAdobe Experience Platformに送信します。 ここで提供されている[ サンプルコードを参照してください。](capture-impression-click-events.md)
