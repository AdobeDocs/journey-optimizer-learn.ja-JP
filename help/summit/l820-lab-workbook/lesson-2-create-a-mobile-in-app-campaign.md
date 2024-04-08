---
title: レッスン 2：モバイルのアプリ内キャンペーンの作成
description: モバイルのアプリ内キャンペーンを作成し、トリガーを設定します。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
source-git-commit: 4f5c92f79eba3651b3633b7850e993160cb1f72c
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 1%

---

# レッスン 2：モバイルのアプリ内キャンペーンの作成

このレッスンでは、モバイルのアプリ内メッセージを作成し、トリガーを設定します。

## 学習内容

* アプリ内メッセージがトリガーされる方法を理解します。
* モバイルのアプリ内キャンペーンの作成方法を理解します。
* アプリ内メッセージをトリガーします。

## 演習 2.1 - Journey Optimizerへのログイン

1. 開く [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. 次の詳細を使用してログインします。
   <br>
   **ユーザー名：** L820+**`<your seat number>`**@adobeeventlab.com
   **パスワード：**   Adobe2024!
   <br>
ログインの詳細は、ラボマシンのデスクトップで確認できます。 Adobe IDとパスワードを使用します。
   ![デスクトップ](/help/summit/l820-lab-workbook/assets/desk-top.png)

   ![ログイン画面](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. 次の 2 つの画面はスキップできます。
   <br>
   ![電話番号](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![パーソナライゼーションポップアップ](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Journey Optimizerおよびホームページにログインする必要があります。
>
>![AJO ホームページ](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## 演習 2.2: モバイルのアプリ内キャンペーンの作成

この演習では、アプリを開くとトリガーされるアプリ内メッセージキャンペーンを作成します。

1. Journey Optimizerの左側のナビゲーションで、 **[!UICONTROL キャンペーン]**.

1. クリック **[!UICONTROL キャンペーンを作成]**.

   ![キャンペーンを作成](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. 日 **[!UICONTROL キャンペーンを作成]** ページ （内）  **[!UICONTROL アクション]** セクションで、 **[!UICONTROL アプリ内メッセージ]** チェックボックスをオンにします。

1. から **[!UICONTROL 送信先]** ドロップダウン、選択 **[!DNL Mobile]**.

1. から **[!UICONTROL アプリサーフェス]** ドロップダウン、選択 **[!DNL Frecopa Mobile App]**.

1. 「**[!UICONTROL 作成]**」をクリックします。

   ![アプリサーフェス](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>これで、Campaign のプロパティが表示されます。
>
> ![キャンペーンプロパティ](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## 演習 2.3：キャンペーンの設定

### 2.3.1 [!UICONTROL プロパティセクション]

キャンペーンに名前を付けます。 キャンペーンをもう一度簡単に見つけられるように、名前はシート番号で始めてください。

例えば、シート番号が 99 の場合：  `99 - Welcome Campaign`.

![プロパティセクション](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 カスタムトリガールールの設定

1. にスクロール ダウンします。 **[!UICONTROL トリガーセクション]**&#x200B;を選択し、 **[!UICONTROL トリガーを編集]**.

   ![変更](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. ルールビルダーで、 **[!UICONTROL アプリケーションの起動]** およびドロップダウンから  *Platform にデータを送信済み*.
   ![データプラットフォームに送信済み](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. 「」をクリックして条件を追加 **[!UICONTROL 条件を追加]**.

   ![「条件を追加」ボタン](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. から **[!UICONTROL 特性を選択]** ドロップダウンで次を選択 **[!UICONTROL XDM イベントタイプ]**.

   ![XDM イベントタイプ](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. 次のテキストフィールドに、 *`<custom string value>`* 思い出してください。

1. 値を保存するには、「**」をクリックします[!UICONTROL 追加**] `<custom string value>`.

   このカスタム文字列値は、後でメッセージを発生させるために使用されます。

   >[!TIP]
   > シート番号をカスタム文字列値に追加すると、シート番号が一意になり、覚えやすくなります。
   > 
   > 例：`99exerciseTrigger`

   ![カスタムトリガー文字列値を追加](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. クリック **[!UICONTROL 完了]** 右上。

>[!SUCCESS]
>
>これで、カスタムトリガーイベントを使用してアプリ内メッセージを定義しました。
>
>![カスタムトリガーが定義されたキャンペーン](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 アプリ内メッセージのコンテンツを編集する

が含まれる **[!UICONTROL アクション]** セクションで、をクリック **[!UICONTROL コンテンツを編集]**.

![コンテンツを編集ボタン](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

この [!UICONTROL アプリ内メッセージ] エディターが表示され、アプリ内メッセージコンテンツを設定できます。

#### 2.3.3.1 レイアウト

メッセージに適用するレイアウトを選択します。

例えば、 **[!UICONTROL モーダル]** を使用して、アプリ内メッセージをモーダルレイアウトにします。

![モーダルボタン](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 メッセージのオーサリングとキャンペーンの公開

1. 「メディア」セクションで、次の URL をペーストします。  `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
値フィールドの外をクリックすると、画像が表示されます。

   ![プレビューに表示されるメディア](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. 次の場合 **[!UICONTROL コンテンツ]** セクションに、メッセージに表示する独自のカスタムテキストを追加します。 **[!UICONTROL ヘッダー]** および **[!UICONTROL 本文]**.

   ![ヘッダーと本文](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. その他のオプション：
   1. **ボタン：**

      ![ボタンセクション](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. エディターのこのセクションでは、「ボタンテキスト」フィールドを編集して、CTA ボタンのテキストをカスタマイズできます。

      2. この **[!UICONTROL インタラクトイベント]** フィールドは、ユーザーが CTA を押した際に SDK に渡される値を定義するために使用されます。

      3. この **[!UICONTROL ターゲット]** フィールドは、CTA でユーザーを取得する場所を定義するために使用されます。 これには、URL とディープリンクが含まれます。 例えば、次のような製品ページにこのディープリンクを追加できます `dxdemo://exoticVibes`.

      4. ボタンを追加するには、を押します。 **[!UICONTROL +追加ボタン]**.

      5. メッセージに 2 つ目のボタンが追加されると、ドロップダウンボックスでボタンのレイアウトを変更できるようになりました。


   2. **詳細フォーマット**

      ![詳細フォーマットの切り替え](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      この切替スイッチを有効にすると、エディターに追加のカスタマイズオプションが提供されます。

      1. メディアサイズ
      1. フォント
      1. Pt サイズ
      1. フォントカラー
      1. 整列

      ![詳細フォーマットオプション](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **「設定」タブ**

      このタブに切り替えて、次のフィールドに移動します。 **[!UICONTROL プレビュー]** セクションでは、 **アプリのプレビュー**.
      <br>\
      ![「設定」タブ](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. この **[!UICONTROL レイアウト]** このセクションでは、画像を背景として使用するか、単色で使用するかを選択できます。

      2. この **[!UICONTROL メッセージ]** 「」セクションには、メッセージに対して有効にできるカスタムインタラクションが用意されています。
         1. カスタムジェスチャー
         2. UI テイクオーバー
         3. カスタム UI テイクオーバー
         4. カスタムサイズ
         5. カスタム位置
         6. カスタムアニメーション
         7. 角を丸めたメッセージ
   <br>
4. コンテンツのオーサリングが完了し、メッセージに満足したら、 **[!UICONTROL アクティブ化するレビュー] ボタン**.

   >[!SUCCESS]
   >
   > これで、モバイルのアプリ内メッセージのオーサリングが完了しました。 これでキャンペーンに追加されます **[!UICONTROL アクティブ化するレビュー]** ページ。
   >
   >![レビューしてアクティブ化](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > ここでは、メッセージの完全な概要を確認できます。
   >
   > *トリガールールとして使用したカスタム値をメモしてください。 この値は、アプリ内メッセージの実行に使用されます。 使用される値は、概要ページのハイライト領域にあります。*

   >[!NOTE]
   >アプリ内メッセージの現在のトリガーがデフォルトです **アプリケーション起動イベントの発生**。つまり、アプリの起動時にアプリ内メッセージがトリガーされます。 これはで確認できます **[!UICONTROL 集計表セクション]**.

5. キャンペーンのレビューが完了したら、「アクティブ化」ボタンを押してキャンペーンを公開します。
   <br>
   ![アクティベート](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> これで、キャンペーン ダッシュボードが表示されます。 スクロールするか、検索機能を使用して、キャンペーンを見つけます。 キャンペーンのステータスが「」に変更された場合 **[!UICONTROL ライブ]** （～1 分）で、キャンペーンが公開されました。
>
> ![公開済みキャンペーン](/help/summit/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## 演習 2.4：モバイルのアプリ内メッセージのトリガー

ペイロードを更新し、新しく公開したキャンペーンをダウンロードするには：

1. モバイルデバイスで、Fréscopa アプリを完全に閉じます。
2. Fréscopa アプリを再度開きます。
3. 次に、アプリの「演習」タブに移動します。

   ![演習ボタン](/help/summit/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. テキストフィールドに、Campaign で定義したカスタムトリガー値を入力します。 次に、「送信」を押します。


   ![変更](/help/summit/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>「送信」をクリックすると、手動でトリガーを実行すると、作成したアプリ内通知がポップアップ表示されます。
>
>![アプリ内メッセージ](/help/summit/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *メッセージのトリガーに関する問題が発生している場合は、次の点を確認してください。*
> 
> * *モバイルアプリの「イベント名」フィールドに、トリガールールの値を、Campaign での値と正確に一致するように入力してください。*
> * *大文字と小文字が正しく、先頭または末尾にスペースがないことを確認します。*
> * *Campaign ダッシュボードでキャンペーンに「戻る」をクリックすると、Campaign のレビューページに戻る場合に、使用したトリガールールの値を検索できます。*

最初のJourney Optimizerのアプリ内メッセージを作成して公開しました。


## ボーナス演習：デバイスでのキャンペーンとプレビューの複製

この **キャンペーンを複製** および **デバイスでプレビュー** 機能は、すぐに使用できる機能で、キャンペーンを複製し、アクティブ化する前にデバイスで直接アプリ内メッセージをテストおよびレビューできます。 この演習では、この機能の使用方法と、演習 3.1 で作成したメッセージのプレビュー方法を説明します。

1. キャンペーンダッシュボードページでキャンペーンの名前をクリックして、作成したキャンペーンを開きます。 これにより、に戻ります **[!UICONTROL キャンペーンをレビュー]** ページ。
1. を押します。 **[!UICONTROL 「複製」ボタン]**. これにより、新しいプロンプトが開き、複製中の新しいキャンペーンに名前を付けることができます。 覚えやすい新しい名前を追加するか、デフォルトの名前を使用します。ここで、 **[!DNL _copy]** はデフォルトで追加されます。

   ![キャンペーンを複製](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. 「複製」ボタンをクリックすると、複製キャンペーンが作成され、キャンペーンダッシュボードに戻ります。
1. キャンペーンが複製されたら、新しいキャンペーンを開きます。

1. デバイスでプレビュー機能には、 **[!UICONTROL キャンペーンレビュー]** ページまたは **[!UICONTROL キャンペーン作成者]** ステップ。

   ![デバイスのプレビューボタン](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. 次に、 **[!UICONTROL 「開始」ボタン]** デバイスに接続画面から。

   ![「開始」ボタン](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Fréscopa アプリを起動するように設定されているベース URL を入力します。 `dxdemo://`

   ![url をプレビュー](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. 画面に表示される指示に従います。
   1. モバイルデバイスで QR コードをスキャンすると、Fréscopa アプリが開き、ピンを入力できる画面が表示されます。
   2. デバイスのアシュランス画面で AJO に表示されているピンを入力し、ピンを入力したら右下に表示される「接続」ボタンをクリックします。


   ![ピン留めを入力](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. このポップアップは、コンピューター画面に表示されます

   ![ポップアップ](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. 「完了」ボタンをクリックします。 これにより、ダイアログボックスが閉じ、電話がデバイスのプレビューに接続されます。


>[!SUCCESS]
>
> アプリ内メッセージがデバイスに表示されます。
>
> *接続すると、毎回アプリ内メッセージが表示されます。 **[!UICONTROL デバイスでプレビュー] ボタン**.

## その他のリソース

**ハウツービデオ：**

* [アプリ内キャンペーンを作成](/help/channels/create-an-in-app-campaign.md)
* [アプリ内メッセージの作成](/help/channels/author-in-app-messages.md)

**製品ドキュメント：**

* [アプリ内チャネルの基本を学ぶ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [モバイルのアプリ内メッセージの作成](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app)
* [アプリ内コンテンツのデザイン](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [アプリ内通知の確認および送信](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
