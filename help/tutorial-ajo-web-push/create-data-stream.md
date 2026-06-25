---
title: データストリームを作成
description: このページでは、Adobe Experience Platformでデータストリームを作成する方法を説明します。この方法は、Web SDKからデータを収集し、AEPおよびAdobe Journey Optimizerに送信するために必要です。 データストリームは、web アプリケーションとAdobe サービス間の接続として機能し、プッシュサブスクリプションとイベントデータを処理できるようにします。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: d419f6a4-67d5-46b5-9ae7-5a317300d1ad
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# データストリームを作成

Adobe Experience Platform（AEP）のデータストリームは、Web SDKから送信されたデータを受け取るエンドポイントとして機能します。 このデータは、AEP、Adobe Analytics、Adobe Journey Optimizerなどの設定済みサービスにルーティングされます。 このチュートリアルでは、データストリームを使用して、web プッシュのサブスクリプションデータとprice.drop イベントをAEPに送信し、アクティベーションします。

## プッシュ通知を追跡するためのイベントスキーマの作成

`SchemaForPushNotification`という名前の新しいXDM ExperienceEvent スキーマを作成します。 このスキーマに`Push Notification Tracking`および`Commerce Details` フィールドグループを追加します。 Commerceの詳細フィールドグループのフィールドを使用して、商品情報を取得し、price.drop カスタムイベントをトリガーします。

![event-schema](assets/event-schema.png)

## プロファイルスキーマを作成してユーザーの同意を保存する

このチュートリアルでは、標準の`AJO Push Profile Schema`を使用します。 このスキーマは、web プッシュ通知の配信に必要なプッシュトークンを含む、ユーザーのプッシュ購読の詳細を保存します。

![profile_schema](assets/profile-schema.png)

## スキーマのデータセットの作成

以前に作成したイベントスキーマを使用して、`DataSetForPushNotification`という名前のデータセットを作成します。 プロファイルデータの場合は、プッシュプロファイルスキーマに関連付けられている、標準の`AJO Push Profile Dataset`を使用します。 チュートリアルの後半で.env ファイルを使用してアプリケーションを設定する際に必要になるので、`DataSetForPushNotification` IDをメモしてください。

## イベントおよびプロファイルデータセットを使用したデータストリームの作成

前の手順で作成したイベントおよびプロファイルデータセットを使用して、WebPushDataStreamという名前の新しいデータストリームを作成します。 チュートリアルの後半で.env ファイルを使用してアプリケーションを設定する際に必要になるので、データストリーム IDをメモしておきます。

![&#x200B; データストリーム &#x200B;](assets/datastream.png)
