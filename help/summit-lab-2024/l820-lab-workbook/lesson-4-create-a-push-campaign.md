---
title: レッスン 4 - プッシュキャンペーンの作成
description: プロファイルデータを確認し、Journey Optimizerでオーディエンスにプッシュ通知を作成して送信する方法を説明します。
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
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
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 4%
---
# レッスン 4 - プッシュキャンペーンの作成

前の演習では、あなたはコーヒー愛好家、フレスコーパの顧客でした。 web サイトとFréscopa アプリを通じて企業と接触し、多くのトランザクションメッセージを受け取りました。 これらのメッセージは、ユーザーがweb サイトまたはアプリケーションとインタラクションすることによってトリガーされます。

この演習では、マーケターに帽子をかぶせて、Frésopaのマーケティングキャンペーンを実装します。このキャンペーンでは、プッシュチャネルを利用してFréscopa アプリユーザーをターゲットにします。 プッシュ通知は、アプリを使用していない場合でも、アプリのユーザーに情報を提供するためだけでなく、アプリで再エンゲージするためにも使用されます。 その目的は、10%の割引を提供することで、顧客にハウスブレンドを購入するように促すことです。

## 学習内容

* プッシュキャンペーンの作成方法。
* プッシュメッセージのデザイン方法。

<br>

## 演習4.1 - プッシュキャンペーンの作成

この演習では、プッシュ キャンペーンを作成し、プッシュ通知をデザインおよびカスタマイズして、プッシュ通知を自分のデバイスに送信します。

1. Journey Optimizerの左側のナビゲーションの「**[!UICONTROL キャンペーン管理]**」セクションで、「**ジャーニー**」を選択します。

