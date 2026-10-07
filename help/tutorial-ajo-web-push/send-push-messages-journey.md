---
title: ジャーニーでのプッシュメッセージの送信
description: Adobe Journey Optimizerの頻度キャッピングは、個々のオファーレベルで適用され、オファーインプレッションとクリックイベントの両方を取得する必要があります。 そのためには、Adobe Web SDKを使用してトラッキング decisioning.propositionDisplayおよびdecisioning.propositionInteract イベントを作成し、Adobe Experience Platformで更新されたXDM Experience Event スキーマにマッピングする必要があります。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%
---
# ジャーニーでのプッシュメッセージの送信

値下げイベントにもとづくジャーニーをトリガーすることで、リアルタイムで行動主導型のユーザーエンゲージメントを可能にします。 実際のシナリオでは、通常、製品の価格が更新された際に、バックエンドの価格設定システムからイベントが発生します。 このチュートリアルでは、名前やSKUなどの商品詳細を含むAEP タグを使用して、Adobe データレイヤーを介してカスタム price.drop イベントを送信することで、その動作をシミュレートします。 このイベントはAdobe Experience Platformに取り込まれ、Adobe Journey Optimizerのジャーニーのエントリトリガーとして使用されます。 ジャーニーを受信したら、パーソナライズされたプッシュ通知をすぐに対象顧客に送信し、価格低下を通知してタイムリーな対応を促すことができます。

カスタムイベントを使用してジャーニーをトリガーするには、次の手順を実行します

## Journey Optimizerでのカスタムイベントの作成

Adobe Journey Optimizerにログインし、Administration → Configurations → Eventsに移動し、「Create Event」を選択します。 PriceDropEventという名前の新しいイベントを作成し、チュートリアルの前に作成したイベントスキーマ SchemaForPushNotificationに関連付けます。 参照画像に示すように、イベントプロパティが設定されていることを確認します。

![event-properties](assets/price-drop-event.png)

スキーマから、必須フィールドを選択して、パーソナライゼーションに使用できるようにします。 具体的には、ProductListItems オブジェクトの`Name`と`SKU`と、identityMapの識別子を含めます。 これらのフィールドはパーソナライゼーションエディター内でアクセスでき、製品とユーザーのコンテキストに基づいてプッシュ通知メッセージを動的に構成できます。

## タグプロパティの作成

このプロパティは、チュートリアルの前に作成したWebPushDataStreamに接続されているAEP Web SDKで設定されます。 タグプロパティは、Adobe データレイヤーのprice.drop イベントをリッスンし、ProductListItems データ要素を更新して、関連する製品の詳細をマッピングします。 データが準備されると、タグプロパティのルールが実行され、Web SDKを介してprice.drop イベントがAEPに送信されます。 このイベントは、Adobe Journey Optimizerのジャーニーの出発点となり、値下がりにもとづいてプッシュ通知を即座に配信することができます。



