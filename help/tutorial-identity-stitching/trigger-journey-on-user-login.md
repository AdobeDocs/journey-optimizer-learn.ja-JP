---
title: Adobe Web SDKを使用したAdobe Journey Optimizer ジャーニーのトリガー
description: Adobe Experience Platform タグを通じて設定された AEP Web SDK を利用して、ユーザーログインなどのサイトイベントから Adobe Journey Optimizer ジャーニーを開始する方法について説明します。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-19287
exl-id: c6d4f720-3780-4012-a2bd-8eae23599144
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 10%
---
# Adobe Web SDKを使用したAdobe Journey Optimizer ジャーニーのトリガー

このID接続チュートリアルの拡張機能では、Adobe Journey Optimizer ジャーニーがトリガーされ、ログインしたユーザーにステッチされたプロファイルを使用して電子メールを送信します。 **この記事では、電子メール チャネルと、電子メール チャネル用のコンテンツの作成に精通していることを前提としています。**

## 電子メールチャネル設定の作成

* _**Journey Optimizer**_&#x200B;にログイン
* _**管理/ チャネル / チャネル設定の作成**_&#x200B;に移動します
* チャネルリストから「**電子メール**」を選択します。 意味のある名前と説明を入力します。
* メール設定を入力します。
* 以下に示すように、実行の詳細を指定します。 メールは、フィールドに保存されているプロファイルのメールアドレスに送信されます
* ![email-channel](assets/email-channel-execution.png)
* メールチャネル設定を有効にする

## イベントを作成

* _**Journey Optimizer**_&#x200B;にログイン
* _**管理 – >設定**_&#x200B;に移動します
* イベントカードの「管理」ボタンをクリックし、「イベントを作成」をクリックします。 以下に示すように、値を指定します
* ![journey-event](assets/journey-event1.png)

* イベントのeventTypeがLoginEventに等しいかどうかを確認します。 `LoginEvent` タイプはAdobe Experience Platform タグで設定されています。
* イベントを保存

## ジャーニーを作成

* _**Journey Optimizer**_&#x200B;にログイン
* _**ジャーニー管理/ジャーニー/ジャーニーを作成**_&#x200B;に移動します
* _**UserLoggedIn**_ イベントをキャンバスにドラッグ&amp;ドロップします
* アクションメニューからメールをドラッグ&amp;ドロップします。 先ほど作成したメールチャネル設定を使用するように、メールアクションを設定します。
* ジャーニーを公開します。

## ジャーニーのトリガー方法

ジャーニーは、Web SDKを介して送信されたイベントペイロードが、ジャーニーで設定されているものと一致したときにトリガーされます。 この例では、イベントは`UserLoggedIn`です。イベントタイプは`LoginEvent`です。

* ジャーニーレポートを表示して確認します
* ![ ジャーニーレポート ](assets/journey-triggered-report.png)
