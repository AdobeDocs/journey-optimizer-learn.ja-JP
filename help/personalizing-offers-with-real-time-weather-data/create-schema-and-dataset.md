---
title: AEPでの XDM スキーマ、データセット、データストリームの設定
description: XDM スキーマ、データセット、データストリームの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 1c7fe9e7-ab72-4d7b-960a-512d0e25808b
source-git-commit: 95a8abd08fbf57900870826112b01a8cd375fe96
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# AEPでの XDM スキーマ、データセット、データストリームの設定

## XDM スキーマの作成

Web ページでAdobe Experience Platform Web SDK（Alloy.js）を使用するには、AEP タグを、XDM イベントスキーマにマッピングされるデータストリームに関連付ける必要があります。 Web SDK（alloy.sendEvent）は、データをエクスペリエンスイベントとしてAEPに送信します。これは、XDM ExperienceEvent クラスに基づく XDM スキーマに準拠する必要があります。

XDM スキーマを作成するには

- Adobe Experience Platformにログインします
- _&#x200B;**データ管理/スキーマ/スキーマを作成**&#x200B;_ に移動します。

- **_Weather-Schema_** という XDM イベントベースのスキーマを作成します。 スキーマの作成に詳しくない場合は、この [ ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/create-schema-ui) に従ってください。


- スキーマに、適切なデータタイプを持つ次のフィールドがあることを確認します。

- ![weather-schema](assets/weather-schema.png)

- フィールドグループ _&#x200B;**Web 詳細**&#x200B;_ をスキーマに追加します。 このフィールドグループは、レポート目的で必要です。

## スキーマに基づくデータセットの作成

**Adobe Experience Platform（AEP）のデータセット）**、定義済みの XDM スキーマに基づいてデータを取り込み、保存およびアクティブ化するために使用される構造化ストレージコンテナです。

- _&#x200B;**データ管理/データセット/データセットを作成**&#x200B;_ に移動します。
- 前の手順で作成した XDM スキーマ（**_Weather-Schema_**）に基づいて、_&#x200B;**Weather-schema-dataset**&#x200B;_ というデータセットを作成します。


## データストリームの作成

Adobe Experience Platformのデータストリームは、web サイトやアプリをAdobe サービスに接続する安全なパイプライン（またはハイウェイ）のようなもので、データの流入と、パーソナライズされたコンテンツの戻りを可能にします。

- _&#x200B;**データ収集/データストリーム**&#x200B;_ に移動し、「新しいデータストリーム」をクリックします。 データストリームに「**weather-related-datastream**」という名前を付けます。


- 以下のスクリーンショットに示すように、次の詳細を入力します
  ![datastream](assets/datastream.png)
- 「保存」をクリックし、「マッピングを追加」をクリックして、適切なチェックボックスを選択したAdobe Experience Platform サービスとイベントデータセットを追加します
  ![datastream-mapping](assets/datastream-service.png)

- データストリームを保存します。
