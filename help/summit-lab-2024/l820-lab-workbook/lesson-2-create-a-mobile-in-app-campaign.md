---
title: レッスン 2 - モバイル アプリ内キャンペーンを作成する
description: モバイルのアプリ内キャンペーンの作成とトリガー。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
    internal-label: Communication channels
subfeature_v2:
  - id: cc5c44e2-54a1-4927-b794-442cd87d8f74
    internal-label: In App channel
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 2%
---
# レッスン 2 - モバイル アプリ内キャンペーンを作成する

このレッスンでは、モバイルのアプリ内メッセージを作成してトリガー化します。

## 学習内容

* アプリ内メッセージがトリガーされる方法を理解します。
* モバイルのアプリ内キャンペーンの作成方法について説明します。
* アプリ内メッセージをトリガーします。

## 演習2.1 - Journey Optimizerにログインする

1. [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}を開く
2. 次の詳細を使用してログインします。
   <br>
   **ユーザー名：** L820+**`<your seat number>`**@adobeeventlab.com
   **パスワード：** Adobe2024!
   <br>
ログインの詳細は、ラボマシンのデスクトップで確認できます。 Adobe IDとパスワードを使用します。
   ![&#x200B; デスクトップ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/desk-top.png)

   ![&#x200B; ログイン画面](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. 次の2つの画面をスキップできます。
   <br>
   ![電話番号](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Personalization ポップアップ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Journey Optimizerにログインし、ホームページで次の操作を行う必要があります。
>
>![AJO ホームページ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## 演習2.2 モバイルアプリ内キャンペーンの作成

この演習では、アプリを開いたときにトリガーされるアプリ内メッセージングキャンペーンを作成します。

1. Journey Optimizerで、左側のナビゲーションで「**[!UICONTROL キャンペーン]**」を選択します。

1. 「**[!UICONTROL キャンペーンを作成]**」をクリックします。

   ![&#x200B; キャンペーンの作成](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. **[!UICONTROL キャンペーンを作成]** ページの&#x200B;**[!UICONTROL アクション]** セクションで、**[!UICONTROL アプリ内メッセージ]** チェックボックスを選択します。

1. **[!UICONTROL 送信先]** ドロップダウンから、**[!DNL Mobile]**&#x200B;を選択します。

1. **[!UICONTROL アプリサーフェス]** ドロップダウンから、**[!DNL Frecopa Mobile App]**&#x200B;を選択します。

1. 「**[!UICONTROL 作成]**」をクリックします。

   ![&#x200B; アプリサーフェス &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>これで、キャンペーンのプロパティに移動します。
>
> ![&#x200B; キャンペーンのプロパティ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## 演習2.3 キャンペーンの設定

### 2.3.1 [!UICONTROL &#x200B; プロパティセクション &#x200B;]

キャンペーンに名前を付けます。 名前は必ず座席番号で始めてください。そうすれば、キャンペーンを簡単に再び見つけることができます。

例えば、座席番号が99の場合：`99 - Welcome Campaign`。

![&#x200B; プロパティ セクション &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 カスタムトリガールールの設定

1. **[!UICONTROL トリガーセクション]**&#x200B;まで下にスクロールし、**[!UICONTROL トリガーを編集]**&#x200B;をクリックします。

   ![変更](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. ルールビルダーで、**[!UICONTROL Application Launch]**&#x200B;をクリックし、ドロップダウンから「*データをPlatform*に送信」を選択します。
   ![&#x200B; データプラットフォームに送信](/help/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. **[!UICONTROL 条件を追加]**&#x200B;をクリックして条件を追加します。

   ![条件を追加ボタン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. **[!UICONTROL 特性を選択]** ドロップダウンから、**[!UICONTROL XDM イベントタイプ]**&#x200B;を選択します。

   ![XDM イベントタイプ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. 次のテキストフィールドに、覚えておくことができる&#x200B;*`<custom string value>`*&#x200B;を追加します。

1. 値を保存するには、「[!UICONTROL 追加&#x200B;**] `<custom string value>`」**&#x200B;クリックします。

   このカスタム文字列値は、後でメッセージを実行するために使用されます。

   >[!TIP]
   > カスタム文字列値に座席番号を追加すると、ユニークで覚えやすくなります。
   > 
   > 例：`99exerciseTrigger`

   ![&#x200B; カスタムトリガー文字列値を追加](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. 右上の「**[!UICONTROL 完了]**」をクリックします。

>[!SUCCESS]
>
>これで、カスタムトリガーイベントを使用してアプリ内メッセージを定義しました。
>
>カスタムトリガーが定義された![Campaign](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 アプリ内メッセージのコンテンツの編集

**[!UICONTROL アクション]** セクションで、**[!UICONTROL コンテンツを編集]**&#x200B;をクリックします。

![&#x200B; コンテンツを編集ボタン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

[!UICONTROL &#x200B; アプリ内メッセージ &#x200B;] エディターが表示され、アプリ内メッセージのコンテンツを設定できます。

#### 2.3.3.1 レイアウト

メッセージに適用するレイアウトを選択します。

例えば、**[!UICONTROL モーダル]**&#x200B;をクリックして、アプリ内メッセージをモーダルレイアウトにします。

![&#x200B; モーダルボタン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 メッセージのオーサリングとキャンペーンの公開

1. メディアセクションで、次のURLに貼り付けます。  `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
   値フィールドの外をクリックすると、画像が表示されます。

   プレビューに表示される![&#x200B; メディア &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-media.png)

2. 次の&#x200B;**[!UICONTROL コンテンツ]** セクションでは、**[!UICONTROL ヘッダー]**&#x200B;と&#x200B;**[!UICONTROL 本文]**&#x200B;のメッセージに表示する独自のカスタムテキストを追加します。

   ![&#x200B; ヘッダーと本文](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-content.png)

3. その他のオプション：
   1. **ボタン：**

      ![&#x200B; ボタンのセクション &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. このセクションでは、「ボタンテキスト」フィールドを編集して、CTAボタンのテキストをカスタマイズできます。

      2. **[!UICONTROL インタラクティブイベント]** フィールドは、CTAがユーザーによって押されたときにSDKに渡される値を定義するために使用されます。

      3. **[!UICONTROL Target]** フィールドは、CTAがユーザーを取得する場所を定義するために使用されます。 これには、URLとディープリンクが含まれます。 例えば、このディープリンクを`dxdemo://exoticVibes`などの製品ページに追加できます。

      4. 追加ボタンを追加するには、**[!UICONTROL +追加ボタン]**&#x200B;を押します。

      5. 2番目のボタンがメッセージに追加されると、ドロップダウンボックスでボタンレイアウトを変更するオプションが表示されます。


   2. **詳細フォーマット**

      ![詳細フォーマット切り替え](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      このトグルを有効にすると、エディターで追加のカスタマイズオプションが表示されます。

      1. メディアサイズ
      1. フォント
      1. Pt サイズ
      1. フォントカラー
      1. 揃え

      ![詳細な書式設定オプション &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **設定タブ**

      このタブに移動し、**[!UICONTROL プレビュー]** セクションで、**アプリプレビュー**&#x200B;を変更できます。
      <br>\
      ![設定タブ](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. 「**[!UICONTROL レイアウト]**」セクションでは、画像を背景または単色として使用するオプションが表示されます。

      2. **[!UICONTROL メッセージ]** セクションには、メッセージに対して有効にできるカスタムインタラクションが用意されています。
         1. カスタムジェスチャー
         2. UIの引き継ぎ
         3. カスタム UIの引き継ぎ
         4. カスタムサイズ
         5. カスタム位置
         6. カスタムアニメーション
         7. メッセージラウンドコーナー
   <br>
4. コンテンツのオーサリングが完了し、メッセージに満足したら、**[!UICONTROL レビューをクリックしてアクティブ化] ボタン**&#x200B;をクリックします。

   >[!SUCCESS]
   >
   > これで、モバイルのアプリ内メッセージのオーサリングが完了しました。 これで、**ページをアクティブ化するためにキャンペーン** レビューに参加する必要があります。
   >
   >![&#x200B; レビューしてアクティブ化](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > ここでは、メッセージの完全な概要を確認できます。
   >
   > *トリガールールとして使用したカスタム値に注意してください。 この値は、アプリ内メッセージを実行するために使用されます。 使用された値は、概要ページのハイライト領域にあります。*

   >[!NOTE]
   >アプリ内メッセージの現在のトリガーは、デフォルトの&#x200B;**Application launch event happens**&#x200B;です。つまり、アプリの起動時にアプリ内メッセージがトリガーされます。 これは、**[!UICONTROL スケジュール セクション]**&#x200B;で確認できます。

5. キャンペーンのレビューが完了したら、「アクティブ化」ボタンを押してキャンペーンを公開します。
   <br>
   ![&#x200B; アクティブ化](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> キャンペーンダッシュボードが表示されます。 スクロールするか検索機能を使用して、キャンペーンを見つけます。 キャンペーンのステータスが&#x200B;**[!UICONTROL ライブ]** （～1分）に変更されると、キャンペーンは公開されました。
>
> ![公開されたキャンペーン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## 演習2.4 モバイルアプリ内メッセージのトリガー

ペイロードを更新し、新しく公開したCampaignをダウンロードするには：

1. お使いのモバイルデバイスで、Fréscopa アプリを完全に閉じます。
2. Fréscopa アプリを再度開きます。
3. 次に、アプリの「演習」タブに移動します。

   ![&#x200B; エクササイズボタン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. テキストフィールドに、Campaignで定義したカスタムトリガー値を入力します。 次に、「送信」を押します。


   ![変更](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>「送信」をクリックすると、手動でトリガーが実行され、作成したアプリ内通知がポップアップ表示されます。
>
>![&#x200B; アプリ内メッセージ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *メッセージのトリガーに問題がある場合は、次の点を確認してください。*
> 
> * *モバイルアプリの「イベント名」フィールドに、トリガールールの値がCampaignでどのように入力されているかを正確に入力してください。*
> * *大文字が正しいこと、および先頭または末尾のスペースがないことを確認してください。*
> * *Campaign ダッシュボードのキャンペーンに戻ってクリックし、Campaign レビューページに戻ると、使用したトリガールール値を検索できます。*

初めてのJourney Optimizer アプリ内メッセージを作成して公開しました。


## ボーナスエクササイズ：デバイスでキャンペーンとプレビューを複製

**キャンペーンの複製**&#x200B;および&#x200B;**デバイスでのプレビュー**&#x200B;機能は、すぐに使用できる機能で、キャンペーンを複製したり、アプリ内メッセージをアクティブ化する前にデバイスで直接テストおよびレビューしたりできます。 この演習では、この機能を使用する方法と、演習3.1で作成したメッセージをプレビューする方法について説明します。

1. キャンペーンダッシュボードページでキャンペーンの名前をクリックして、作成したキャンペーンを開き、キャンペーンを開きます。 これにより、**[!UICONTROL レビューキャンペーン]** ページに戻ります。
1. **[!UICONTROL 複製ボタン]**&#x200B;を押します。 複製されている新しいキャンペーンに名前を付ける新しいプロンプトが開きます。 覚えやすい新しい名前を追加するか、**[!DNL _copy]**&#x200B;がデフォルトで追加されるデフォルト名を使用します。

   ![&#x200B; キャンペーンを複製](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. 「複製」ボタンを押すと、複製されたキャンペーンが作成され、キャンペーンダッシュボードに戻ります。
1. キャンペーンが複製されたら、新しいキャンペーンを開きます。

1. デバイスのプレビュー機能には、**[!UICONTROL Campaign レビュー]** ページまたは&#x200B;**[!UICONTROL Campaign オーサー]** ステップからアクセスできます。

   デバイス上の![&#x200B; プレビューボタン](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. 次に、デバイスに接続の画面から&#x200B;**[!UICONTROL 開始ボタン]**&#x200B;をクリックします。

   ![開始ボタン](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Fréscopa アプリを起動するように設定されているベース URLを入力してください：`dxdemo://`

   ![&#x200B; プレビューurl](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. 画面の指示に従います。
   1. お使いのモバイルデバイスでQR コードをスキャンすると、Fréscopa アプリが開き、PINを入力できる画面が表示されます。
   2. AJOに表示されているピンを入力し、ピンを入力すると右下に表示される「Assurance」ボタンをクリックします。


   ![&#x200B; ピンを入力](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. このポップアップはコンピューターの画面に表示されます

   ![&#x200B; ポップアップ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-pop-up.png)

1. 「完了」ボタンをクリックします。 これにより、ダイアログボックスが閉じ、デバイス上のプレビューに電話が接続されます。


>[!SUCCESS]
>
> アプリ内メッセージがデバイスに表示されます。
>
> * 接続すると、アプリ内メッセージが毎回表示されるので、**[!UICONTROL デバイスでプレビュー] ボタン**&#x200B;をクリックします。

## その他のリソース

**ビデオの操作方法：**

* [アプリ内キャンペーンの作成](/help/channels/create-an-in-app-campaign.md)
* [アプリ内メッセージを作成](/help/channels/author-in-app-messages.md)

**製品ドキュメント：**

* [アプリ内チャネルの基本を学ぶ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [モバイルのアプリ内メッセージの作成](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app)
* [アプリ内コンテンツのデザイン](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [アプリ内通知の確認および送信](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
