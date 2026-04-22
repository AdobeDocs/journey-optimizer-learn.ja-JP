---
title: キャンペーンを作成
description: Create a campaign to target users who have opted in to receive push notifications and delivers the message at the scheduled time.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%

---

# Create Campaign

In this step, you will create a campaign in Adobe Journey Optimizer to send scheduled web push notifications to users who have opted in. The campaign targets an eligible audience and delivers messages at a predefined time, enabling planned and audience-based engagement.

* Log in to Journey Optimizer
* Navigate to Journey Management | Campaigns | Create Campaigns

## Specify  Campaign Settings


Specify the campaign name

![campaign-name](assets/campign-push-notification.png)

## Associate Action with the campaign

Associate the push channel configuration created earlier in this tutorial

![campaign-action](assets/campign-push-notification-action.png)

## Associate Audience with the campaign

オーディエンス `AudienceForPush`をキャンペーンに関連付ける

![campaign-audience](assets/campign-push-notification-audience.png)

## Create content for the push notification

Create basic push content for testing the push notification. Specify title and body of the message as shown below

![content-for-push-notification](assets/campign-push-notification-content.png)

## キャンペーンのスケジュール

Schedule the campaign as per your needs

![schedule-campaing](assets/campign-push-notification-schedule.png)

Finally make sure you activate the campaign.

## Test the campaign

To test the campaign, first enable notifications on the[web page by opting in](http://localhost:3000) when prompted. オプトインしたら、キャンペーンがスケジュールされた時間に実行されるのを待ちます。 キャンペーンが実行されると、ブラウザーにプッシュ通知が届きます。




