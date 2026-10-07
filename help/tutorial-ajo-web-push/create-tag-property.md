---
title: Create Tag プロパティ
description: タグプロパティは、Web SDKを介してブラウザーからAEPにデータを送信します。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-20879
exl-id: 108de002-f033-4b88-bee5-2b50463c345c
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%
---
# Create Tag プロパティ

このチュートリアルの第2部では、カスタム price.drop イベントを手動で送信することで、プッシュ通知をリアルタイムでトリガーする方法について説明します。 このアプローチでは、AEP Data Collection （Tags）を使用して、web ページからイベントを取得し、Adobe Experience Platformに送信します。 イベントが取り込まれると、Adobe Journey Optimizerでジャーニーがトリガーされ、ユーザーのアクションやビジネスイベントにもとづいてプッシュ通知をオンデマンドで送信できます。

このプロパティは、チュートリアルの前に作成した`WebPushDataStream`に接続されているAEP Web SDKで設定されます。 タグプロパティは、Adobe データレイヤーの`price.drop` イベントをリッスンし、ProductListItems データ要素を更新して、関連する製品の詳細をマッピングします。 データが準備されると、タグプロパティのルールが実行され、Web SDKを介してprice.drop イベントがAEPに送信されます。 このイベントは、Adobe Journey Optimizerのジャーニーの出発点となり、値下がりにもとづいてプッシュ通知を即座に配信することができます。

## タグ要素

ProductListItems：製品の詳細を保持

![tag-elements](assets/product-list-items-element.png)

`schemaForPushNotification`へのxdmvariable マッピング

![xdm-variable](assets/xdmvariable-data-element.png)

## ルールを作成

price.drop イベントを聴く
![data-pushed-event](assets/tag-rule-event.png)

更新変数を使用してproductListItemsを更新する
![update-variable](assets/update-variable.png)
最後に、更新されたxdmvariableを使用してprice.drop イベントをAEPに送信します
![send-event](assets/send-event.png)

次のJavaScript コードは、web ページからAEP タグにprice.drop イベントを送信します

```javascript
 <script>
      window.adobeDataLayer.push({
        event: "price.drop",
        productListItems: productListItems
      });
  </script>
```
