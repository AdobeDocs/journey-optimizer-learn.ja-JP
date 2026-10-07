---
title: AEPでのXDM スキーマ、データセットおよびデータストリームの設定
description: XDM スキーマ、データセットおよびデータストリームの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: 0efa418a-5b4f-4012-a6fc-afaa34a59285
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
source-wordcount: '284'
ht-degree: 0%
---
# AEPでのXDM スキーマ、データセットおよびデータストリームの設定

## XDM スキーマの作成

* Adobe Experience Platformにログインします
* データ管理/スキーマ/スキーマの作成

* _Financial Advisors_&#x200B;という名前のXDM イベントベースのスキーマを作成します。 スキーマの作成に慣れていない場合は、この[&#x200B; ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)に従ってください

* スキーマに次の構造を追加します。 PreferredFinancialInstrument要素には、ユーザーのStocks、Bonds、CDに対する好みが格納されます。 **__techmarketingdemos_**&#x200B;はテナント IDであり、環境によって異なります。
  ![xdm-schema](assets/xdm-schema.png)

* PreferredFinancialInstrument要素には、次のように定義された列挙値があります
  ![enum-values](assets/enum-values.png)

* プロファイルでスキーマが有効になっていることを確認します。

## スキーマに基づくデータセットの作成

Adobe Experience Platform （AEP） **の** データセットは、定義されたXDM スキーマに基づいてデータを取り込み、保存、アクティブ化するために使用される構造化ストレージコンテナです。


* データ管理 – > データセット -> データセットの作成
* 前の手順で作成したXDM スキーマ（Financial Advisors）に基づいて、_Financial Advisors データセット_&#x200B;という名前のデータセットを作成します。

* プロファイルでデータセットが有効になっていることを確認します

## データストリームの作成

Adobe Experience Platformのデータストリームは、web サイトやアプリとAdobe サービスを結ぶ安全なパイプライン（高速道路）のようなもので、データを流し込み、パーソナライズされたコンテンツを元に戻すことができます。

* データ収集/データストリームを選択し、「新規データストリーム」をクリックします。 データストリーム _Financial Advisors DataStream_&#x200B;に名前を付けます

* 以下のスクリーンショットに示すように、次の詳細を入力します
  ![&#x200B; データストリーム &#x200B;](assets/datastream.png)
* 「保存」をクリックし、「マッピングを追加」をクリックして、図のようにAdobe Experience Platform サービスとイベントデータセットを追加します
  ![&#x200B; データストリームマッピング &#x200B;](assets/datastream-service.png)

* 適切なイベントデータセット（以前に作成）を選択します。

* データストリームを保存

