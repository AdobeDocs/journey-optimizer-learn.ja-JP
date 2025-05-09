---
title: Adobe Experience Platform タグの作成
description: ユーザーの投資環境設定（株式、債券、CD）に基づくAJO オーディエンスの作成
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
source-git-commit: 2ca9ffee1a2326b8ae55a8e8de496a632fea79c8
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Adobe Experience Platformを作成

Adobe Launch は、Adobe Experience Platform Web SDKを読み込むように Web ページに設定され、sendEvent API 呼び出しで、パーソナライズされたエクスペリエンスをトリガー化できます。 このセットアップにより、必要なクライアントサイドライブラリが正しく初期化され、オファー配信のためにAdobe Journey Optimizerとリアルタイムにやり取りできるようになります。

* データ収集へのログイン
* タグ/新しいプロパティをクリックします。
* ECID サービスというAdobe Experience Platform タグを作成します。

* タグに次の拡張機能を追加します
  ![tags-extensions](assets/ecid-tag.png)

* 前のチュートリアルで作成した正しい環境とファイナンシャル・アドバイザのデータ・ストリームを使用するように、Adobe Experience Platformの WebSDKを必ず構成してください
  ![web-sdk-configuration](assets/web-sdk-configuration.png)

* Adobe Client Data Layer および Core Extensions の設定は不要です

## データ要素の作成

Adobe Launch の ECID データ要素は、デバッグおよびテストのみを目的として作成されます。 これにより、開発者は、ユーザーのブラウザーセッションに割り当てられたExperience Cloud ID を表示できます。これにより、ID スティッチングを検証し、sendEvent 呼び出しが正しいプロファイルに関連付けられていることを確認できます。 この要素は、パーソナライゼーションが機能するために必要なものではありませんが、実装および QA 時に役立ちます

![ecid](assets/ecid-data-element.png)


## HTML ページにAEP タグを含める

Adobe Experience Platform タグのビルドと公開

AEP タグプロパティが公開されると、Adobeによってスクリプトタグが提供されます。スクリプトタグは、HTML ``` <head>``` 内または ``` <body>``` タグの下部に配置する必要があります。

* タグ（ECID サービス）のプロパティに移動します。

* 「環境」をクリックし、目的とする環境のインストールアイコン（開発、ステージング、実稼動など）をクリックします。

* 埋め込みコードをメモします。 このコードは、HTMLページの終了 ```</body>``` タグの直前に配置する必要があります。
