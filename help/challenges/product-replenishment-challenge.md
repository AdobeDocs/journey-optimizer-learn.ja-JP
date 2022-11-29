---
title: 製品補充の課題
description: セグメントの作成とスキルのテストについて学んだことを適用します。
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# 製品補充の課題

| 課題 | 製品補充 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=en)</li><li> [HTML 電子メールコンテンツの読み込みと作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=en)</li><li>[ユースケース - セグメントの読み取り](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| ダウンロードするアセット | [季節ごとのコレクションの電子メールファイル](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## 物語

Luma の Web サイトを参照する際、顧客は興味のある製品をウィッシュリストに追加できます。 これにより、Luma は、ターゲットを絞ったマーケティングメッセージと製品に関する情報を顧客に送信できます。

## 課題

Luma は、以前に在庫切れだったアイテムを持つ顧客に、そのアイテムが在庫に戻ったときにその顧客に通知するジャーニーをJourney Optimizerで実装するように求めます。

## セグメントの定義 — 在庫切れのウィッシュリスト項目

製品の再在庫時に潜在的な興味を持つ顧客をターゲットにするには、顧客で構成されるセグメントを作成します

* 1 つ以上の項目をウィッシュリストに追加したユーザー ( イベントタイプを使用： [!UICONTROL コマース後のために保存])
* それは **在庫切れ** 過去 3 か月間（在庫数= 0 を使用）
* そして、その品目を購入してからではありません。

このセグメントに名前を付ける： *お名前 — 在庫切れ — ウィッシュリスト*

+++**作業内容を確認する**

セグメントは次のようになります。

![セグメント — 在庫切れのウィッシュリスト項目](/help/challenges/assets/C1-S2.png)

過去 3 か月間に在庫切れとなったウィッシュリストに品目を追加したお客様：

* イベント：後で使用するために保存
   * 少なくとも 1 つを含める
   * ここで、在庫数量は 0 です。

およびは、次の品目を購入した後はありません。

* SKU が SKU と一致する購入イベントタイプをすべて **後で使用するために保存するイベント**.

>[!TIP]
> * 「後で使用するために保存」で SKU を選択します ( *変数を参照* セクション
> * SKU を「後で保存するために保存」の下にイベントフィールドにドロップする場合は、比較オプションを使用します


セグメントを編集画面の右下隅にある「イベント」で、コードを確認します。 コードは次のようになります。

コード:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### 電子メールの作成 — Luma-Product 補充

買い物を開始する呼び出しで在庫切れの品目を追加した顧客に、その品目が在庫に戻ったことを通知します。

### ジャーニーの作成 — 製品在庫通知

以前に在庫切れになった品目が再び在庫に戻ったら、買い物を開始する呼び出しで在庫切れ品目を追加した顧客に、その品目が在庫に戻ったことを通知します。

1. 「your name_Luma - Product Restock」という名前のジャーニーを作成します。
1. 製品が在庫に戻ったら、ジャーニーをトリガーする必要があります
1. を *Luma-Product 補充* 電子メール送信先
1. 在庫切れの際にこの項目をウィッシュリストに追加したユーザー

>[!TIP]
>
> 既存のビジネスイベントを使用します。 後で保存する際に、在庫 SKU が（任意の）イベントタイプに含まれていることを確認する条件を追加する必要があります。

+++**達成基準**

ジャーニーのテスト:

1. セグメントの選定イベントに名前空間= E メールが含まれていることを確認します。
1. デフォルトの E メールパラメーターを上書きし、独自の E メールアドレスに設定します ( 手順については、 E メール#1を参照 )
1. ジャーニーをテストモードに設定
1. トリガーとイベント — 次のデータを入力します。

   * 説明：ファンシーマシンと高価なメンバーシップを忘れる — ハーモニー Lumaflex Strength Band Kit は、素晴らしいトレーニングに必要なすべてです。 このキットは、強化と調色の練習の範囲に必要なすべてを備えています。
   * 名前：ハーモニールマフレックス強度バンドキット
   * 価格：22
   * 製品 ID:24-UG03
   * 製品画像 URL:https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU:24-UG03
   * 在庫イベントタイプ：再在庫
   * プロファイル識別子：Jenna_Palmer9530@emailsim.io

Jenna の製品詳細とパーソナライゼーションを記載した「Luma Email Product Replisation」E メールが届きます。

+++

+++**作業内容を確認する**

ジャーニーは次のようになります。

![製品補充ジャーニー](/help/challenges/assets/c3-j3-journey.png)

条件：ウィッシュリスト内

![条件 — ウィッシュリスト内](/help/challenges/assets/c3-j3-condition.png)

条件コード：

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
