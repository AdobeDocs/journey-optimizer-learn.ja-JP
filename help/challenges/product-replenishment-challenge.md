---
title: 製品補充の課題
description: セグメントの作成とスキルのテストについて学習した内容を適用します。
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 2bddc86066f265cda1d2063db8eb37c9f211eb76
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 91%

---

# 製品補充の課題

| 課題 | 製品補充 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=ja)</li><li> [HTML メールコンテンツの読み込みと作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=ja)</li><li>[ユースケース - セグメントの読み取り](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=ja)</li> |
| ダウンロードするアセット | [季節ごとのコレクションのメールファイル](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## ストーリー

Luma の web サイトを参照する際、顧客は興味のある製品をウィッシュリストに追加できます。これにより、Luma は、ターゲットを絞ったマーケティングメッセージと製品に関する情報を顧客に送信できます。

## 課題

Luma は、Journey Optimizer でジャーニーを実装して、以前は在庫切れだったアイテムをウィッシュリストに持っている顧客に、このアイテムが再入荷したときに通知するように依頼します。

>[!BEGINTABS]

>[!TAB タスク]

## 1.セグメントを定義 — 在庫切れのウィッシュリスト項目

製品が再入荷されたときに潜在的な興味のある顧客をターゲットにするには、顧客で構成されるセグメントを作成します:

* 1 つ以上の項目をウィッシュリストに追加したユーザー ( イベントタイプを使用： [!UICONTROL コマース後のために保存])
* 過去 3 か月以内に在庫切れになったアイテム（使用在庫数 = 0）
* および、それ以来アイテムを購入していない。

>[!TIP]
>SKU が&#x200B;*後で購入するために保存イベント*&#x200B;の SKU と一致するすべての購入イベントタイプを除外します。フィールドは、 *変数を参照* 」セクションに入力します。

このセグメントに名前を付ける： `Out-of-stock-Wishlist`


### 2.ジャーニーの作成 — 製品在庫通知

以前に在庫切れだったアイテムが再入荷したら、在庫切れのアイテムを追加した顧客に、アイテムが再入荷したので買い物を開始するように通知します。

1. ジャーニーを呼び出す： `Product Restock`
2. 製品が再入荷したときにジャーニーをトリガーする必要があります
3. *Luma-製品補充*&#x200B;メールを送信します
4. 在庫切れのアイテムをウィッシュリストに追加した顧客

>[!TAB 成功基準]

ジャーニーをテストします。

1. セグメントの選定イベントに名前空間 = メールがあることを確認してください
1. デフォルトのメールパラメーターを上書きし、独自のメールアドレスに設定します（手順については、メール #1 を参照）
1. ジャーニーをテストモードに設定
1. イベントのトリガー - 次のデータを入力します。

   * 説明：高額なマシンや高価な会費は必要ありません - Harmony Lumaflex Strength Band Kit だけあれば、素晴らしいワークアウトを実現できます。このキットには、筋肉の強化や引き締めエクササイズに必要な機能がすべて揃っています。
   * 名前：Harmony Lumaflex Strength Band Kit
   * 価格：22
   * 製品 ID：24-UG03
   * 製品画像 URL：https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * 在庫イベントタイプ：再在庫
   * プロファイル識別子：Jenna_Palmer9530@emailsim.io

Jenna の製品詳細とパーソナライゼーションを記載した「Luma メール製品補充」のメールが届きます。

>[!TAB 作業内容の確認]

セグメントは、次のようになります。

![セグメント - 在庫切れのウィッシュリストアイテム](/help/challenges/assets/C1-S2.png)




ジャーニーは次のようになります。

![製品補充ジャーニー](/help/challenges/assets/c3-j3-journey.png)

条件：ウィッシュリスト内

![条件 - ウィッシュリスト内](/help/challenges/assets/c3-j3-condition.png)

条件コード：

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```


>[!TIP]
> * *変数を参照*&#x200B;セクションの「後で購入するために保存」の下にある SKU を選択します。
> * 「後で購入するために保存」の下にある SKU をイベントフィールドにドロップする際に、比較オプションを使用します


セグメントを編集画面の右下隅のイベントの下にあるコードを確認します。コードは、次のようになります。

コード：
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

>[!ENDTABS]

### メールの作成 - Luma 製品補充

在庫切れのアイテムを追加した顧客に、そのアイテムが再入荷したので今すぐ買い物を開始するように通知します。



>[!TIP]
>
> 既存のビジネスイベントを使用している。再入荷 SKU が後で保存する（任意の）イベントタイプに含まれていることを確認する条件を追加する必要があります。




