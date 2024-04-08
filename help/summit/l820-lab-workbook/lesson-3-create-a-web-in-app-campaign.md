---
title: レッスン 3:Web アプリ内キャンペーンの作成
description: Web アプリ内キャンペーンを作成し、トリガーします。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
exl-id: 0f84adfb-edb1-47fa-b696-58eec2b33bb1
source-git-commit: 4f5c92f79eba3651b3633b7850e993160cb1f72c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# レッスン 3:Web アプリ内キャンペーンの作成

アプリのモバイルエクスペリエンスを作成したので、このレッスンでは、Fréscopa web サイトで見たエクスペリエンスの 1 つを作成します。 Web アプリ内キャンペーンを作成します。 メッセージをデザインおよびカスタマイズし、メッセージを実行するトリガーを定義します。

## 学習目標

* Web アプリ内キャンペーンの作成方法を理解する。
* アプリ内メッセージをトリガーします。

## 演習 3.1:web アプリ内キャンペーンの作成

この演習では、キャンペーンを作成し、アプリ内メッセージを表示する web ページを定義します。

1. Journey Optimizerの左側のナビゲーションの下の **ジャーニー管理** 選択 **キャンペーン**.

1. クリック **キャンペーンを作成**.

   ![キャンペーンを作成](/help/summit/l820-lab-workbook/assets/4-1-create-campaign.png)

1. 日 **キャンペーンを作成** ページ （内） **アクション** セクションで、 **アプリ内メッセージ** チェックボックスをオンにします。

1. から **送信先** ドロップダウン、選択 **Web。**

1. 次の URL を入力します。 **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *これは、メッセージが表示される web ページです。*

   ![アプリ内 URL](/help/summit/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. 「**[!UICONTROL 作成]**」をクリックします。

## 演習 3.2：キャンペーンの設定

このページでは、キャンペーンのプロパティと、アプリ内メッセージをトリガーして web ページに表示するイベントを定義します。 その他の設定はすべてデフォルトのままにします。 この演習では、特定のオーディエンスを定義する必要はありません。

### 3.2.1 [!UICONTROL プロパティセクション]

1. が含まれる **プロパティ** セクションで、キャンペーンに一意を指定する **名前**:

   >[!NOTE]
   > 簡単に行えるように、シート番号から名前を始めてください
   > 後でキャンペーンを見つけます。
   > 
   > 例えば、シート番号が 99 の場合： 
   >
   > ![プロパティ名](/help/summit/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 カスタムトリガールールの設定

このセクションでは、Web サイトに表示するメッセージのトリガーを定義します。 メッセージを自分専用に送信できる一意のトリガーを定義します。

1. にスクロール ダウンします。 **[!UICONTROL トリガーセクション]**&#x200B;を選択し、 **[!UICONTROL トリガーを編集]**.

   ![変更](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. ルールビルダーで、 **[!UICONTROL アプリケーションの起動]** およびドロップダウンから  *Platform にデータを送信済み*.
   ![トリガーイベントドロップダウン](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. 「」をクリックして条件を追加 **[!UICONTROL +条件を追加]**.

   ![「条件を追加」ボタン](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. から **[!UICONTROL 特性を選択]** ドロップダウンで次を選択 **[!UICONTROL XDM イベントタイプ]**.

   ![XDM イベントタイプ](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. 次のテキストフィールドに、 *`<custom string value>`* あなたが覚えていること、そして押す **[!UICONTROL 追加]** `<custom string value>` 値を保存します。

   このカスタム文字列値は、後でメッセージを発生させるために使用されます。

   >[!TIP]
   > シート番号をカスタム文字列値に追加すると、シート番号が一意になり、覚えやすくなります。
   > 
   > 例：`99web`
   > 

   ![カスタムトリガー文字列値を追加](/help/summit/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. を押します。 **[!UICONTROL 完了]** 右上の「」ボタン。

>[!SUCCESS]
>
>これで、カスタムのトリガーイベントを使用して web アプリ内メッセージを定義しました。
>
>![カスタムトリガーが定義された web キャンペーン](/help/summit/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 アプリ内メッセージのコンテンツの編集

この節では、メッセージのコンテンツ、デザイン、レイアウトを定義します。

1. 「」をクリックします **コンテンツを編集** のボタン **アクション** オーサリング構造にアクセスするには、「」セクションをクリックします。

   ![コンテンツを編集ボタン](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. オーサリングプロセスは、上記のモバイルのアプリ内演習で完了したプロセスと同じです。 自分のタイトル、本文、メディアコンテンツを使用して、メッセージを自由に編集する時間を取ります。

   モーダルまたはフルスクリーンレイアウトを使用する場合は、ボタンを追加できます。 この URL を使用して製品ページを開くことができます。 **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. メッセージの編集が完了したら、 **[!UICONTROL アクティブ化するレビュー]**.

1. レビュー画面の表示がすべてうまくいったら、 **[!UICONTROL Activate]** をクリックしてアプリ内メッセージを公開します。

1. キャンペーンダッシュボードに戻ります。

   キャンペーンのステータスが次のように変更される待機ユニット **ライブ** 4.1.4 に移行する前に以下のことを行います。

## 演習 3.3:web アプリ内メッセージのトリガー

1. Fréscopa の web サイトに移動し、 **演習** ブラウザーのページ。

   ![Web 演習リンク](/help/summit/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. Web ページを必ず更新してください。

1. キャンペーンで定義した一意の文字列値を入力します。

   ![演習ページ](/help/summit/l820-lab-workbook/assets/4-2-exercise-page.png)

1. 「**[!UICONTROL 送信]**」をクリックします。

>[!SUCCESS]
>
>一意の値で「送信」ボタンをクリックすると、web アプリ内メッセージがトリガーで実行されます。 Web アプリ内メッセージが画面に表示されます。
>
>この演習では、Fréscopa のカスタマーエクスペリエンスを通じて見たカスタム XDM 送信イベントをシミュレートしました。


## その他のリソース

**ハウツービデオ：**

* [アプリ内キャンペーンを作成](/help/channels/create-an-in-app-campaign.md)
* [アプリ内メッセージの作成](/help/channels/author-in-app-messages.md)

**製品ドキュメント：**

* [アプリ内チャネルの基本を学ぶ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Web アプリ内メッセージの作成](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app-web)
* [アプリ内コンテンツのデザイン](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [アプリ内通知の確認および送信](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
