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
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 1%

---

# レッスン 2：モバイルのアプリ内キャンペーンの作成

このレッスンでは、モバイルのアプリ内メッセージを作成し、トリガーを設定します。

## 学習内容

* アプリ内メッセージがトリガーされる方法を理解します。
* モバイルのアプリ内キャンペーンの作成方法を理解します。
* アプリ内メッセージをトリガーします。

## 演習 2.1 - Journey Optimizerへのログイン

1. [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} を開く
2. 次の詳細を使用してログインします。
   <br>
   **ユーザー名：** L820+**`<your seat number>`**@adobeeventlab.com
   **パスワード：**   Adobe2024!
   <br>
ログインの詳細は、ラボマシンのデスクトップで確認できます。 Adobe IDとパスワードを使用します。
   ![&#x200B; デスクトップ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/desk-top.png)

   ![&#x200B; ログイン画面 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. 次の 2 つの画面はスキップできます。
   <br>
   ![&#x200B; 電話番号 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Personalization ポップアップ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Journey Optimizerおよびホームページにログインする必要があります。
>
>![AJO ホームページ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## 演習 2.2: モバイルのアプリ内キャンペーンの作成

この演習では、アプリを開くとトリガーされるアプリ内メッセージキャンペーンを作成します。

1. Journey Optimizerの左側のナビゲーションで「**[!UICONTROL キャンペーン]**」を選択します。

1. **[!UICONTROL キャンペーンを作成]** をクリックします。

   ![&#x200B; キャンペーンを作成 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. **[!UICONTROL キャンペーンを作成]** ページの「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL アプリ内メッセージ]**」チェックボックスを選択します。

1. **[!UICONTROL 送信先]** ドロップダウンから「**[!DNL Mobile]**」を選択します。

1. **[!UICONTROL アプリサーフェス]** ドロップダウンから「**[!DNL Frecopa Mobile App]**」を選択します。

1. 「**[!UICONTROL 作成]**」をクリックします。

   ![&#x200B; アプリサーフェス &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>これで、Campaign のプロパティが表示されます。
>
> ![&#x200B; キャンペーンプロパティ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## 演習 2.3：キャンペーンの設定

### 2.3.1 [!UICONTROL &#x200B; プロパティセクション &#x200B;]

キャンペーンに名前を付けます。 キャンペーンをもう一度簡単に見つけられるように、名前はシート番号で始めてください。

例えば、シート番号が 99 の場合：`99 - Welcome Campaign` です。

![properties セクション &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 カスタムトリガールールの設定

1. 「**[!UICONTROL トリガー」セクションまでスクロールし]** 「**[!UICONTROL トリガーを編集]** をクリックします。

   ![&#x200B; 変更 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. ルールビルダーで「**[!UICONTROL アプリケーションの起動]**」をクリックし、ドロップダウンから「*Platform にデータを送信*」を選択します。
   ![&#x200B; データプラットフォームに送信 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. 「**[!UICONTROL 条件を追加]**」をクリックして条件を追加します。

   ![&#x200B; 条件を追加ボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. **[!UICONTROL 特性を選択]** ドロップダウンから、「**[!UICONTROL XDM イベントタイプ]**」を選択します。

   ![XDM イベントタイプ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. 次のテキストフィールドに、覚えやすい *`<custom string value>`* を追加します。

1. 値を保存するには、「**[!UICONTROL &#x200B; 追加**]」をクリックし `<custom string value>` す。

   このカスタム文字列値は、後でメッセージを発生させるために使用されます。

   >[!TIP]
   > シート番号をカスタム文字列値に追加すると、シート番号が一意になり、覚えやすくなります。
   > 
   > 例：`99exerciseTrigger`

   ![&#x200B; カスタムトリガー文字列値を追加 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. 右上の **[!UICONTROL 完了]** をクリックします。

>[!SUCCESS]
>
>これで、カスタムトリガーイベントを使用してアプリ内メッセージを定義しました。
>
>![&#x200B; カスタムトリガーが定義されたキャンペーン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 アプリ内メッセージのコンテンツを編集する

「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL コンテンツを編集]**」をクリックします。

![&#x200B; コンテンツを編集ボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

[!UICONTROL &#x200B; アプリ内メッセージ &#x200B;] エディターが表示され、アプリ内メッセージコンテンツを設定できます。

#### 2.3.3.1 Layout

メッセージに適用するレイアウトを選択します。

例えば、「**[!UICONTROL モーダル]**」をクリックして、アプリ内メッセージをモーダルレイアウトにします。

![&#x200B; モーダルボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 メッセージのオーサリングとキャンペーンの公開

1. 「メディア」セクションで、次の URL をペーストします。`https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
値フィールドの外をクリックすると、画像が表示されます。

   ![&#x200B; プレビューに表示されるメディア &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-media.png)

2. 次の **[!UICONTROL コンテンツ]** セクションで、メッセージに表示する **[!UICONTROL ヘッダー]** と **[!UICONTROL 本文]** 独自のカスタムテキストを追加します。

   ![&#x200B; ヘッダーと本文 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-content.png)

3. その他のオプション：
   1. **ボタン：**

      ![&#x200B; ボタンセクション &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. エディターのこのセクションでは、「ボタンテキスト」フィールドを編集して、「CTA」ボタンのテキストをカスタマイズできます。

      2. **[!UICONTROL インタラクトイベント]** フィールドは、ユーザーがCTAを押したときにSDKに渡される値を定義するために使用されます。

      3. **[!UICONTROL Target]** フィールドは、CTAでユーザーを取得する場所を定義するために使用されます。 これには、URL とディープリンクが含まれます。 例えば、このディープリンクを `dxdemo://exoticVibes` などの製品ページに追加できます。

      4. **[!UICONTROL +追加ボタン]** キーを押して、追加のボタンを追加できます。

      5. メッセージに 2 つ目のボタンが追加されると、ドロップダウンボックスでボタンのレイアウトを変更できるようになりました。


   2. **詳細フォーマット**

      ![&#x200B; 詳細フォーマットの切替スイッチ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      この切替スイッチを有効にすると、エディターに追加のカスタマイズオプションが提供されます。

      1. メディアサイズ
      1. フォント
      1. Pt サイズ
      1. フォントカラー
      1. 整合性

      ![&#x200B; 詳細フォーマットオプション &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **「設定」タブ**

      このタブと「**[!UICONTROL プレビュー]**」セクションに移動すると、**アプリのプレビュー** を変更できます。
      <br>\
      ![&#x200B; 「設定」タブ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. 「**[!UICONTROL レイアウト]**」セクションでは、画像を背景として使用するか、単色で使用するかを選択できます。

      2. 「**[!UICONTROL メッセージ]**」セクションでは、メッセージに対して有効にできるカスタムインタラクションを提供します。
         1. カスタムジェスチャー
         2. UI テイクオーバー
         3. カスタム UI テイクオーバー
         4. カスタムサイズ
         5. カスタム位置
         6. カスタムアニメーション
         7. 角を丸めたメッセージ
   <br>
4. コンテンツのオーサリングが完了し、メッセージに満足したら、「**[!UICONTROL アクティブ化するレビュー &#x200B;] ボタン** をクリックします。

   >[!SUCCESS]
   >
   > これで、モバイルのアプリ内メッセージのオーサリングが完了しました。 これで、キャンペーン **[!UICONTROL アクティブ化するレビュー]** ページが表示されます。
   >
   >![&#x200B; レビューとアクティブ化 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > ここでは、メッセージの完全な概要を確認できます。
   >
   > *トリガールールとして使用したカスタム値をメモしてください。 この値は、アプリ内メッセージの実行に使用されます。 使用される値は、概要ページのハイライト領域にあります。*

   >[!NOTE]
   >アプリ内メッセージの現在のトリガーはデフォルトの **アプリケーション起動イベントが発生する** です。つまり、アプリの起動時にアプリ内メッセージがトリガーされます。 これは **[!UICONTROL スケジュール セクション]** で確認できます。

5. キャンペーンのレビューが完了したら、「アクティブ化」ボタンを押してキャンペーンを公開します。
   <br>
   ![&#x200B; アクティベート &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> これで、キャンペーン ダッシュボードが表示されます。 スクロールするか、検索機能を使用して、キャンペーンを見つけます。 キャンペーンのステータスが **[!UICONTROL ライブ]** （約 1 分）に変更されると、キャンペーンが公開されました。
>
> ![&#x200B; 公開済みキャンペーン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## 演習 2.4：モバイルのアプリ内メッセージのトリガー

ペイロードを更新し、新しく公開したキャンペーンをダウンロードするには：

1. モバイルデバイスで、Fréscopa アプリを完全に閉じます。
2. Fréscopa アプリを再度開きます。
3. 次に、アプリの「演習」タブに移動します。

   ![&#x200B; 演習ボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. テキストフィールドに、Campaign で定義したカスタムトリガー値を入力します。 次に、「送信」を押します。


   ![&#x200B; 変更 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>「送信」をクリックすると、手動でトリガーを実行すると、作成したアプリ内通知がポップアップ表示されます。
>
>![&#x200B; アプリ内メッセージ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *メッセージのトリガーに関する問題が発生した場合は、次の点を確認してください。*
> 
> * *モバイルアプリの「イベント名」フィールドで、トリガールールの値を、Campaign での値と正確に一致するように入力していることを確認します。*
> * *大文字と小文字が正しく、先頭または末尾にスペースがないことを確認します。*
> * *キャンペーンダッシュボードでキャンペーンに「戻る」をクリックして、キャンペーンレビューページに戻る場合、使用したトリガールール値を検索できます。*

最初のJourney Optimizerのアプリ内メッセージを作成して公開しました。


## ボーナス演習：デバイスでのキャンペーンとプレビューの複製

**キャンペーンの複製** および **デバイスでプレビュー** 機能は標準搭載され、キャンペーンの複製や、アクティブ化する前にデバイスで直接アプリ内メッセージをテストおよびレビューできます。 この演習では、この機能の使用方法と、演習 3.1 で作成したメッセージのプレビュー方法を説明します。

1. キャンペーンダッシュボードページでキャンペーンの名前をクリックして、作成したキャンペーンを開きます。 これにより、「キャンペーンをレビュー **[!UICONTROL ページに戻]** ます。
1. **[!UICONTROL 複製ボタン]** を押します。 これにより、新しいプロンプトが開き、複製中の新しいキャンペーンに名前を付けることができます。 覚えやすい新しい名前を追加するか、デフォルトで追加されるデフォルトの名前 **[!DNL _copy]** 使用します。

   ![&#x200B; キャンペーンを複製 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. 「複製」ボタンをクリックすると、複製キャンペーンが作成され、キャンペーンダッシュボードに戻ります。
1. キャンペーンが複製されたら、新しいキャンペーンを開きます。

1. **[!UICONTROL キャンペーンレビュー]** ページまたは **[!UICONTROL キャンペーンオーサー]** 手順のデバイスでプレビュー機能にアクセスできます。

   ![&#x200B; デバイスでプレビューボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. 次に、デバイスに接続画面から **[!UICONTROL 開始ボタン]** をクリックします。

   ![&#x200B; 開始ボタン &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Fréscopa アプリを起動するように設定されているベース URL を入力します：`dxdemo://`

   ![&#x200B; プレビュー url](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. 画面に表示される指示に従います。
   1. モバイルデバイスで QR コードをスキャンすると、Fréscopa アプリが開き、ピンを入力できる画面が表示されます。
   2. デバイスのAssurance画面でAJOに表示されているピンを入力し、ピンを入力したら右下に表示される「接続」ボタンをクリックします。


   ![&#x200B; ピン留めを入力 &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. このポップアップは、コンピューター画面に表示されます

   ![&#x200B; ポップアップ &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-pop-up.png)

1. 「完了」ボタンをクリックします。 これにより、ダイアログボックスが閉じ、電話がデバイスのプレビューに接続されます。


>[!SUCCESS]
>
> アプリ内メッセージがデバイスに表示されます。
>
> *接続するたびにアプリ内メッセージが表示されるので、「**[!UICONTROL デバイスでプレビュー &#x200B;]」ボタンをクリックします**。

## その他のリソース

**ビデオガイド：**

* [アプリ内キャンペーンを作成](/help/channels/create-an-in-app-campaign.md)
* [アプリ内メッセージの作成](/help/channels/author-in-app-messages.md)

**製品ドキュメント：**

* [&#x200B; アプリ内チャネルの概要 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/get-started-in-app)
* [&#x200B; モバイルのアプリ内メッセージの作成 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/create-in-app)
* [アプリ内コンテンツのデザイン](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/design-in-app)
* [&#x200B; アプリ内通知の確認と送信 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/send-in-app)
