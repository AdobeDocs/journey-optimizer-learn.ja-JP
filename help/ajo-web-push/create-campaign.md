---
title: キャンペーンを作成
description: プッシュ通知の受信をオプトインしたユーザーをターゲットにし、メッセージをスケジュールされた時間に配信するキャンペーンを作成します。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 94fda23f-e26a-494b-8e5c-6c442bae61c4
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%

---

# キャンペーンを作成

この手順では、Adobe Journey Optimizerでキャンペーンを作成し、オプトインしたユーザーにスケジュール済みのweb プッシュ通知を送信します。 このキャンペーンは、適格なオーディエンスをターゲットとし、事前に定義された時間にメッセージを配信することで、計画されたオーディエンスベースのエンゲージメントを可能にします。

* Journey Optimizerにログインします
* ジャーニー管理に移動| キャンペーン | キャンペーンの作成

## キャンペーン設定の指定


キャンペーン名の指定

![campaign-name](assets/campign-push-notification.png)

## アクションをキャンペーンに関連付ける

このチュートリアルで先ほど作成したプッシュチャネル設定を関連付けます

![campaign-action](assets/campign-push-notification-action.png)

## オーディエンスをキャンペーンに関連付ける

オーディエンス `AudienceForPush`をキャンペーンに関連付ける

![campaign-audience](assets/campign-push-notification-audience.png)

## プッシュ通知用のコンテンツの作成

プッシュ通知をテストするための基本的なプッシュコンテンツを作成します。 次に示すように、メッセージのタイトルと本文を指定します

![content-for-push-notification](assets/campign-push-notification-content.png)

## キャンペーンのスケジュール

ニーズに応じてキャンペーンをスケジュールし

![schedule-camping](assets/campign-push-notification-schedule.png)

最後に、キャンペーンをアクティブ化します。

## キャンペーンのテスト

キャンペーンをテストするには、最初にメッセージが表示されたら[をオプトインして、](http://localhost:3000)web ページで通知を有効にします。 オプトインしたら、キャンペーンがスケジュールされた時間に実行されるのを待ちます。 キャンペーンが実行されると、ブラウザーにプッシュ通知が届きます。
