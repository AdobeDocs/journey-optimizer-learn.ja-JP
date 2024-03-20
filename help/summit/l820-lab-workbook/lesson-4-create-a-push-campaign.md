---
title: レッスン 4 — プッシュキャンペーンの作成
description: プロファイルデータを確認し、Journey Optimizerでオーディエンスにプッシュ通知を作成して送信する方法を学びます。
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
source-git-commit: c590b47ad3dfc54badbac0d8fcaff6b9dd053cc1
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---


# レッスン 4 — プッシュキャンペーンの作成

前の練習では、コーヒー愛好家、フレスコパのお客様でした。 Web サイトや Fréscopa アプリを通じてブランドとやり取りし、多くのトランザクションメッセージを受け取りました。 これらのメッセージは、Web サイトまたはアプリケーションとのユーザーのインタラクションを通じてトリガーされます。

この演習では、マーケターに帽子をかぶせ、Frésopa 用のマーケティングキャンペーンを実装します。このキャンペーンでは、プッシュチャネルを利用して Fréscopa アプリのユーザーをターゲットに設定します。 プッシュ通知は、アプリを使用していない場合でも、アプリユーザーに通知を与え続け、アプリを使用して再び関与させるために使用されます。 目的は、10%の割引を提供して、顧客が家のブレンドを購入するよう促すことです。

## 学習内容

* プッシュキャンペーンの作成方法を説明します。
* プッシュメッセージのデザイン方法を説明します。

<br>

## 演習 4.1 — プッシュキャンペーンの作成

この練習では、プッシュキャンペーンを作成し、プッシュ通知を設計およびカスタマイズし、プッシュ通知を独自のデバイスに送信します。

1. Journey Optimizerの左側のナビゲーションで、 **[!UICONTROL ジャーニー管理]** セクション、選択 **キャンペーン**.

1. クリック **[!UICONTROL キャンペーンを作成]**.

   ![キャンペーンを作成](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. 次の日： **[!UICONTROL キャンペーンを作成]** ページの  **[!UICONTROL アクション]** セクションで、 **[!UICONTROL プッシュ通知]** 」チェックボックスをオンにします。

1. 次から： **[!UICONTROL アプリサーフェス]** ドロップダウン、選択 *[!DNL Frecopa-Push]*.

1. クリック **[!UICONTROL 作成]** をクリックして、プッシュキャンペーンを作成します。

   ![アプリサーフェス](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>これで、キャンペーンプロパティページに移動します。
> ![キャンペーンのプロパティ](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## 演習 4.2 — キャンペーンの設定

このページでは、キャンペーンのプロパティ、オーディエンス、アクションおよびスケジュールを設定します。

### 4.2.1 [!UICONTROL 「プロパティ」セクション]

キャンペーンに名前を付けます。 名前は必ずシート番号で始めてください。これにより、キャンペーンの検索時にキャンペーンを簡単に見つけることができます。

例えば、座席番号が 99 の場合： `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL オーディエンスセクション]**

1. 「オーディエンス」セクションで、 **[!UICONTROL オーディエンスを選択]**.

   ![オーディエンスセクション](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. 次の日： **[!UICONTROL オーディエンスを選択]** 画面で、オーディエンスを検索します。

   **Lab — シート`your seat number`**

1. オーディエンスを選択し、「 **[!UICONTROL 保存]**.

   ![オーディエンス選択](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 プッシュ通知の内容の編集

この練習では、プッシュ通知を設計し、カスタマイズします。

1. Adobe Analytics の **[!UICONTROL アクション]** セクションで、 **[!UICONTROL コンテンツを編集] ボタン**.

   ![コンテンツ編集ボタン](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. 次の画面で、使用しているモバイルデバイスに応じて、 [!DNL iOS™] または [!DNL Android™] タブをクリックして、コンテンツを設定します。

>[!BEGINTABS]

>[!TAB iOS]

![iOSタブ](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![「Android」タブ](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL メッセージを作成] セクション

1. **メッセージを作成：** 任意のテキストを自由に追加できます。 使用できる例を次に示します。

   * タイトル：`Get 10% off today!`
   * 本文： `Today only! Get 10% off on your House Blend coffee purchase!`

     ![メッセージを作成](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 メッセージのクリック時の動作をに変更する **製品ページを開く**

1. Adobe Analytics の **[!UICONTROL クリック時の動作]** セクション、選択 **[!UICONTROL ディープリンク]** から **[!UICONTROL 本文のクリック動作]** ドロップダウン。

1. 次の URL を **URL フィールド**:

   `dxdemo://exoticVibes`

   ![ディープリンク](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 メッセージへの画像の追加

1. Adobe Analytics の **[!UICONTROL メディアを追加]** セクションで、 **[!UICONTROL メディアを追加]**.

   ![メディアボタンの追加](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. 次の日： **[!UICONTROL アセットを選択]** 画面の左側のナビゲーションで、 **Fréscopa フォルダー** をクリックし、そのフォルダーから画像を選択します。

   例：`HouseBlend.png`

1. 画像をクリックし、 **[!UICONTROL 選択] ボタン** をクリックして、画像をプッシュ通知に追加します。

   ![画像を選択](/help/summit/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. プレビュー画面で、 **[!UICONTROL 表示を展開]**.
   > 1. メッセージをプレビューします。
   > <br>
   >
   > ![展開表示](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

### ボーナスエクササイズ

練習のこの部分を完了し、まだ時間がある場合は、ボーナス練習を試してみてください。

+++ ボーナスエクササイズ

#### 受信者の名を追加して、送信するメッセージをパーソナライズします

1. クリック **パーソナライゼーションダイアログ** の横 **[!UICONTROL 本文]** フィールドに入力します。

   ![パーソナライゼーションボタン](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. 次の日： **パーソナライゼーションダイアログ** 画面で、テキスト内の名を追加する位置にカーソルを置きます。

1. 次の点を確認します。 **プロファイル属性** が左側のナビゲーションで選択されている。

   ![プロファイル属性](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. Adobe Analytics の **検索フィールド**、以下を検索します。 `first name`.

1. クリック **+** の横 **名（プロファイル属性/ユーザー/姓名）** パーソナライゼーションフィールドをテキストに追加します。

   ![名を検索](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > テキストは次のようになります。
   > 
   >![パーソナライゼーショントークン](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. クリック **[!UICONTROL 保存]** パーソナライゼーションを保存します。


   >[!SUCCESS]
   >
   > 1. プレビュー画面で、 **[!UICONTROL 表示を展開]**.
   > 1. メッセージをプレビューします。
   > 
   > ![展開表示](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4.確認とアクティブ化

メッセージの内容に満足した場合は、次の手順でメッセージをアクティブ化できます。

1. クリック **[!UICONTROL 有効化するレビュー]**.

   ![「レビューとアクティブ化」ボタン](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. 次の日： **[!UICONTROL 有効化するレビュー]** スクリーン、クリック **[!UICONTROL 有効化]**.

   ![画面をアクティベートするレビュー](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> 次の日： **キャンペーンの概要ページ**&#x200B;をクリックし、キャンペーンを見つけてステータスを確認します。
>
> ![キャンペーンステータス](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> ステータスが「処理中」から「ライブ」に変わり、「完了」に変わります。これには数分かかる場合があります。
> ステータスが「完了」に変わったら、次の手順に従います。
>
> ![結果のプッシュ](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)


**ありがとうございます。**

ご参加いただき、ありがとうございます。 Summit App の Lab 820 セッション調査を完了し、実験室がお客様の期待に応えた場合は、どのように行ったかに関するフィードバックをお寄せください。

