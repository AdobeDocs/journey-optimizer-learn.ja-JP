---
title: AJO Offer Decisioningから配信されたAdobe Journey Optimizer （AJO）オファーのトラッキングとレポート
description: このチュートリアルでは、気温などのコンテキストデータに基づいてパーソナライズされたオファーを提供する、既存のAdobe Journey Optimizer（AJO）の実装を拡張します。 インプレッションおよびインタラクションイベントを取得し、Journey Optimizer 内でレポート用のデータを準備する方法の概要を説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18526
source-git-commit: fa4795d92cf290b867df23277a297c99d6222224
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# オファー項目へのトラッキングトークンの追加

パーソナライゼーションエディターでコードを変更するには、次の手順に従います。

_&#x200B;**ジャーニー管理/キャンペーン**&#x200B;_ に移動します

適切なキャンペーンを開き、「_&#x200B;**キャンペーンを停止**&#x200B;_」ボタンをクリックしてキャンペーンを停止します。

停止したキャンペーンを開き、「_&#x200B;**キャンペーンを変更**&#x200B;_」ボタンをクリックします。

「_&#x200B;**コンテンツ**&#x200B;_」タブをクリックし、「_&#x200B;**コードを編集**&#x200B;_」ボタンをクリックして、パーソナライゼーションエディターを開きます。

スクリーンショットに示すように、div に 2 つの新しいデータ属性を追加します。
![tracking-token](assets/offer-item-with-tracking-code.png)

trackingToken と ItemID を追加するには、左側のナビゲーションで「決定ポリシー」アイコンをクリックし、決定ツリーをドリルダウンして、itemID と trackingToken を選択します。
![tracking-token](assets/insert-tracking-token.png)

これにより、レンダリングされた各オファーにデータトラッキングトークンが含まれます。これは、正確なインプレッションおよびクリックイベントの追跡に不可欠です。

変更を保存し、キャンペーンをアクティブ化します。
