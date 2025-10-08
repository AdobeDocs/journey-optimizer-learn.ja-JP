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
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '778'
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

1. Journey Optimizerの左側のナビゲーションの「**[!UICONTROL ジャーニー管理]**」セクションで、「**キャンペーン**」を選択します。

1. **[!UICONTROL キャンペーンを作成]** をクリックします。

   ![&#x200B; キャンペーンを作成 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. **[!UICONTROL キャンペーンを作成]** ページの「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL プッシュ通知]**」チェックボックスを選択します。

1. **[!UICONTROL アプリサーフェス]** ドロップダウンから「*[!DNL Frecopa-Push]*」を選択します。

1. 「**[!UICONTROL 作成]**」をクリックして、プッシュキャンペーンを作成します。

   ![&#x200B; アプリサーフェス &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>これで、キャンペーンのプロパティページが表示されます。
>&#x200B;> ![キャンペーンプロパティ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## 演習 4.2 - キャンペーンの設定

このページでは、キャンペーンのプロパティ、オーディエンス、アクションおよびスケジュールを設定します。

### 4.2.1 [!UICONTROL &#x200B; プロパティセクション &#x200B;]

キャンペーンに名前を付けます。 キャンペーンを検索する際にキャンペーンを簡単に見つけられるように、名前はシート番号で始めてください。

例えば、シート番号が 99 の場合：`99 - 10% Discount Campaign` です。

### 4.2.2 **[!UICONTROL オーディエンスセクション]**

1. 「オーディエンス」セクションで、「**[!UICONTROL オーディエンスを選択]**」をクリックします。

   ![&#x200B; オーディエンスセクション &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. **[!UICONTROL オーディエンスを選択]** 画面で、オーディエンスを検索します。

   **Lab - Seat`your seat number`**

1. オーディエンスを選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![&#x200B; オーディエンスの選択 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 プッシュ通知の内容を編集する

この演習では、プッシュ通知をデザインしカスタマイズします。

1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL コンテンツを編集 &#x200B;] ボタンをクリックします**。

   ![&#x200B; コンテンツを編集ボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. 次の画面で、使用しているモバイルデバイスに応じて、「[!DNL iOS™]」または「[!DNL Android™]」タブを選択して、コンテンツを設定します。

>[!BEGINTABS]

>[!TAB iOS]

![&#x200B; 「iOS」タブ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![&#x200B; 「Android」タブ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1[!UICONTROL &#x200B; メッセージを作成 &#x200B;] セクション

1. **メッセージの作成：** 任意のテキストを自由に追加できます。 次のような例を使用できます。

   * タイトル：`Get 10% off today!`
   * 本文：`Today only! Get 10% off on your House Blend coffee purchase!`

     ![&#x200B; メッセージを作成 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 メッセージのクリック時の動作を **製品ページを開く** に変更します

1. 「**[!UICONTROL クリック時の動作]**」セクションで、「**[!UICONTROL 本文のクリック動作]**」ドロップダウンから「**[!UICONTROL ディープリンク]**」を選択します。

1. 次の URL をコピーして **URL フィールド** に貼り付けます。

   `dxdemo://exoticVibes`

   ![&#x200B; ディープリンク &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 メッセージへの画像の追加

1. 「**[!UICONTROL メディアを追加]**」セクションで、「**[!UICONTROL メディアを追加]**」をクリックします。

   ![&#x200B; メディアを追加ボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. **[!UICONTROL Assetsを選択]** 画面の左側のナビゲーションで **Fréscopa フォルダーを開き** そのフォルダーから画像を選択します。

   例：`HouseBlend.png`

1. 画像をクリックし、**[!UICONTROL 選択 &#x200B;] ボタン** をクリックして、プッシュ通知に画像を追加します。

   ![&#x200B; 画像を選択 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. プレビュー画面で、「**[!UICONTROL ビューを展開]**」をクリックします。
   > 1. メッセージのプレビュー。
   > <br>
   >
   > ![&#x200B; ビューを展開 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

### ボーナス演習

演習のこの部分を完了しても時間がある場合は、ボーナス演習を試してください。

+++ ボーナス演習

#### 受信者の名を追加して、送信するメッセージをパーソナライズします

1. **本文** フィールドの横にある **[!UICONTROL パーソナライゼーションダイアログ]** をクリックします。

   ![&#x200B; パーソナライゼーションボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-button.png)

1. **パーソナライゼーションダイアログ** 画面で、テキストの名を追加する位置にカーソルを置きます。

1. 左側のナビゲーションで **プロファイル属性** が選択されていることを確認します。

   ![&#x200B; プロファイル属性 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. **検索フィールド** で、`first name` を検索します。

1. **名（プロファイル属性/ユーザー/姓名）の横にある**+**をクリックして** パーソナライゼーションフィールドをテキストに追加します。

   ![&#x200B; 名を検索 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > テキストは次のようになります。
   > 
   >![Personalization トークン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-token.png)

1. **[!UICONTROL 保存]** をクリックして、パーソナライゼーションを保存します。


   >[!SUCCESS]
   >
   > 1. プレビュー画面で、「**[!UICONTROL ビューを展開]**」をクリックします。
   > 1. メッセージのプレビュー。
   > 
   > ![&#x200B; ビューを展開 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. レビューとアクティブ化

メッセージの内容に満足している場合は、メッセージをアクティベートできます。

1. **[!UICONTROL アクティブ化するレビュー]** をクリックします。

   ![&#x200B; レビューしてアクティブ化ボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. **[!UICONTROL アクティブ化するレビュー]** 画面で、「**[!UICONTROL アクティブ化]**」をクリックします。

   ![&#x200B; アクティブ化するレビュー画面 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> **キャンペーンの概要ページ** で、キャンペーンを見つけて、ステータスを確認します。
>
> ![&#x200B; キャンペーンステータス &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> ステータスが「処理中」から「ライブ」に変わります。この処理には数分かかる場合があります。
> &#x200B;> ステータスが完了に変更されたら、次の操作を行います。
>
> ![&#x200B; プッシュ結果 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-push-notification-result.png)

## その他のリソース

**ビデオガイド：**

* [プッシュキャンペーンの設定と送信](/help/channels/create-a-push-campaign.md)

**製品ドキュメント：**

* [&#x200B; プッシュ通知の概要 &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/get-started-push)
* [プッシュ通知の作成](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/create-push)
* [プッシュ通知のデザイン](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/design-push)
* [&#x200B; プッシュ通知を確認して送信する &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/send-push)
