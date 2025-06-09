---
title: Adobe Experience Platform タグの作成
description: ユーザーの投資環境設定（株式、債券、CD）に基づくAJO オーディエンスの作成
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: dac6b373226bd0be2533cf859e4f250018cf568b
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# AEP タグの作成

Adobe Experience Platform Tags （旧称Adobe Launch）は、サイトのコードを変更しなくても、web サイトでマーケティングおよび分析テクノロジーを管理してデプロイするのに役立ちます。

この [ ビデオでは、Adobe Experience Tags の作成プロセスを説明し ](https://experienceleague.adobe.com/ja/playlists/experience-platform-get-started-with-tags) す。

* データ収集へのログイン
* タグ/新しいプロパティをクリックします。
* _&#x200B;**personalization-on-weather**&#x200B;_ というAdobe Experience Platform タグを作成します。

* タグに次の拡張機能を追加します
  ![tags-extensions](assets/tags-extensions1.png)

* 前の手順で作成した正しい環境と **天候関連のデータストリーム** を使用するようにAdobe Experience Platform Web SDKを設定してください。
  ![web-sdk-configuration](assets/tags-extensions.png)



## AEP タグのビルドとデプロイ


新しいライブラリを作成し、以下のスクリーンショットに示すように、変更されたすべてのリソースをそのライブラリに追加します。

**ライブラリを追加**

![new-library](assets/tag-add-library.png)

**ライブラリの作成**

ライブラリを作成画面で、ライブラリ名と環境を指定します。

変更されたすべてのリソースをこのライブラリに追加
![tag-library](assets/tag-build-library.png)

次に、「保存して開発用にビルド」ボタンをクリックして、ライブラリをビルドします

## HTML ページにAEP タグを含める

AEP タグプロパティを公開すると、Adobeによってスクリプトタグが提供されます。スクリプトタグは、HTML ``` <head>``` 内または ``` <body>``` タグの下部に配置する必要があります。

* タグ（パーソナライズ機能、天気）プロパティに移動します。

* 「環境」をクリックし、目的とする環境のインストールアイコン（開発、ステージング、実稼動など）をクリックします。

* 埋め込みコードをメモします。 これは、このチュートリアルの後半で必要になります。
