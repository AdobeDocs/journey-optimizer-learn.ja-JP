---
title: AEPでの XDM スキーマ、データセット、データストリームおよびオーディエンスの設定
description: XDM スキーマ、データセット、データストリームおよびオーディエンスの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 0efa418a-5b4f-4012-a6fc-afaa34a59285
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# AEPでの XDM スキーマ、データセット、データストリームおよびオーディエンスの設定

* Adobe Experience Platformにログインします

* Journey Optimizerで、Financial Advisors という XDM イベントベースのスキーマを作成します。 スキーマの作成に詳しくない場合は、この [ ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) に従ってください。

* 次の構造をスキーマに追加します。 PreferredFinancialInstrument 要素には、株式、債券、CD に対するユーザーの環境設定が格納されます
  ![xdm-schema](assets/xdm-schema.png)

* PreferredFinancialInstrument 要素には、次のように定義された列挙値があります
  ![enum-values](assets/enum-values.png)

* スキーマがプロファイルに対して有効になっていることを確認します。

## スキーマに基づくデータセットの作成

**Adobe Experience Platform（AEP）のデータセット）**、定義済みの XDM スキーマに基づいてデータを取り込み、保存およびアクティブ化するために使用される構造化ストレージコンテナです。

* 前の手順で作成した XDM スキーマに基づいて、_Financial Advisors データセット_ Financial Advisors データセット）を作成します。

* データセットでプロファイルが有効になっていることを確認します

## データストリームの作成

Adobe Experience Platformのデータストリームは、web サイトやアプリをAdobe サービスに接続する安全なパイプライン（またはハイウェイ）のようなもので、データの流入と、パーソナライズされたコンテンツの戻りを可能にします。

* AEP/データストリームに移動し、「新しいデータストリーム」をクリックします。 データストリームに「Financial Advisors DataStream _という名前を付け_

* 以下のスクリーンショットに示すように、次の詳細を入力します
  ![datastream](assets/datastream.png)
* 「保存」をクリックしてから「マッピングを追加」をクリックし、Adobe Experience Platform サービスとイベントデータセットを追加します（下図を参照）
  ![datastream-mapping](assets/datastream-service.png)

* 適切な（以前に作成した）イベントデータセットを選択します。

* データストリームの保存

## オーディエンスを作成

Adobe Experience Platformのオーディエンスは、パーソナライズされたエクスペリエンスを提供するために、アクション、環境設定またはプロファイル情報に基づいて作成されたユーザーグループです。

* 顧客/ オーディエンスに移動します。
* ルールの作成方法を使用したオーディエンスの作成

* イベントスキーマの PreferredFinancialInstrument 要素を使用して、AJOで次の 3 つのオーディエンスを作成します。

   * 株式に関心のあるお客様

   * 社債に関心のあるお客様

   * CD に関心のあるお客様

リアルタイムの選定を行うには、各オーディエンスの評価方法がEdgeに設定されていることを確認します。

次のスクリーンショットは、オーディエンスの作成に役立ちます。

![ オーディエンス ](assets/rule-based-audience.png)

![ イベント ](assets/event-attribute.png)


![ 優先金融商品 ](assets/stock-customers.png)

![ エッジオーディエンス ](assets/audience-edge.png)
