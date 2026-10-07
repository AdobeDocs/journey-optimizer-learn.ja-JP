---
title: AEPでのXDM スキーマ、データセットおよびデータストリームの設定
description: XDM スキーマ、データセットおよびデータストリームの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 8bb85ba7-3c50-4596-88f8-e112c48a8253
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
source-wordcount: '299'
ht-degree: 0%
---
# AEPでのXDM スキーマ、データセットおよびデータストリームの設定

## XDM スキーマの作成

Web ページでAdobe Experience Platform Web SDK（Alloy.js）を使用するには、XDM イベントスキーマにマッピングされたデータストリームにAEP タグを関連付ける必要があります。 Web SDK（alloy.sendEvent）は、データをExperience EventsとしてAEPに送信します。これは、XDM ExperienceEvent クラスに基づくXDM スキーマに準拠する必要があります。

XDM スキーマを作成するには

* Adobe Experience Platformにログインします
* データ管理/スキーマ/スキーマの作成

* **_Financial Advisors_**&#x200B;という名前のXDM イベントベースのスキーマを作成します。 スキーマの作成に慣れていない場合は、この[&#x200B; ドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/create-schema-ui)に従ってください


* プロファイルでスキーマが有効になっていることを確認します。

## スキーマに基づくデータセットの作成

Adobe Experience Platform （AEP） **の** データセットは、定義されたXDM スキーマに基づいてデータを取り込み、保存、アクティブ化するために使用される構造化ストレージコンテナです。


* データ管理 – > データセット -> データセットの作成
* 前の手順で作成したXDM スキーマ（Financial Advisors）に基づいて、**_Financial Advisors データセット_**&#x200B;という名前のデータセットを作成します。

* プロファイルでデータセットが有効になっていることを確認します

## データストリームの作成

Adobe Experience Platformのデータストリームは、web サイトやアプリとAdobe サービスを結ぶ安全なパイプライン（高速道路）のようなもので、データを流し込み、パーソナライズされたコンテンツを元に戻すことができます。

* データ収集/データストリームに移動し、「新規データストリーム」をクリックします。 データストリーム **_Financial Advisors DataStream_**&#x200B;に名前を付けます

* 以下のスクリーンショットに示すように、次の詳細を入力します
  ![&#x200B; データストリーム &#x200B;](assets/datastream.png)
* 「保存」をクリックし、「マッピングを追加」をクリックして、図のようにAdobe Experience Platform サービスとイベントデータセットを追加します
  ![&#x200B; データストリームマッピング &#x200B;](assets/datastream-service.png)

* 適切なイベントデータセット（以前に作成）を選択します。

* データストリームを保存します。