1. 「**[!UICONTROL キャンペーンを作成]**」をクリックします。

   ![ キャンペーンの作成](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. **[!UICONTROL キャンペーンを作成]** ページの&#x200B;**[!UICONTROL アクション]** セクションで、**[!UICONTROL プッシュ通知]** チェックボックスを選択します。

1. **[!UICONTROL アプリサーフェス]** ドロップダウンから、*[!DNL Frecopa-Push]*&#x200B;を選択します。

1. 「**[!UICONTROL 作成]**」をクリックして、プッシュキャンペーンを作成します。

   ![ アプリサーフェス ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>これで、キャンペーンのプロパティページに移動します。
> ![キャンペーンのプロパティ ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## 演習4.2 - キャンペーンの設定

このページでは、キャンペーンのプロパティ、オーディエンス、アクション、スケジュールを設定します。

### 4.2.1 [!UICONTROL  プロパティセクション ]

キャンペーンに名前を付けます。 名前は必ず座席番号で始めましょう。検索するとキャンペーンが簡単に見つかります。

例えば、座席番号が99の場合：`99 - 10% Discount Campaign`。

### 4.2.2 **[!UICONTROL オーディエンスセクション]**

1. オーディエンスセクションで、**[!UICONTROL オーディエンスを選択]**&#x200B;をクリックします。

   ![ オーディエンスセクション ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. **[!UICONTROL オーディエンスを選択]**&#x200B;画面で、オーディエンスを検索します。

   **Lab - シート`your seat number`**

1. オーディエンスを選択し、**[!UICONTROL 保存]**&#x200B;をクリックします。

   ![ オーディエンスの選択](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 プッシュ通知のコンテンツの編集

この演習では、プッシュ通知をデザインしてカスタマイズします。

1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL コンテンツを編集]」ボタン**&#x200B;をクリックします。

   ![ コンテンツを編集ボタン ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. 次の画面で、お持ちのモバイルデバイスに応じて、「[!DNL iOS™]」または「[!DNL Android™]」タブを選択してコンテンツを設定します。

>[!BEGINTABS]

>[!TAB iOS]

![iOS タブ ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Android タブ ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL  メッセージの作成] セクション

1. **メッセージを作成：**&#x200B;必要なテキストを自由に追加できます。 ここでは、例をいくつか紹介します。

   * タイトル：`Get 10% off today!`
   * 本文：`Today only! Get 10% off on your House Blend coffee purchase!`

     ![ メッセージを作成](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 メッセージのクリック時の動作を&#x200B;**製品ページを開く**&#x200B;に変更します

1. **[!UICONTROL クリック時の動作]** セクションで、**[!UICONTROL ボディクリックの動作]** ドロップダウンから&#x200B;**[!UICONTROL ディープリンク]**&#x200B;を選択します。

1. 次のURLをコピーして、**URL フィールド**&#x200B;に貼り付けます。

   `dxdemo://exoticVibes`

   ![ ディープリンク ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 メッセージに画像を追加

1. **[!UICONTROL メディアを追加]** セクションで、**[!UICONTROL メディアを追加]**&#x200B;をクリックします。

   ![ メディアボタンを追加](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. **[!UICONTROL Assetsを選択]**&#x200B;画面で、左側のナビゲーションで&#x200B;**Fréscopa フォルダー**&#x200B;を開き、そのフォルダーから画像を選択します。

   例：`HouseBlend.png`

1. 画像をクリックし、**[!UICONTROL 選択] ボタン**&#x200B;をクリックして、画像をプッシュ通知に追加します。

   ![画像を選択](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. プレビュー画面で、**[!UICONTROL ビューを展開]**&#x200B;をクリックします。
   > 1. メッセージをプレビューします。
   > <br>
   >
   > ![ ビューを展開](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

### ボーナス演習

あなたが演習のこの部分を完了し、まだ時間がある場合は、ボーナスの演習を試してください：

+++ ボーナス演習

#### 受信者の名前を追加して、送信するメッセージをパーソナライズします

1. **[!UICONTROL 本文]** フィールドの横にある&#x200B;**パーソナライゼーションダイアログ**&#x200B;をクリックします。

   ![ パーソナライゼーションボタン ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-button.png)

1. **パーソナライゼーションダイアログ**&#x200B;画面で、テキストの最初の名前を追加する場所にカーソルを置きます。

1. 左側のナビゲーションで&#x200B;**プロファイル属性**&#x200B;が選択されていることを確認します。

   ![ プロファイル属性](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. **検索フィールド**&#x200B;で、`first name`を検索します。

1. **名（プロファイル属性>人物> フルネーム）**&#x200B;の横にある&#x200B;**+**&#x200B;をクリックして、パーソナライゼーションフィールドをテキストに追加します。

   ![名を検索](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > 次のようなテキストを作成します。
   > 
   >![Personalization トークン ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-token.png)

1. 「**[!UICONTROL 保存]**」をクリックして、パーソナライゼーションを保存します。


   >[!SUCCESS]
   >
   > 1. プレビュー画面で、**[!UICONTROL ビューを展開]**&#x200B;をクリックします。
   > 1. メッセージをプレビューします。
   > 
   > ![ ビューを展開](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. レビューとアクティブ化

メッセージの内容に満足している場合は、メッセージをアクティベートできます。

1. 「**[!UICONTROL レビュー」をクリックして]**&#x200B;をアクティブ化します。

   ![ ボタンのレビューとアクティベート ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. **[!UICONTROL アクティブ化のレビュー]**&#x200B;画面で、**[!UICONTROL アクティブ化]**&#x200B;をクリックします。

   ![画面をアクティベートするためのレビュー](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> **キャンペーンの概要ページ**&#x200B;で、キャンペーンを検索し、ステータスを確認します。
>
> ![ キャンペーンステータス ](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> ステータスが処理からライブに変わり、完了します。これには数分かかる場合があります。
> ステータスが「完了」に変更されたら、次の操作を行います。
>
> ![ プッシュ結果](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-push-notification-result.png)

## その他のリソース

**ビデオの操作方法：**

* [プッシュキャンペーンの設定と送信](/help/channels/create-a-push-campaign.md)

**製品ドキュメント：**

* [プッシュ通知の基本を学ぶ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/get-started-push)
* [プッシュ通知の作成](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/create-push)
* [プッシュ通知のデザイン](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/design-push)
* [プッシュ通知の確認と送信](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/send-push)
