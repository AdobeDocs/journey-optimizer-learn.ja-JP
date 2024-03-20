---
title: レッスン 3 - Web アプリ内キャンペーンの作成
description: Web アプリ内キャンペーンを作成し、トリガーします。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
source-git-commit: c509c768d07984d07ed2ec65634e000c54bb6ff1
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---



# レッスン 3 - Web アプリ内キャンペーンの作成

アプリのモバイルエクスペリエンスを作成したので、このレッスンでは、Fréscopa の Web サイトで見たエクスペリエンスの 1 つを作成します。 Web アプリ内キャンペーンを作成します。 メッセージを設計およびカスタマイズし、メッセージを実行するトリガーを定義します。

## 学習内容

* Web アプリ内キャンペーンの作成方法を説明します。
* トリガーとアプリ内メッセージ。

## 演習 3.1 Web アプリ内キャンペーンの作成

この演習では、キャンペーンを作成し、アプリ内メッセージを表示する Web ページを定義します。

1. Journey Optimizerで、左のナビゲーションで、をクリックします。 **ジャーニー管理** 選択 **キャンペーン**.

1. クリック **キャンペーンを作成**.

   ![CreateCampaign](/help/summit/l820-lab-workbook/assets/4-1-create-campaign.png)

1. 次の日： **キャンペーンを作成** ページの **アクション** セクションで、 **アプリ内メッセージ** 」チェックボックスをオンにします。

1. 次から： **送信先** ドロップダウン、選択 **Web。**

1. 次の URL を入力します。 **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *これは、メッセージが表示される Web ページです。*

   ![アプリ内 URL](/help/summit/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. 「**[!UICONTROL 作成]**」をクリックします。

## 演習 3.2 キャンペーンの設定

このページでは、キャンペーンのプロパティと、アプリ内メッセージを Web ページに表示するトリガーを設定するイベントを定義します。 その他の設定はすべてデフォルトのままにします。 この演習では、特定のオーディエンスを定義する必要はありません。

### 3.2.1 [!UICONTROL 「プロパティ」セクション]

1. Adobe Analytics の **プロパティ** セクションで、キャンペーンに固有の **名前**:

   >[!NOTE]
   > 名前は必ずシート番号で始めてください。
   > キャンペーンを後で見つけます。
   > 
   > 例えば、座席番号が 99 の場合： 
   >
   > ![プロパティ名](/help/summit/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 カスタムトリガールールの設定

このセクションでは、Web サイトに表示するトリガーを定義します。 メッセージを自分に送信できる一意のトリガーを定義します。

1. 下にスクロールして、 **[!UICONTROL トリガーセクション]**&#x200B;を選択し、次に **[!UICONTROL 編集トリガー]**.

   ![変更](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. ルールビルダーで、「 **[!UICONTROL アプリケーションの起動]** また、ドロップダウンから  *データをプラットフォームに送信*.
   ![トリガーイベントドロップダウン](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. クリックして条件を追加 **[!UICONTROL +条件を追加]**.

   ![条件追加ボタン](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. 次から： **[!UICONTROL 特性を選択]** ドロップダウン、「 」を選択します。 **[!UICONTROL XDM イベントタイプ]**.

   ![XDM イベントタイプ](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. 次のテキストフィールドに、 *`<custom string value>`* 覚えておいて、 **[!UICONTROL 追加]** `<custom string value>` をクリックして値を保存します。

   このカスタム文字列値は、後でメッセージを送信するために使用されます。

   >[!TIP]
   > シート番号をカスタム文字列値に追加すると、一意になり、覚えやすくなります。
   > 
   > 例：`99web`
   > 

   ![カスタムトリガーー文字列値を追加](/help/summit/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. を押します。 **[!UICONTROL 完了]** 」ボタンを右上に表示します。

>[!SUCCESS]
>
>これで、Web アプリ内メッセージをカスタムメッセージイベントで定義しましたトリガー。
>
>![定義済みのカスタムトリガーの Web キャンペーン](/help/summit/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 アプリ内メッセージのコンテンツの編集

このセクションでは、メッセージのコンテンツ、デザインおよびレイアウトを定義します。

1. 次をクリック： **コンテンツを編集** ボタン **アクション** セクションを開いて、オーサリング構成にアクセスします。

   ![コンテンツ編集ボタン](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. オーサリングプロセスは、上記の「モバイルアプリ内演習」で行った手順と同じです。 時間をかけて、独自のタイトル、本文、メディアコンテンツでメッセージを自由に編集します。

   モーダルレイアウトまたはフルスクリーンレイアウトを使用する場合は、ボタンを追加できます。 この URL を使用して製品ページを開くことができます。 **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. メッセージの編集が完了したら、「 **[!UICONTROL 有効化するレビュー]**.

1. レビュー画面で問題なく表示される場合は、 **[!UICONTROL 有効化]** をクリックして、Web アプリ内メッセージを公開します。

1. キャンペーンダッシュボードに戻ります。

   キャンペーンステータスが次の値に変わるまで待機する単位： **ライブ** 4.1.4 に移行する前に、以下の手順に従ってください。

## 演習 3.3 Web アプリ内メッセージのトリガー

1. Fréscopa の Web サイトに移動し、 **演習** ページをブラウザーに表示します。

   ![Web 演習リンク](/help/summit/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. Web ページを必ず更新してください。

1. キャンペーンで定義した一意の文字列値を入力します。

   ![演習ページ](/help/summit/l820-lab-workbook/assets/4-2-exercise-page.png)

1. 「**[!UICONTROL 送信]**」をクリックします。

>[!SUCCESS]
>
>固有の値で「送信」ボタンをクリックすると、Web アプリ内メッセージがトリガーされ、実行されます。 Web のアプリ内メッセージが画面に表示されます。
>
>この演習では、Fréscopa の顧客体験で確認したカスタム XDM 送信イベントをシミュレートしました。
