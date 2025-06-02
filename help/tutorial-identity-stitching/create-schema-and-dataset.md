---
title: AEPでの XDM スキーマ、データセット、データストリームの設定
description: XDM スキーマ、データセット、データストリームの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-18089
source-git-commit: 860f4fa4f6b491f3327776ba372bd5fa20e5d5d3
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# AEPでの XDM スキーマ、データセット、データストリームの設定

## XDM スキーマの作成

Web ページでAdobe Experience Platform Web SDK（Alloy.js）を使用するには、AEP タグを、XDM イベントスキーマにマッピングされるデータストリームに関連付ける必要があります。 Web SDK（alloy.sendEvent）は、データをエクスペリエンスイベントとしてAEPに送信します。これは、XDM ExperienceEvent クラスに基づく XDM スキーマに準拠する必要があります。

XDM スキーマを作成するには

* Adobe Experience Platformにログインします
* データ管理/ スキーマ / スキーマを作成

* **_Financial Advisors_** という XDM イベントベースのスキーマを作成します。 スキーマの作成に詳しくない場合は、この [ ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/create-schema-ui) に従ってください。


* スキーマがプロファイルに対して有効になっていることを確認します。

## スキーマに基づくデータセットの作成

**Adobe Experience Platform（AEP）のデータセット）**、定義済みの XDM スキーマに基づいてデータを取り込み、保存およびアクティブ化するために使用される構造化ストレージコンテナです。


* データ管理/ データセット / データセットを作成
* 前の手順で作成した XDM スキーマに基づいて、**_Financial Advisors データセット_** Financial Advisors データセット）を作成します。

* データセットでプロファイルが有効になっていることを確認します

## データストリームの作成

Adobe Experience Platformのデータストリームは、web サイトやアプリをAdobe サービスに接続する安全なパイプライン（またはハイウェイ）のようなもので、データの流入と、パーソナライズされたコンテンツの戻りを可能にします。

* データ収集/データストリームに移動し、「新規データストリーム」をクリックします。 データストリームに「Financial Advisors DataStream **_という名前を付け_**

* 以下のスクリーンショットに示すように、次の詳細を入力します
  ![datastream](assets/datastream.png)
* 「保存」をクリックしてから「マッピングを追加」をクリックし、Adobe Experience Platform サービスとイベントデータセットを追加します（下図を参照）
  ![datastream-mapping](assets/datastream-service.png)

* 適切な（以前に作成した）イベントデータセットを選択します。

* データストリームを保存します。

