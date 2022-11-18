---
title: イベントの設定
description: Journey Optimizerの課題を解決するために必要な 3 つのイベントを設定
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
source-git-commit: 93c5191d9bc0e5cc81d5892251df73251e6c6ea7
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 10%

---


# イベントの設定

このセクションでは、 [Journey Optimizerの課題](/help/challenges/introduction-and-prerequisites.md).

ビデオを見る [イベントを作成](/help/set-up-journeys/create-events.md) イベントの作成方法に関するガイダンスが必要です。

## Luma オンライン購入イベントの作成

1. 左側のナビゲーションから、に移動します。 [!UICONTROL 管理] を選択し、 *[!UICONTROL 設定]*
1. 次の [!UICONTROL ダッシュボード]を選択します。 *[!UICONTROL 管理*]* イベント

![イベントの管理](assets/create-events.png)

1. クリック *[!UICONTROL イベントを作成]*
1. イベントの詳細とパラメーターを入力します。

   | [!UICONTROL パラメーター] | [!UICONTROL 値] |
   |-------------|-----------|
   | [!UICONTROL 名前] | `LumaOnlinePurchase` |
   | [!UICONTROL タイプ] | [!UICONTROL 単一] |
   | [!UICONTROL イベント ID タイプ] | [!UICONTROL ルールベース] |
   | [!UICONTROL スキーマ] | Luma 製品インタラクション |
   | [!UICONTROL フィールド] | EventType <br>Order.priceTotal<br>purchaseOrderNumber<br>productListItems.quantity<br><b>製品リスト項目で、「Luma 製品」>「_」*[!DNL yourOrganizationID]* > 製品：</b> <br> 名前<br>価格<br>ProductImageURL<br>ProductURL |

1. を [!UICONTROL イベント ID 条件]: **[!DNL LumaOnlinePurchase.eventType is commerce.purchases]**

   1. 鉛筆アイコンを選択してフィールドを編集します
   2. の [!UICONTROL イベント ID 条件の追加] モーダルを表示し、ドラッグ&amp;ドロップします。 `eventType` キャンバスに
   3. 選択 `commerce.purchases`
   4. キャンバスで「 ok 」を選択します。
   5. モーダルで「 ok 」を選択します。

![イベント条件を追加](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. 選択 [!UICONTROL 名前空間]: `Email(Email)`

1. 「**[!UICONTROL 保存]**」を選択します。

## 作成 *[!DNL Luma Wishlist Add]* イベント

| [!UICONTROL パラメーター] | [!UICONTROL 値] |
|-------------|-----------|
| [!UICONTROL 名前] | `LumaWishlistAdd` |
| [!UICONTROL タイプ] | [!UICONTROL 単一] |
| [!UICONTROL イベント ID タイプ] | [!UICONTROL ルールベース] |
| [!UICONTROL スキーマ] | `Luma Product Interactions` |
| [!UICONTROL フィールド] | EventType<br>productListItem.quantity<br><b>製品リスト項目で、「Luma 製品」>「_」*[!DNL yourOrganizationID]* > 製品：</b> <br>名前<br>価格<br> ProductImageURL<br>ProductURL |
| [!UICONTROL 条件] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL 名前空間] | 電子メール（電子メール） |

## 作成*[!DNL Luma Product Restock] イベント

| [!UICONTROL パラメーター] | [!UICONTROL 値] |
|-------------|-----------|
| [!UICONTROL 名前] | `LumaProductRestock` |
| [!UICONTROL タイプ] | [!UICONTROL ビジネス] |
| [!UICONTROL スキーマ] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL フィールド] | productID <br> stockEventType<br><b>製品/Luma 製品/ *[!DNL yourOrganizationID]* > 製品：</b> <br>名前<br>価格<br> ProductImageURL<br>説明 |
| [!UICONTROL 条件] | LumaProductRestock。_`your organization's ID`.inventoryEvent.stockEventType は restock です |

## これで完了です

サンドボックスを使用する準備が整いました。
