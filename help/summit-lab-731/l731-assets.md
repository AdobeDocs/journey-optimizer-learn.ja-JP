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
source-git-commit: 056965ea13a84a182971b10138e5d9a75522d5c7
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 67%

---

# サミットラボ L731- チートシート

このページには、L731 Summit Lab で使用されているテキストとリンクが含まれています。 これらを使用して、コンテンツをコピーし、Journey Optimizerメッセージに貼り付けることができます。

## 演習 1.1 - アプリのダウンロードとインストール

QR コードをスキャンしてアプリをダウンロード

>[!BEGINTABS]

>[!TAB iOS]

![iOS 用の QR コード](/help/assets/lab731-ios-qr-code.png)

>[!IMPORTANT]
>
>使用コードを要求された場合は、TestFlight アプリを閉じて、QR コードをもう一度スキャンしてください。
>
>通知を許可してください。
>

Testflight のインストールを求められます（手順 1～4）。 Testflight をインストールしたら、手順 5～8 に従って Vegas Stay アプリをインストールします。

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>手順 1 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-1.png"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>手順 2 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>手順 3 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>手順 4 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
      </a>
      </div>
  </td>
  </tr>
  <tr>
<td>
 <div>
      <p>
      <b>手順 5 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>手順 6</b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>手順 7 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>手順 8 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![Android 用の QR コード](/help/assets/lab731-android-qr-code.png)

アプリが Google Play ストアに登録されていないので、次の警告メッセージが表示されます。

![Android の警告画面](/help/assets/lab731-install-android.png)

「**とにかくインストールする**」をクリックします

>[!ENDTABS]

## 演習 1：Adobe Journey Optimizer へのログイン

[Journey Optimizer にログインするには、こちらをクリックしてください](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home){target="_blank"}

**ログインの詳細：**

* **ユーザー名：** `L731+<your seat number>@summitlab.us`（例：L731+001@summitlab.us）
* **パスワード：** Adobe2023!


## 演習 2：アプリ内キャンペーンの作成

| セクション | フィールド | テキスト | リンク |
|----|----|----|----|
| **プロパティ** |  | キャンペーン名 | `<your seat number> Vegas Stay Campaign` |  |
| **Triggers** | 都道府県 | 今すぐ予約 |  |
| **コンテンツを編集：** メディア | メディア URL オプション |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| **コンテンツを編集：** コンテンツ | タイトル | 早めの鳥割引を！ |  |
| **コンテンツを編集：** コンテンツ | 本文 | Adobe・マックスはラスベガスに戻る。 刺激的な講演者やスキルを高めるセッション、新しい人脈作りに備えましょう。今すぐスイートを予約して、10%引きです。 |  |
| **コンテンツを編集：** ボタン | ボタン | 10%割引を！ | lab://booking?suite=presidential&amp;discount=10 |
| **コンテンツを編集：** コンテンツ |  | ボタン：Interact イベント | アプリ内 CTA |  |
| **デバイスでのプレビュー** |  | デバイスでのプレビューに使用するベース URL |  | **iOS:** lab:// <br>**Android**:https://lab |


## 演習 3:プッシュ通知の作成

| フィールド | テキスト | リンク |
|----|----|----|
| キャンペーン名 | `<your seat number> Max Push Campaign` |  |
| メディア URL オプション |  | https://i.ibb.co/1M0BnZn/Firefly-Big-conference-big-stage-with-ADBE-text-on-screen-40178.jpg |
| タイトル | おい！ |  |
| 本文 | Adobe・マックスがベガスに戻るのを知っていたか。 部屋を予約して、10%割引を受けます。 |  |
