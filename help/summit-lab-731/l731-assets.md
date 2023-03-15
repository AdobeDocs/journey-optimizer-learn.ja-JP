---
title: L731 チートシート
description: このページには、L731 サミットラボで使用されているテキストとリンクが含まれています。
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: 8e9f7460410a117031598096d81eabd3090647af
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 39%

---

# サミットラボ L731  — チートシート

このページには、L731 Summit Lab で使用されているテキストとリンクが含まれています。 これらを使用して、コンテンツをコピーし、Journey Optimizerメッセージに貼り付けることができます。

## 演習 1.1 — アプリケーションのダウンロードとインストール

QR コードをスキャンしてアプリをダウンロード

>[!BEGINTABS]

>[!TAB iOS]

![iOSの QR コード](/help/assets/lab731-ios-qr-code.png)

Testflight をインストールするように求められます。 Testflight をインストールしたら、次の手順に従って Vegas Stay App をインストールします。

![iOSのインストール手順](/help/assets/lab731-install-ios.png)

>[!TAB Android™]

![Android 用の QR コード](/help/assets/lab731-android-qr-code.png)

Android シミュレーターを使用している場合は、次のリンクを使用します。 [https://ajolab.s3.amazonaws.com/ajolabapp-release.apk](https://ajolab.s3.amazonaws.com/ajolabapp-release.apk)

アプリがGoogle Play Store に登録されていないので、次の警告メッセージが表示されます。

![Android の警告画面](/help/assets/lab731-install-android.png)

クリック **インストール**

>[!ENDTABS]

## 演習 1.3:Adobe Journey Optimizerにログイン

[Journey Optimizerにログインするには、ここをクリックしてください](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**ログインの詳細：**

* **ユーザー名：** `L731+<your seat number>@summitlab.us` ( 例：L731+001@summitlab.us)
* **パスワード：** Adobe2023!


## 演習 2.1：アプリ内キャンペーンの作成

| フィールド | テキスト | リンク |
|----|----|----|
| キャンペーン名 | `<your seat number> March Vegas Campaign` |  |
| Matcher | 本を読む |  |
| メディア URL オプション |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| タイトル | それは起こっていて、それはライブです！ |  |
| 本文 | Adobe Summit が 2023年3月21日～23日 にラスベガスに戻ってきます。 刺激的な講演者やスキルを高めるセッション、新しい人脈作りに備えましょう。 |  |
| ボタン | 今すぐホテルを予約すれば 10％割引 | lab://booking?suite=presidential&amp;discount=10 |
| ボタン：インタラクティブイベント | アプリ内 CTA |  |
| ベース URL |  | iOS:lab:// <br>Android™:https://lab |


## レッスン 3：オムニチャネルジャーニーの作成

>[!BEGINTABS]

>[!TAB プッシュメッセージ]

**タイトル:**\
ベガスステイへようこそ！

**本文:**\
列に並ばずにモバイルアプリでチェックイン

**ディープリンク：** lab://checkin

**メディア:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=en


プッシュ通知に使用する画像は次のとおりです。

![オンラインチェックイン](/help/assets/vegas_online_check_in.jpg)

>[!TAB SMS メッセージ]

**メッセージ：**
ベガスステイへようこそ。 列に並ばずにモバイルアプリでチェックイン：lab://checkin

>[!TAB 電子メールメッセージ]

**件名：**
{{profile.person.name.firstName}}チェックイン済みです。今すぐ滞在のオファーを確認してください。

>[!ENDTABS]
