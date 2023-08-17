---
title: イベントの設定
description: Journey Optimizer の実習課題に必要な 3 つのイベントの設定
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: df055830da42b94d751890af6c19074ddfea2237
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 100%

---

# イベントの設定

この節では、[Journey Optimizer の課題](/help/challenges/introduction-and-prerequisites.md)の実習に必要な 3 つのイベントを設定します。

次のビデオでは、イベントの作成方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on)

## Luma オンライン購入イベントの作成

このイベントを使用すると、Journey Optimizer は、ユーザーが luma 製品をオンラインで購入したときに情報を受信します。

1. 次のパラメーターを持つイベントを作成します。

   | [!UICONTROL パラメーター] | [!UICONTROL 値] |
   |-------------|-----------|
   | [!UICONTROL 名前] | `LumaOnlinePurchase` |
   | [!UICONTROL タイプ] | [!UICONTROL 単一] |
   | [!UICONTROL イベント ID のタイプ] | [!UICONTROL ルールベース] |
   | [!UICONTROL スキーマ] | `Luma Web Events Schema` |
   | [!UICONTROL フィールド] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. `LumaOnlinePurchase.eventType is commerce.purchases` という[!UICONTROL イベント ID 条件]を追加します。

   1. 鉛筆アイコンを選択して、フィールドを編集します。

   1. **[!UICONTROL イベント ID 条件を追加]**&#x200B;モーダルで、`eventType` をキャンバスにドラッグ＆ドロップします。
   1. `commerce.purchases` を選択します。
   1. キャンバスで「**[!UICONTROL OK]**」を選択します。
   1. モーダルで「**[!UICONTROL OK]**」を選択します。

   ![イベント条件の追加](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. [!UICONTROL 名前空間] `Luma CRM ID (lumaCrmId)` を選択します。

1. 「**[!UICONTROL 保存]**」を選択します。

## *[!DNL Luma Product Restock]* イベントの作成

| [!UICONTROL パラメーター] | [!UICONTROL 値] |
|-------------|-----------|
| [!UICONTROL 名前] | `LumaProductRestock` |
| [!UICONTROL タイプ] | [!UICONTROL ビジネス] |
| [!UICONTROL スキーマ] | [!DNL Luma Product Inventory Event Schema] |
| [!UICONTROL フィールド] | SKU <br> stockEventType<br><b>LumaProductCatalogSchema._yourOrganizationID.product :</b> <br>名前<br>価格<br> ImageURL<br>説明 |
| [!UICONTROL 条件] | LumaProductRestock。_`your organization's ID`.inventoryEvent.stockEventType は restock です |

おめでとうございます。これで、サンドボックスを使用する準備が整いました。
