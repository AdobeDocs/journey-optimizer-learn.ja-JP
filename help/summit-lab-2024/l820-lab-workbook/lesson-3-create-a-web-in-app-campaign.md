---
title: レッスン 3 - web アプリ内キャンペーンの作成
description: web アプリ内キャンペーンの作成とトリガー。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
exl-id: 0f84adfb-edb1-47fa-b696-58eec2b33bb1
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
source-wordcount: '778'
ht-degree: 5%
---
# レッスン 3 - Web アプリ内キャンペーンの作成

このレッスンでは、アプリのモバイル体験を作成したので、Fréscopaのweb サイトで見た体験の1つを作成しました。 Web アプリ内キャンペーンを作成します。 メッセージをデザインおよびカスタマイズし、メッセージを実行するトリガーを定義します。

## 学習目標

* Web アプリ内キャンペーンの作成方法について説明します。
* アプリ内メッセージをトリガーします。

## 演習3.1 web アプリ内キャンペーンの作成

この演習では、キャンペーンを作成し、アプリ内メッセージが表示されるweb ページを定義します。

1. Journey Optimizerの左側のナビゲーションで、**キャンペーン管理**&#x200B;の下の「**ジャーニー**」を選択します。

1. 「**キャンペーンを作成**」をクリックします。

   ![CreateCampaign](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-create-campaign.png)

1. **キャンペーンを作成** ページの&#x200B;**アクション** セクションで、**アプリ内メッセージ** チェックボックスを選択します。

1. **送信先** ドロップダウンから、**Web.**&#x200B;を選択します。

1. 次のURLを入力します。**https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *メッセージが表示されるweb ページです。*

   ![&#x200B; アプリ内URL](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. 「**[!UICONTROL 作成]**」をクリックします。

## 演習3.2 キャンペーンの設定

このページでは、キャンペーンのプロパティと、アプリ内メッセージをトリガーしてweb ページに表示するイベントを定義します。 その他の設定はすべてデフォルトのままにします。 この演習では、特定のオーディエンスを定義する必要はありません。

### 3.2.1 [!UICONTROL &#x200B; プロパティセクション &#x200B;]

1. **プロパティ** セクションで、キャンペーンに一意の&#x200B;**名前**&#x200B;を指定します。

   >[!NOTE]
   > 名前は必ず座席番号で始めましょう
   > 後でキャンペーンを検索します。
   > 
   > 例えば、座席番号が99の場合： 
   >
   > ![&#x200B; プロパティ名](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 カスタムトリガールールの設定

このセクションでは、メッセージをweb サイトに表示するトリガーを定義します。 メッセージを自分だけに送ることができる固有のトリガーを定義します。

1. **[!UICONTROL トリガーセクション]**&#x200B;まで下にスクロールし、**[!UICONTROL トリガーを編集]**&#x200B;をクリックします。

   ![変更](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. ルールビルダーで、**[!UICONTROL Application Launch]**&#x200B;をクリックし、ドロップダウンから「*データをPlatform*に送信」を選択します。
   ![トリガーイベントドロップダウン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. **[!UICONTROL +条件を追加]**&#x200B;をクリックして条件を追加します。

   ![条件を追加ボタン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. **[!UICONTROL 特性を選択]** ドロップダウンから、**[!UICONTROL XDM イベントタイプ]**&#x200B;を選択します。

   ![XDM イベントタイプ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. 次のテキストフィールドに、覚えておくことができる&#x200B;*`<custom string value>`*&#x200B;を追加し、**[!UICONTROL Add]** `<custom string value>`を押して値を保存します。

   このカスタム文字列値は、後でメッセージを実行するために使用されます。

   >[!TIP]
   > カスタム文字列値に座席番号を追加すると、ユニークで覚えやすくなります。
   > 
   > 例：`99web`
   > 

   ![&#x200B; カスタムトリガー文字列値を追加](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. 右上の「**[!UICONTROL 完了]**」ボタンを押します。

>[!SUCCESS]
>
>これで、カスタムトリガーイベントを使用してweb アプリ内メッセージを定義しました。
>
>カスタムトリガーが定義された![Web キャンペーン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 アプリ内メッセージのコンテンツの編集

このセクションでは、メッセージのコンテンツ、デザイン、レイアウトを定義します。

1. 「**アクション**」セクションの「**コンテンツを編集**」ボタンをクリックして、オーサリング構成にアクセスします。

   ![&#x200B; コンテンツを編集ボタン &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. オーサリングプロセスは、上記のモバイルのアプリ内演習で完了したプロセスと同じです。 時間をかけて、独自のタイトル、本文、メディアコンテンツでメッセージを自由に編集しましょう。

   モーダルまたはフルスクリーンレイアウトを使用する場合は、ボタンを追加できます。 このURLを使用して、製品ページを開くことができます：**https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. メッセージの編集が完了したら、**[!UICONTROL レビューをクリックしてアクティブ化します]**。

1. レビュー画面ですべてが正常に表示された場合は、**[!UICONTROL アクティベート]**&#x200B;をクリックしてWeb アプリ内メッセージを公開します。

1. キャンペーンダッシュボードに戻ります。

   4.1.4に移行する前に、キャンペーンステータスが&#x200B;**Live**&#x200B;に変更されるのを待ちます。

## 演習3.3 web アプリ内メッセージのトリガー

1. FréscopaのWeb サイトに移動し、ブラウザーの&#x200B;**演習** ページに移動します。

   ![Web演習リンク &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. 必ずweb ページを更新してください。

1. キャンペーンで定義した一意の文字列値を入力します。

   ![演習ページ &#x200B;](/help/summit-lab-2024/l820-lab-workbook/assets/4-2-exercise-page.png)

1. 「**[!UICONTROL 送信]**」をクリックします。

>[!SUCCESS]
>
>一意の値で「送信」ボタンをクリックすると、Web アプリ内メッセージがトリガーされて送信されます。 アプリ内メッセージが画面に表示されます。
>
>この演習では、Fréscopaの顧客体験を通じて見たカスタム XDM送信イベントをシミュレートしました。


## その他のリソース

**ビデオの操作方法：**

* [アプリ内キャンペーンの作成](/help/channels/create-an-in-app-campaign.md)
* [アプリ内メッセージを作成](/help/channels/author-in-app-messages.md)

**製品ドキュメント：**

* [アプリ内チャネルの基本を学ぶ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Web アプリ内メッセージの作成](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/create-in-app-web)
* [アプリ内コンテンツのデザイン](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/design-in-app)
* [アプリ内通知の確認および送信](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/in-app/send-in-app)
