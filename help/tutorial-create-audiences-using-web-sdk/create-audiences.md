---
title: Adobe Journey Optimizerでのオーディエンスの作成
description: AJOでターゲットオーディエンスを定義および構築し、パーソナライズされたカスタマージャーニーとリアルタイムの意思決定を強化する方法をご確認ください
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30
jira: KT-17923
exl-id: d90f1868-0514-49b2-832d-82460883b6e4
source-git-commit: 073d4a99b74a0bc341117e83a66747aed02648bf
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%
---
# Adobe Journey Optimizerでのオーディエンスの作成


Adobe Experience Platformの「オーディエンス」とは、パーソナライズされたエクスペリエンスを提供するために、ユーザーの行動、好み、プロファイル情報にもとづいて作成されたユーザーグループのことです。

* Journey Optimizerにログインします
* 顧客/ オーディエンス / オーディエンスの作成に移動します
* ルールを作成メソッドを使用したオーディエンスの作成

  ![オーディエンス](assets/rule-based-audience.png)

* 次の3つのオーディエンスを作成します

  * ストックに興味のある顧客

  * 債券に興味のある顧客

  * CDに興味のあるユーザー


* リアルタイムの選定のために、各オーディエンスの評価方法が&#x200B;_&#x200B;**Edge**&#x200B;_に設定されていることを確認します。
  ![edge-audience](assets/audience-edge.png)

* 「PreferredFinancialInstrument」フィールドを使用して、選択した投資関心（株、債券、CDなど）に基づいてユーザーをセグメント化します

![&#x200B; イベント &#x200B;](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>&#x200B;>「イベント」タブにPreferredFinancialInstrument フィールドが表示されない場合は、設定アイコンをクリックし、「完全なXDM スキーマを表示」を切り替えます。



![toggle-full-xdm-schema](assets/show-custom-fields.png)
