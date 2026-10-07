---
title: Adobe Journey Optimizerでのオーディエンスの作成
description: AJOでターゲットオーディエンスを定義および構築し、パーソナライズされたカスタマージャーニーとリアルタイムの意思決定を強化する方法をご確認ください
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: d90f1868-0514-49b2-832d-82460883b6e4
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
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


* リアルタイムの選定のために、各オーディエンスの評価方法が&#x200B;_**Edge**_に設定されていることを確認します。
  ![edge-audience](assets/audience-edge.png)

* 「PreferredFinancialInstrument」フィールドを使用して、選択した投資関心（株、債券、CDなど）に基づいてユーザーをセグメント化します

![ イベント ](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>>「イベント」タブにPreferredFinancialInstrument フィールドが表示されない場合は、設定アイコンをクリックし、「完全なXDM スキーマを表示」を切り替えます。



![toggle-full-xdm-schema](assets/show-custom-fields.png)
