---
title: Adobe Experience Platform タグの作成
description: ユーザーの投資環境設定（株式、債券、CD）に基づくAJO オーディエンスの作成
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Adobe Experience Platform タグの作成

Experience Platform タグは、Adobe Experience Platform Web SDKを読み込むように Web ページに設定され、sendEvent API 呼び出しで、パーソナライズされたエクスペリエンスをトリガー化できます。 このセットアップにより、必要なクライアントサイドライブラリが正しく初期化され、オファー配信のためにAdobe Journey Optimizerとリアルタイムにやり取りできるようになります。

1. データ収集にログインします。
1. **[!UICONTROL タグ]**/**[!UICONTROL 新しいプロパティ]** をクリックします。
1. ECID サービスというAdobe Experience Platform タグを作成します。
1. タグに次の拡張機能を追加します。

   ![tags-extensions](assets/ecid-tag.png)

1. 前のチュートリアルで作成した正しい環境と Financial Advisors データ・ストリームを使用するようにAdobe Experience Platformの WebSDKを構成します

   ![web-sdk-configuration](assets/web-sdk-configuration.png)

Adobe Client Data Layer および Core Extensions の設定は不要です

## データ要素の作成

Experience Platform タグの ECID データ要素は、デバッグおよびテストのみを目的として作成されます。 データ要素を使用すると、開発者は、ユーザーのブラウザーセッションに割り当てられたExperience Cloud ID を表示できます。これにより、ID スティッチングを検証し、`sendEvent` 呼び出しが正しいプロファイルに関連付けられていることを確認できます。 この要素は、パーソナライゼーションが機能するために必要なものではありませんが、実装および QA 時に役立ちます

![ecid](assets/ecid-data-element.png)


## HTML ページにAEP タグを含める

Adobe Experience Platform タグをビルドして公開します。

AEP タグプロパティが公開されると、Adobeによってスクリプトタグが提供されます。スクリプトタグは、HTML ``` <head>``` 内または ``` <body>``` タグの下部に配置する必要があります。

1. タグ（ECID サービス）プロパティに移動します。

1. 「環境」をクリックしてから、目的とする環境のインストールアイコン（開発、ステージング、実稼動など）をクリックします。

1. 埋め込みコードをメモしておきます。

   このコードは、HTMLページの終了 ```</body>``` タグの直前に配置する必要があります。
