---
title: Adobe Experience Platform タグの作成
description: ユーザーの投資環境設定（株式、債券、CD）に基づくAJO オーディエンスの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 2%

---


# AEP タグの作成

Adobe Experience Platform Tags （旧称Adobe Launch）は、サイトのコードを変更しなくても、web サイトでマーケティングおよび分析テクノロジーを管理してデプロイするのに役立ちます。

この [ ビデオでは、Adobe Experience Tags の作成プロセスを説明し ](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags) す。

* データ収集へのログイン
* タグ/新しいプロパティをクリックします。
* Financial Advisors というAdobe Experience Platform タグを作成します。

* タグに次の拡張機能を追加します
  ![tags-extensions](assets/tags-extensions.png)

* 前の手順で作成した正しい環境とファイナンシャル・アドバイザのデータ・ストリームを使用するように、Adobe Experience Platformの WebSDKを必ず構成してください。
  ![web-sdk-configuration](assets/web-sdk-configuration.png)

* Adobe Client Data Layer および Core Extensions の設定は不要です

## データ要素の作成

データ要素は、web ベースのマーケティングおよび広告テクノロジー全体でデータを収集、整理、配信するために使用されます。

次のデータ要素を作成します

| 要素名 | 拡張機能 | データ要素タイプ | 追加のコメント |
|------------------------------|-----------------------------------|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 優先金融商品 | コア | カスタムコード | 以下のメモを参照してください |
| XDM オブジェクト | Adobe Experience Platform Web SDK | XDM オブジェクト | 環境およびファイナンシャル・アドバイザ・スキーマの選択 |


カスタムコードの場合は、コードエディターを開き、次のコードをコピー&amp;ペーストします

```javascript
return window.adobeDataLayer
  ?.slice()
  .reverse()
  .find(event => event.event === "assetClassSelection")
  ?.xdm?.FinancialInterest?.PreferredFinancialInstrument || "undefined";
```

## コードの説明

adobeDataLayer 配列（web ページで発生するイベントを保存する）を見ます。

元の配列が変更されないように、.slice （）を使用して配列のコピーを作成します。

イベントの順序を逆にして、最新のイベントを最初に確認します。

event.event が正確に「assetClassSelection」である最初のイベント（新しいイベントから開始）を見つけます。

見つかった場合は、そのイベントの xdm データに移動し、FinancialInterest.PreferredFinancialInstrument から値を取得します。

何も見つからない場合は、文字列「undefined、」



## ルールを作成

Adobe Experience Platform タグのルールビルダーを使用すると、ユーザーの行動やイベントに基づいて、web サイトで特定のアクションを実行するタイミングと方法を定義できます。

* 優先金融商品の送信という名前のルールを作成します。 このルールには、イベントとアクションが含まれています


* 次に示すように、「優先アセットクラスを選択」という名前のイベント設定を作成します。 このイベントは、assetClassSelection イベントをリッスンします。
  ![ ルールイベント ](assets/rule-event.png)


* 更新された XDM スキーマをAEPに送信するアクションを作成
  ![send-event](assets/rule-send-event.png)

* 最終的なルールは次のようになります
  ![ 最終ルール ](assets/final-rule.png)

## AEP タグのビルドとデプロイ


新しいライブラリを作成し、以下のスクリーンショットに示すように、変更されたすべてのリソースをそのライブラリに追加します。

ライブラリを追加

![new-library](assets/tag-add-library.png)

ライブラリの作成

ライブラリを作成画面で、ライブラリ名と環境を指定します。
変更されたすべてのリソースをこのライブラリに追加する必要があります。
![tag-library](assets/tag-build-library.png)

次に、「保存して開発用にビルド」ボタンをクリックして、ライブラリをビルドします

## HTML ページにAEP タグを含める

AEP タグプロパティを公開すると、Adobeによってスクリプトタグが提供されます。スクリプトタグは、HTML ``` <head>``` 内または ``` <body>``` タグの下部に配置する必要があります。

* Tags （Financial Advisors）プロパティに移動します。

* 「環境」をクリックし、目的とする環境のインストールアイコン（開発、ステージング、実稼動など）をクリックします。

* 埋め込みコードをメモします。 これは、このチュートリアルの後半で必要になります。

