---
title: ロイヤルティステータスのお知らせメールの作成 — チャレンジ
description: ジャーニーキャンバスでジャーニーを構築する基本を理解します。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: a9b6559d308823f5af7c2b26c3b2ae59d60d5a60
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# ロイヤルティステータスのお知らせメールの作成 — チャレンジ

![ロイヤルティステータスのお知らせメール — チャレンジバナー](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 課題 | ロイヤルティステータスのお知らせメールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[セグメントの選定](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[インポートHTMLコンテンツ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| ダウンロードするアセット | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## ザストーリー

Luma は、顧客を引き付け、保持する方法としてロイヤリティープログラムを提供しています。 プログラムは、次の 4 つの異なるレベルを提供します。青銅、銀、金、プラチナ。 各ロイヤルティ層は、リピートビジネスの報酬として、様々なレベルまたは報酬、割引、その他の特別なインセンティブを受け取ります。

特別なプラチナステータスに下線を引く。 Luma は、プラチナ層に到達した顧客に歓迎のメールを送信したいと考えています。

## 課題

プラチナロイヤルティ層に到達した顧客に歓迎のメールを自動的に送信するジャーニーを設定するように求められました。

>[!BEGINTABS]

>[!TAB タスク]

ロイヤリティ顧客がプラチナ層の資格を得たら、新しい特典を受け取り、お祝いを申し上げるために E メールを送信します。 クリエイティブチームがHTMLファイルを提供しました **[Luma — ステータスアップグレード — ようこそ eMail](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** 電子メール本文に置き換えます。

1. の作成 [!UICONTROL セグメント] Journey Optimizerで `Luma – status upgrade`.
2. という名前のジャーニーを作成します。 `Luma – New Status – platinum`.
   1. 顧客は、プラチナロイヤルティ層の資格を得ると、ジャーニーに進みます。
   2. 顧客は、ラベル付きの E メールメッセージを受け取る `Luma – Platinum Status - Welcome`件名行 `Welcome to Platinum Status, (recipient's first name)!` クリエイティブチームが提供する e メール本文を含む。
   3. HTMLファイルをアップロードすると、E メールが「platinum」ではなく「diamond」ステータスを参照していることに気がつきます。 クリエイティブチームに新しいファイルを要求する代わりに、E メールデザイナーで E メールを更新します。

>[チップ！]
> Luma - Platinum Status - Welcome eMail が[!UICONTROL トランザクション].


>[!TAB 達成基準]

ジャーニーのテスト:

1. 必ず [!UICONTROL セグメントを読み取りアクティビティ] には [!UICONTROL 名前空間] に設定 **[!DNL Luma CRM id(lumaCrmId)]**
2. デフォルトを上書き [!UICONTROL 電子メールパラメーター] を設定し、独自のメールアドレスに設定します。
   * 目の記号をクリックして、非表示の値を表示します。
   * 内 [!UICONTROL E メールパラメーター]、T 記号をクリックします（パラメータの上書きを有効にする）

       ![ 電子メールパラメーターを上書き ](/help/challenges/assets/c3-override-email-paramters.jpg)
   
   * をクリックして、 [!UICONTROL 住所フィールド]
   * 次の画面で、括弧内にメールアドレスを追加します。 `"yourname@yourdomain"` 式エディターで、「 ok 」をクリックします。


3. ジャーニーをテストモードに設定
4. トリガーとイベント
5. 以下を追加します。 [!DNL CRM ID] 対象 [!DNL Stanleigh Stooke] に [!UICONTROL プロファイル識別子] フィールド： `4f34057d9d9e792c28ba18ecae378e98`

パーソナライズされた *Luma — プラチナステータス — ようこそ* 電子メール。

>[!TAB 作業内容を確認する]

ジャーニーは次のようになります。

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)


E メールは次のようになります。

![Luma — ステータスアップグレード — ようこそ eMail](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
