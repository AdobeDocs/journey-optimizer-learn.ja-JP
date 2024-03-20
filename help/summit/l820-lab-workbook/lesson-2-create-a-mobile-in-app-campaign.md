---
title: レッスン 2 — モバイルアプリ内キャンペーンの作成
description: モバイルアプリ内キャンペーンを作成し、トリガーします。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
source-git-commit: c509c768d07984d07ed2ec65634e000c54bb6ff1
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 0%

---


# レッスン 2 — モバイルアプリ内キャンペーンの作成

このレッスンでは、モバイルアプリ内メッセージを作成してトリガーを設定します。

## 学習内容

* アプリ内メッセージがトリガーされる方法を理解します。
* モバイルアプリ内キャンペーンの作成方法を説明します。
* トリガーとアプリ内メッセージ。

## 演習 2.1 - Journey Optimizerにログインする

1. 開く [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. 次の詳細を使用してログインします。
   <br>
   **ユーザー名：** L820 以降&#x200B;**`<your seat number>`**@adobeeventlab.com
   **パスワード：**   ADOBE2024!
   <br>
ログインの詳細は、ラボマシンのデスクトップで確認できます。 「 Adobe ID 」と「パスワード」を使用します。
   ![デスクトップ](/help/summit/l820-lab-workbook/assets/desk-top.png)

   ![ログイン画面](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. 次の 2 つの画面をスキップできます。
   <br>
   ![電話番号](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![パーソナライゼーションポップアップ](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Journey Optimizerおよびホームページにログインする必要があります。
>
>![AJO ホームページ](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## 演習 2.2 モバイルアプリ内キャンペーンの作成

この演習では、アプリを開いたときにトリガーされるアプリ内メッセージキャンペーンを作成します。

1. Journey Optimizerの左側のナビゲーションで、「 」を選択します。 **[!UICONTROL キャンペーン]**.

1. クリック **[!UICONTROL キャンペーンを作成]**.

   ![キャンペーンを作成](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. 次の日： **[!UICONTROL キャンペーンを作成]** ページの  **[!UICONTROL アクション]** セクションで、 **[!UICONTROL アプリ内メッセージ]** 」チェックボックスをオンにします。

1. 次から： **[!UICONTROL 送信先]** ドロップダウン、選択 **[!DNL Mobile]**.

1. 次から： **[!UICONTROL アプリサーフェス]** ドロップダウン、選択 **[!DNL Frecopa Mobile App]**.

1. 「**[!UICONTROL 作成]**」をクリックします。

   ![アプリサーフェス](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>これで、Campaign プロパティが表示されます。
>
> ![キャンペーンのプロパティ](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## 演習 2.3 キャンペーンの設定

### 2.3.1 [!UICONTROL 「プロパティ」セクション]

キャンペーンに名前を付けます。 名前は必ずシート番号で始めてください。これにより、キャンペーンを再度見つけやすくなります。

例えば、シート番号が 99 の場合：  `99 - Welcome Campaign`.

![プロパティセクション](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 カスタムトリガールールの設定

1. 下にスクロールして、 **[!UICONTROL トリガーセクション]**&#x200B;を選択し、次に **[!UICONTROL 編集トリガー]**.

   ![変更](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. ルールビルダーで、「 **[!UICONTROL アプリケーションの起動]** また、ドロップダウンから  *データをプラットフォームに送信*.
   ![データプラットフォームに送信](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. クリックして条件を追加 **[!UICONTROL 条件を追加]**.

   ![条件追加ボタン](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. 次から： **[!UICONTROL 特性を選択]** ドロップダウン、「 」を選択します。 **[!UICONTROL XDM イベントタイプ]**.

   ![XDM イベントタイプ](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. 次のテキストフィールドに、 *`<custom string value>`* 覚えていると思います

1. 値を保存するには、**[!UICONTROL 追加**] `<custom string value>`.

   このカスタム文字列値は、後でメッセージを送信するために使用されます。

   >[!TIP]
   > カスタム文字列の値にシート番号を追加すると、一意になり、覚えやすくなります。
   > 
   > 例：`99exerciseTrigger`

   ![カスタムトリガーー文字列値を追加](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. クリック **[!UICONTROL 完了]** を右上に表示します。

>[!SUCCESS]
>
>これで、アプリ内メッセージをカスタムメッセージイベントで定義しましたトリガー。
>
>![定義済みのカスタムトリガーのキャンペーン](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 アプリ内メッセージのコンテンツの編集

Adobe Analytics の **[!UICONTROL アクション]** セクションで、 **[!UICONTROL コンテンツを編集]**.

![コンテンツ編集ボタン](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

The [!UICONTROL アプリ内メッセージ] エディターが表示され、アプリ内メッセージコンテンツを設定できます。

#### 2.3.3.1 レイアウト

メッセージに適用するレイアウトを選択します。

例えば、「 **[!UICONTROL モーダル]** アプリ内メッセージをモーダルレイアウトにする場合。

![モーダルボタン](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 メッセージのオーサリングとキャンペーンのパブリッシュ

1. メディアセクションで、次の URL に貼り付けます。  `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
値フィールドの外をクリックすると、画像が表示されます。

   ![プレビューに表示されるメディア](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. 次の場合： **[!UICONTROL コンテンツ]** セクションで、メッセージに表示するカスタムテキストを **[!UICONTROL ヘッダー]** および **[!UICONTROL 本文]**.

   ![ヘッダーと本文](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. その他のオプション：
   1. **ボタン：**

      ![ボタンセクション](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. エディターのこのセクションでは、「ボタンテキスト」フィールドを編集して、CTA ボタンのテキストをカスタマイズできます。

      2. The **[!UICONTROL Interact イベント]** フィールドは、CTA がユーザーに押されたときに SDK に渡される値を定義するために使用されます。

      3. The **[!UICONTROL Target]** フィールドは、CTA がユーザーを取得する場所を定義するために使用されます。 これには、URL やディープリンクが含まれます。 例えば、このディープリンクを製品ページ ( `dxdemo://exoticVibes`.

      4. ボタンを追加するには、 **[!UICONTROL +「追加」ボタン]**.

      5. メッセージに 2 つ目のボタンが追加されると、ドロップダウンボックスを使用してボタンのレイアウトを変更するオプションが追加されます。


   2. **詳細フォーマット**

      ![詳細フォーマット切り替え](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      この切り替えを有効にすると、エディターで追加のカスタマイズオプションが表示されます。

      1. メディアサイズ
      1. フォント
      1. Pt サイズ
      1. フォントカラー
      1. 整列

      ![詳細書式設定オプション](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **「設定」タブ**

      このタブに移動し、 **[!UICONTROL プレビュー]** セクションで、 **アプリのプレビュー**.
      <br>\
      ![「設定」タブ](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. The **[!UICONTROL レイアウト]** 「 」セクションでは、画像を背景またはべた塗りの色として使用できます。

      2. The **[!UICONTROL メッセージ]** 「 」セクションには、メッセージに対して有効にできるカスタムインタラクションが用意されています。
         1. カスタムジェスチャー
         2. UI テイクオーバー
         3. カスタム UI テイクオーバー
         4. カスタムサイズ
         5. カスタム位置
         6. カスタムアニメーション
         7. メッセージの丸い角
   <br>
4. コンテンツのオーサリングが完了し、メッセージに満足したら、 **[!UICONTROL 有効化するレビュー] ボタン**.

   >[!SUCCESS]
   >
   > これで、モバイルアプリ内メッセージのオーサリングが完了しました。 これで、キャンペーンに移動します。 **[!UICONTROL 有効化するレビュー]** ページに貼り付けます。
   >
   >![レビューとアクティブ化](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > ここで、メッセージの完全な概要を確認できます。
   >
   > *トリガールールとして使用したカスタム値を控えておいてください。 この値は、アプリ内メッセージの実行に使用されます。 使用された値は、概要ページのハイライト領域にあります。*

   >[!NOTE]
   >アプリ内メッセージの現在のトリガーがデフォルトです **アプリケーション起動イベントが発生します**：アプリが起動したときにアプリ内メッセージがトリガーされます。 これは、 **[!UICONTROL 「スケジュール」セクション]**.

5. キャンペーンのレビューが完了したら、「アクティブ化」ボタンを押して、キャンペーンを公開します。
   <br>
   ![アクティブ化](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> これで、キャンペーンダッシュボードが表示されます。 スクロールまたは検索機能を使用してキャンペーンを見つけます。 キャンペーンのステータスが「 **[!UICONTROL ライブ]** （約 1 分）、キャンペーンが公開されました。
>
> ![公開済みキャンペーン](/help/summit/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## 演習 2.4 モバイルアプリ内メッセージのトリガー

ペイロードを更新し、新しく公開したキャンペーンをダウンロードするには：

1. モバイルデバイスで、Fréscopa アプリを完全に閉じます。
2. Fréscopa アプリを再度開きます。
3. 次に、デスクトップアプリケーションの「演習」タブに移動します。

   ![「演習」ボタン](/help/summit/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. テキストフィールドに、Campaign で定義したカスタムトリガー値を入力します。 次に、「送信」を押します。


   ![変更](/help/summit/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>「送信」をクリックすると、手動でトリガーが発生し、作成したアプリ内通知がポップアップ表示されます。
>
>![アプリ内メッセージ](/help/summit/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *メッセージをトリガーする際に問題が発生した場合は、以下を確認してください。*
> 
> * *モバイルアプリの「トリガー名」フィールドに、Campaign でのイベントルールの値と完全に一致する値を入力していることを確認します。*
> * *大文字と小文字が正しいこと、および先頭または末尾のスペースがないことを確認します。*
> * *キャンペーンダッシュボードで「キャンペーンに戻る」をクリックして「キャンペーンのレビュー」ページに戻った場合に使用したトリガールール値を検索できます。*

最初のJourney Optimizerアプリ内メッセージを作成して公開しました。


## ボーナス演習：デバイスでのキャンペーンとプレビューの複製

The **キャンペーンを複製** および **デバイスでプレビュー** 機能は、標準搭載の機能で、キャンペーンを複製し、アプリ内メッセージをアクティブ化する前に、デバイス上で直接テストして確認できます。 この練習では、この機能の使用方法と、演習 3.1 で作成したメッセージのプレビュー方法を学習します。

1. 作成したキャンペーンを開きます。開くには、キャンペーンダッシュボードページでキャンペーンの名前をクリックし、キャンペーンを開きます。 これにより、 **[!UICONTROL キャンペーンのレビュー]** ページに貼り付けます。
1. を押します。 **[!UICONTROL 複製ボタン]**. これにより、複製中の新しいキャンペーンに名前を付ける新しいプロンプトが開きます。 覚えやすい新しい名前を追加するか、デフォルト名を使用します。 **[!DNL _copy]** はデフォルトで追加されます。

   ![キャンペーンを複製](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. 複製ボタンを押すと、複製キャンペーンが作成され、キャンペーンダッシュボードに戻ります。
1. キャンペーンが複製されたら、新しいキャンペーンを開きます。

1. デバイスでのプレビュー機能には、 **[!UICONTROL キャンペーンレビュー]** ページまたは **[!UICONTROL キャンペーン作成者]** 手順

   ![「デバイスでプレビュー」ボタン](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. 次に、 **[!UICONTROL 開始ボタン]** デバイスに接続画面から。

   ![開始ボタン](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Fréscopa アプリを起動するように設定されたベース URL を入力します。 `dxdemo://`

   ![url をプレビュー](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. 画面の指示に従います。
   1. モバイルデバイスで QR コードをスキャンすると、Fréscopa アプリが開き、画面が表示され、ピンを入力できます。
   2. お使いのデバイスのアシュランス画面で AJO に表示されるピンを入力し、ピンを入力したら右下に表示される「接続」ボタンをクリックします。


   ![ピンを入力](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. このポップアップは、お使いのコンピューターの画面に表示されます

   ![ポップアップ](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. 「完了」ボタンをクリックします。 これによりダイアログボックスが閉じ、携帯電話がデバイスのプレビューに接続されます。


>[!SUCCESS]
>
> デバイスにアプリ内メッセージが表示されます。
>
> *接続すると、毎回アプリ内メッセージが表示され、**[!UICONTROL デバイスでプレビュー] ボタン**.*