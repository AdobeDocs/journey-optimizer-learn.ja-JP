---
title: Adobe Web SDKを使用したAdobe Journey Optimizerジャーニーのトリガー
description: Adobe Experience Platform タグを通じて設定されたAdobe Journey Optimizer Web SDKを利用して、ユーザーログインなどのサイトイベントからAEP ジャーニーを開始する方法を説明します
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-19287
source-git-commit: 6927cade07790603e711f4e6e4c3f6982a56e6f5
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# Adobe Web SDKを使用したAdobe Journey Optimizerジャーニーのトリガー

ID ステッチチュートリアルのこの拡張機能では、Adobe Journey Optimizer ジャーニーがトリガーされ、ステッチされたプロファイルを使用してログインユーザーにメールが送信されます。 **この記事は、メールチャネルと、メールチャネルのコンテンツの作成に精通していることを前提としています。**

## メールチャネル設定の作成

* _&#x200B;**Journey Optimizer**&#x200B;_ にログインします
* _&#x200B;**管理/チャネル/チャネル設定を作成**&#x200B;_ に移動します。
* チャネルリストから **メール** を選択します。 意味のある名前と説明を指定します。
* メール設定を入力します。
* 以下に示すように、実行の詳細を指定します。 メールは、フィールドに保存されたプロファイルのメールアドレスに送信されます
* ![&#x200B; メールチャネル &#x200B;](assets/email-channel-execution.png)
* メールチャネル設定のアクティベート

## イベントを作成

* _&#x200B;**Journey Optimizer**&#x200B;_ にログインします
* _&#x200B;**管理/設定**&#x200B;_ に移動します。
* イベントカードの「管理」ボタンをクリックし、「イベントを作成」をクリックします。 次に示すように値を指定します
* ![journey-event](assets/journey-event1.png)

* イベントの eventType が LoginEvent に等しいかどうかを確認します。 `LoginEvent` のタイプは、Adobe Experience Platform タグで設定されます。
* イベントを保存

## ジャーニーを作成

* _&#x200B;**Journey Optimizer**&#x200B;_ にログインします
* _&#x200B;**ジャーニー管理/ジャーニー/ジャーニーを作成**&#x200B;_ に移動します。
* _&#x200B;**UserLoggedIn**&#x200B;_ イベントをキャンバスにドラッグ&amp;ドロップします
* アクション メニューからメールをドラッグ&amp;ドロップします。 前に作成したメールチャネル設定を使用するようにメールアクションを設定します。
* ジャーニーを公開します。

## ジャーニーのトリガー方法

Web SDK経由で送信されたイベントペイロードが、ジャーニーで設定されたものと一致すると、ジャーニーがトリガーされます。 この例では、イベントはイベントタイプ `UserLoggedIn` `LoginEvent` です。

* ジャーニーレポートを表示して、これを確認します
* ![&#x200B; ジャーニーレポート &#x200B;](assets/journey-triggered-report.png)




