---
title: Adobe Experience Platform タグの作成
description: ユーザーの投資設定（株、債券、CD）に基づくAJO オーディエンスの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 244fcb09-3b16-4e3b-b335-4e84bc93095e
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 2%
---
# Adobe Experience Platform タグの作成

Adobe Experience Platform Tags （旧Adobe Launch）を使用すれば、サイトのコードを変更することなく、マーケティングおよび分析テクノロジーをweb サイトに管理およびデプロイできます。

この[&#x200B; ビデオでは、Adobe Experience Tags](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)の作成手順について説明します

* データ収集にログイン
* タグ/新規プロパティをクリックします
* Financial AdvisorsというAdobe Experience Platformタグを作成します。

* タグに次の拡張機能を追加します
  ![tags-extensions](assets/tags-extensions.png)

* 前の手順で作成した正しい環境とFinancial Advisors DataStreamを使用するように、Adobe Experience Platform Web SDKを構成してください。
  ![web-sdk-configuration](assets/web-sdk-configuration.png)

* Adobe Client Data LayerとCore拡張機能に追加の設定は必要ありません

## データ要素の作成

データ要素は、web ベースのマーケティングと広告テクノロジーをまたいでデータを収集、整理、配信するために使用されます。

次のデータ要素を作成します

| 要素名 | 拡張機能 | データ要素タイプ | 追加コメント |
|------------------------------|-----------------------------------|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PreferredFinancialInstrument | コア | カスタムコード | 以下のメモを参照してください |
| XDM オブジェクト | Adobe Experience Platform Web SDK | XDM オブジェクト | 環境とFinancial Advisors スキーマの選択 |


カスタムコードの場合は、コードエディターを開き、次のコードをコピー&amp;ペーストします

```javascript
return window.adobeDataLayer
  ?.slice()
  .reverse()
  .find(event => event.event === "assetClassSelection")
  ?.xdm?.FinancialInterest?.PreferredFinancialInstrument || "undefined";
```

## コード説明

adobeDataLayer配列（web ページで発生するイベントを保存する）を確認します。

元の配列が変更されないように、.slice （）を使用して配列のコピーを作成します。

イベントの順序を逆にして、最初に最新のイベントを確認します。

event.eventが正確に「assetClassSelection」である最初のイベント（最新のイベントから開始）を検索します。

見つかった場合は、そのイベントのxdm データにアクセスし、FinancialInterest.PreferredFinancialInstrumentから値を取得します。

何も見つからない場合は、「undefined」という文字列を返します。



## ルールを作成

Adobe Experience Platformのルールビルダーでは、利用者の行動やイベントにもとづいて、web サイト上で特定のアクションをいつ、どのように実行すべきかを定義できます。

* 「Send Preferred Financial Instrument」という名前のルールを作成します。 このルールには、イベントとアクションが含まれています


* 次に示すように、Preferred Asset Class Selectedという名前のイベント設定を作成します。 このイベントは、assetClassSelection イベントをリッスンします。

![rule-event](assets/rule-event.png)


* 更新されたXDM スキーマをAEPに送信するアクションを作成する

![send-event](assets/rule-send-event.png)

* 最終的なルールは次のようになります

![final-rule](assets/final-rule.png)

## AEP タグのビルドとデプロイ


以下のスクリーンショットに示すように、新しいライブラリを作成し、変更されたすべてのリソースをそれに追加します。

ライブラリを追加

![new-library](assets/tag-add-library.png)

ライブラリの作成

ライブラリの作成画面で、ライブラリ名と環境を指定します。
変更したすべてのリソースをこのライブラリに追加する必要があります
![tag-library](assets/tag-build-library.png)

次に、「保存して開発用にビルド」ボタンをクリックして、ライブラリをビルドします

## HTML ページにAEP タグを含める

AEP Tags プロパティを公開すると、AdobeはHTML ` <head>`内または`<body>` タグの下部に配置する必要があるスクリプトタグを提供します。

* Tags （Financial Advisors）プロパティに移動します。

* 「環境」をクリックし、必要な環境（開発、ステージング、実稼動など）のインストールアイコンをクリックします。

* 埋め込まれたコードをメモします。 このチュートリアルの後半の段階で必要になります。
