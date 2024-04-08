---
title: レッスン 4：プッシュキャンペーンの作成
description: プロファイルデータを確認し、Journey Optimizerでオーディエンスにプッシュ通知を作成して送信する方法を学びます。
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: befde57252ebc12c5d6df31fde8078e4535d1261
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 2%

---

# レッスン 4：プッシュキャンペーンの作成

前の演習では、あなたはコーヒー愛好家、Fréscopa の顧客でした。 あなたは彼らのウェブサイトと Fréscopa アプリを通じてブランドとやり取りし、多くのトランザクションメッセージを受信しました。 これらのメッセージは、ユーザーの web サイトやアプリケーションとのやり取りを通じてトリガーされます。

この演習では、マーケターに帽子をかぶせ、Frésopa のマーケティングキャンペーンを実装します。このキャンペーンは、プッシュチャネルを利用して Fréscopa アプリのユーザーをターゲットにします。 プッシュ通知は、アプリを使用していない場合でもアプリのユーザーに情報を提供し続けるためだけでなく、ユーザーをアプリに再び関わらせるためにも使用されます。 目的は、10% の割引を提供することで、お客様にハウスブレンドを購入するように促すことです。

## 学習内容

* プッシュキャンペーンの作成方法を理解する。
* プッシュメッセージのデザイン方法を理解する。

<br>

## 演習 4.1 - プッシュキャンペーンの作成

この演習では、プッシュキャンペーンを作成し、プッシュ通知をデザインおよびカスタマイズして、プッシュ通知を独自のデバイスに送信します。

1. Journey Optimizerの左側のナビゲーションの **[!UICONTROL ジャーニー管理]** セクションで選択 **キャンペーン**.

1. クリック **[!UICONTROL キャンペーンを作成]**.

   ![キャンペーンを作成](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. 日 **[!UICONTROL キャンペーンを作成]** ページ （内）  **[!UICONTROL アクション]** セクションで、 **[!UICONTROL プッシュ通知]** チェックボックスをオンにします。

1. から **[!UICONTROL アプリサーフェス]** ドロップダウン、選択 *[!DNL Frecopa-Push]*.

1. クリック **[!UICONTROL 作成]** （プッシュキャンペーンの作成用）。

   ![アプリサーフェス](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>これで、キャンペーンのプロパティページが表示されます。
> ![キャンペーンプロパティ](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## 演習 4.2 - キャンペーンの設定

このページでは、キャンペーンのプロパティ、オーディエンス、アクションおよびスケジュールを設定します。

### 4.2.1 [!UICONTROL プロパティセクション]

キャンペーンに名前を付けます。 キャンペーンを検索する際にキャンペーンを簡単に見つけられるように、名前はシート番号で始めてください。

例えば、シート番号が 99 の場合： `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL オーディエンスセクション]**

1. 「オーディエンス」セクションで、 **[!UICONTROL オーディエンスを選択]**.

   ![オーディエンスセクション](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. 日 **[!UICONTROL オーディエンスを選択]** 画面で、オーディエンスを検索します。

   **ラボ – シート`your seat number`**

1. オーディエンスを選択し、 **[!UICONTROL 保存]**.

   ![オーディエンスの選択](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 プッシュ通知の内容を編集する

この演習では、プッシュ通知をデザインしカスタマイズします。

1. が含まれる **[!UICONTROL アクション]** セクションで、 **[!UICONTROL コンテンツを編集] ボタン**.

   ![コンテンツを編集ボタン](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. 次の画面で、使用しているモバイルデバイスに応じて、次のどちらかを選択します [!DNL iOS™] または [!DNL Android™] タブをクリックしてコンテンツを設定します。

>[!BEGINTABS]

>[!TAB iOS]

![「iOS」タブ](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![「Android」タブ](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL メッセージを作成] セクション

1. **メッセージを作成します。** 任意のテキストを自由に追加できます。 次のような例を使用できます。

   * タイトル：`Get 10% off today!`
   * 本文： `Today only! Get 10% off on your House Blend coffee purchase!`

     ![メッセージを作成](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 メッセージのクリック時の動作をに変更する **製品ページを開く**

1. が含まれる **[!UICONTROL クリック時の動作]** セクションで選択 **[!UICONTROL ディープリンク]** から **[!UICONTROL 本文クリックの動作]** ドロップダウン。

1. 次の URL をコピーして、にペーストします **URL フィールド**:

   `dxdemo://exoticVibes`

   ![ディープリンク](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 メッセージに画像を追加する

1. が含まれる **[!UICONTROL メディアを追加]** セクションで、をクリック **[!UICONTROL メディアを追加]**.

   ![メディアボタンを追加](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. 日 **[!UICONTROL アセットを選択]** 画面の左側のナビゲーションで、 **Fréscopa フォルダー** そのフォルダーから画像を選択します。

   例：`HouseBlend.png`

1. 画像をクリックしてから、 **[!UICONTROL を選択] ボタン** プッシュ通知に画像を追加します。

   ![画像を選択](/help/summit/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. プレビュー画面で、 **[!UICONTROL ビューの展開]**.
   > 1. メッセージのプレビュー。
   > <br>
   >
   > ![ビューを展開](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

### ボーナス演習

演習のこの部分を完了しても時間がある場合は、ボーナス演習を試してください。

+++ ボーナス演習

#### 受信者の名を追加して、送信するメッセージをパーソナライズします

1. クリック **パーソナライゼーションダイアログ** 「」の横 **[!UICONTROL 本文]** フィールド。

   ![パーソナライゼーションボタン](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. 日 **パーソナライゼーションダイアログ** 画面で、テキストの名を追加する位置にカーソルを置きます。

1. 必ずを **プロファイル属性** 左側のナビゲーションで選択されます。

   ![プロファイル属性](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. が含まれる **検索フィールド**、次を検索： `first name`.

1. クリック **+** 「」の横 **名（プロファイル属性/人物/姓名）** パーソナライゼーションフィールドをテキストに追加します。

   ![名を検索](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > テキストは次のようになります。
   > 
   >![パーソナライゼーショントークン](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. クリック **[!UICONTROL 保存]** をクリックしてパーソナライゼーションを保存します。


   >[!SUCCESS]
   >
   > 1. プレビュー画面で、 **[!UICONTROL ビューの展開]**.
   > 1. メッセージのプレビュー。
   > 
   > ![ビューを展開](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. レビューとアクティブ化

メッセージの内容に満足している場合は、メッセージをアクティベートできます。

1. クリック **[!UICONTROL アクティブ化するレビュー]**.

   ![「レビューしてアクティブ化」ボタン](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. 日 **[!UICONTROL アクティブ化するレビュー]** 画面、クリック **[!UICONTROL Activate]**.

   ![アクティベートするレビュー画面](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> 日 **キャンペーンの概要ページ**、キャンペーンを見つけて、ステータスを確認します。
>
> ![キャンペーンステータス](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> ステータスが「処理中」から「ライブ」に変わります。この処理には数分かかる場合があります。
> ステータスが完了に変更されたら、次の操作を行います。
>
> ![プッシュの結果](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)

## その他のリソース

**ハウツービデオ：**

* [プッシュキャンペーンの設定と送信](/help/channels/create-a-push-campaign.md)

**製品ドキュメント：**

* [プッシュ通知の基本を学ぶ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/get-started-push)
* [プッシュ通知の作成](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/create-push)
* [プッシュ通知のデザイン](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/design-push)
* [プッシュ通知の確認と送信](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/send-push)
