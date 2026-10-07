---
title: L731 チートシート
description: このページには、L731 Summit Lab で使用されているテキストとリンクが含まれています。
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: 'yes'
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 6eb7d9ad-3477-58b3-957a-080ef7738a30
    internal-label: SMS
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
    internal-label: Email
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
    internal-label: Communication channels
subfeature_v2:
  - id: cc5c44e2-54a1-4927-b794-442cd87d8f74
    internal-label: In App channel
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 98%
---
# Summit Lab L731 - チートシート

このページには、L731 Summit Lab で使用されているテキストとリンクが含まれています。 これらを使用して、コンテンツをコピーし、Journey Optimizerメッセージに貼り付けることができます。

## 演習 1.1 - アプリのダウンロードとインストール

QR コードをスキャンしてアプリをダウンロード

>[!BEGINTABS]

>[!TAB iOS]

![iOS 用の QR コード](/help/assets/lab731-ios-qr-code.png)

>[!IMPORTANT]
>
>引き換えコードを求められた場合は、TestFlight アプリを閉じて、もう一度 QR コードをスキャンしてください。
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

**ログインの詳細**

* **ユーザー名：** `L731+<your seat number>@summitlab.us`（例：L731+001@summitlab.us）
* **パスワード：** Adobe2023!


## 演習 2：アプリ内キャンペーンの作成

| セクション | フィールド | テキスト | リンク |
|----|----|----|----|
| **プロパティ** | キャンペーン名 | `<your seat number> Vegas Stay Campaign` |  |
| **トリガー** | 都道府県 | 今すぐ予約 |  |
| **コンテンツを編集：**&#x200B;メディア | メディア URL オプション |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| **コンテンツを編集：**&#x200B;コンテンツ | タイトル | 早期ディスカウントを入手 |  |
| **コンテンツを編集：**&#x200B;コンテンツ | 本文 | Adobe Max がラスベガスに戻ってきます。 刺激的な講演者やスキルを高めるセッション、新しい人脈作りに備えましょう。 今すぐスイートを予約すると 10％オフになります。 |  |
| **コンテンツを編集：**&#x200B;ボタン | ボタン | 10％ディスカウントを入手 | lab://booking?suite=presidential&amp;discount=10 |
| **コンテンツを編集：**&#x200B;ボタン | インタラクトイベント | アプリ内 CTA |  |
| **デバイスでのプレビュー** | デバイス上でのプレビューに使用するベース URL |  | **iOS：** lab:// <br>**Android**：https://lab |

## 演習 3：プッシュ通知の作成

| フィールド | テキスト | リンク |
|----|----|----|
| キャンペーン名 | **`<your seat number> Max Push Campaign`** |  |
| タイトル | こんにちは |  |
| 本文 | Adobe Max がラスベガスに戻ってくることをご存知ですか。 今すぐ部屋を予約すると 10％ディスカウントになります。 |  |
| メディア URL オプション |  | https://i.ibb.co/1M0BnZn/Firefly-Big-conference-big-stage-with-ADBE-text-on-screen-40178.jpg |
