---
title: AEPでの XDM スキーマ、データセット、データストリームの設定
description: XDM スキーマ、データセット、データストリームの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: 0efa418a-5b4f-4012-a6fc-afaa34a59285
source-git-commit: 15b2379c251ed0d7583a01fb6af67815322456cf
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# AEPでの XDM スキーマ、データセット、データストリームの設定

## XDM スキーマの作成

* Adobe Experience Platformにログインします
* データ管理/ スキーマ / スキーマを作成

* _Financial Advisors_ という XDM イベントベースのスキーマを作成します。 スキーマの作成に詳しくない場合は、この [ ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) に従ってください。

* 次の構造をスキーマに追加します。 PreferredFinancialInstrument 要素には、Stock、Bonds、CD に対するユーザーの環境設定が格納されます。 **__techmarketingdemos_**はテナント ID で、お使いの環境で異なります。
  ![xdm-schema](assets/xdm-schema.png)

* PreferredFinancialInstrument 要素には、次のように定義された列挙値があります
  ![enum-values](assets/enum-values.png)

* スキーマがプロファイルに対して有効になっていることを確認します。

## スキーマに基づくデータセットの作成

**Adobe Experience Platform（AEP）のデータセット）**、定義済みの XDM スキーマに基づいてデータを取り込み、保存およびアクティブ化するために使用される構造化ストレージコンテナです。


* データ管理/ データセット / データセットを作成
* 前の手順で作成した XDM スキーマに基づいて、_Financial Advisors データセット_ Financial Advisors データセット）を作成します。

* データセットでプロファイルが有効になっていることを確認します

## データストリームの作成

Adobe Experience Platformのデータストリームは、web サイトやアプリをAdobe サービスに接続する安全なパイプライン（またはハイウェイ）のようなもので、データの流入と、パーソナライズされたコンテンツの戻りを可能にします。

* データ収集/データストリームを選択し、「新規データストリーム」をクリックします。 データストリームに「Financial Advisors DataStream _という名前を付け_

* 以下のスクリーンショットに示すように、次の詳細を入力します
  ![datastream](assets/datastream.png)
* 「保存」をクリックしてから「マッピングを追加」をクリックし、Adobe Experience Platform サービスとイベントデータセットを追加します（下図を参照）
  ![datastream-mapping](assets/datastream-service.png)

* 適切な（以前に作成した）イベントデータセットを選択します。

* データストリームの保存

