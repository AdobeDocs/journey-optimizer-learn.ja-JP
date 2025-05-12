---
title: Adobe Journey Optimizerでのオーディエンスの作成
description: パーソナライズされたカスタマージャーニーとリアルタイムの意思決定を強化するために、AJOでターゲットオーディエンスを定義および構築する方法について説明します
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: ba83be3caf214d2daaa8c99556d246686ff3f0cb
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Adobe Journey Optimizerでのオーディエンスの作成


Adobe Experience Platformのオーディエンスは、パーソナライズされたエクスペリエンスを提供するために、アクション、環境設定またはプロファイル情報に基づいて作成されたユーザーグループです。

* Journey Optimizerにログインします
* 顧客/ オーディエンス / オーディエンスを作成に移動します。
* ルールの作成方法を使用したオーディエンスの作成

  ![ オーディエンス ](assets/rule-based-audience.png)

* 次の 3 つのオーディエンスを作成します

   * 株式に関心のあるお客様

   * 社債に関心のあるお客様

   * CD に関心のあるお客様


* リアルタイムで選定するには、各オーディエンスの評価方法が **_0&rbrace;Edge&rbrace; に設定されていることを確認します。_**
  ![ エッジオーディエンス ](assets/audience-edge.png)

* PreferredFinancialInstrument フィールドを使用して、選択した投資関心（株式、債券、CD など）に基づいてユーザーをセグメント化します

![ イベント ](assets/event-attribute.png)

![ 優先金融商品 ](assets/stock-customers.png)




>[!NOTE]
>
>&#x200B;>「イベント」タブに「PreferredFinancialInstrument」フィールドが表示されない場合は、設定アイコンをクリックし、「完全な XDM スキーマを表示」を切り替えます。



![toggle-full-xdm-schema](assets/show-custom-fields.png)


