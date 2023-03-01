---
title: ロイヤルティステータス案内メールの作成 - 課題
description: ジャーニーキャンバスでジャーニーを構築する基本を理解します。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: e9553da0fd85ee6e48d3089a93d51a994635de81
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 61%

---

# ロイヤルティステータス案内メールの作成 - 課題

![ロイヤルティステータス案内メール - 課題バナー](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 課題 | ロイヤルティステータス案内メールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ja)</li> <li>[セグメントの選定](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=ja)</li><li>[HTML コンテンツのインポート](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=ja)</li></ul> |
| ダウンロードするアセット | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style=&quot;table-layout:auto&quot;}

## ストーリー

Luma は、顧客を引き付け維持する手段としてロイヤルティプログラムを提供しています。このプログラムには、ブロンズ、シルバー、ゴールド、プラチナの 4 種類の層が用意されています。それぞれのロイヤルティ層では、リピート客への報酬として様々な特典や割引、その他の特別なインセンティブを受け取ります。

Luma は、特別なプラチナステータスに下線を引くために、プラチナ層に到達した顧客に歓迎のメールを送信したいと考えています。

## 課題

プラチナロイヤルティ層に到達した顧客に案内メールを自動的に送信するジャーニーを設定するよう求められました。

>[!BEGINTABS]

>[!TAB タスク]

ロイヤルティ顧客がプラチナ層の資格を得たら、新しい特典を受け取り、お祝いのメールを受け取り、顧客に知らせる必要があります。 クリエイティブチームがHTMLファイルを提供しました **[Luma — ステータスアップグレード — ようこそ eMail](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** 電子メール本文に置き換えます。

1. Journey Optimizer で `Luma - platinum status` という名前の[!UICONTROL セグメント]を作成します。

1. `Luma - New Status - platinum` という名前のジャーニーを作成します。

   1. 顧客は、プラチナロイヤルティ層に認定されると、ジャーニーに進みます。

   1. 顧客は、`Luma - Platinum Status - Welcome` というラベル付きのメールメッセージを受信します。件名は「`Welcome to Platinum Status, {firstName}!`」で、クリエイティブチームから提供されたメール本文を含んでいます。 これは、 [!UICONTROL トランザクション] 電子メール。

   1. HTML ファイルをアップロードすると、メールが「プラチナ」ではなく「ダイヤモンド」ステータスを参照していることがわかります。クリエイティブチームに新しいファイルを要求するのではなく、[!UICONTROL メールデザイナー]でメールを更新します。

>[!TAB 成功基準]

ジャーニーをテストします。

1. 次を確認します。 [!UICONTROL セグメントを読み取りアクティビティ] には [!UICONTROL 名前空間] に設定 **[!DNL Luma CRM id(lumaCrmId)]**.

1. デフォルトを上書き [!UICONTROL 電子メールパラメーター] を設定し、独自の電子メールアドレスに設定します。
   * 内 **[!UICONTROL E メールパラメーター]**、T 記号をクリックします（パラメータの上書きを有効にする）。

   * 次をクリック： **[!UICONTROL 住所]** フィールドに入力します。

   * 次の画面で、電子メールアドレスを括弧で囲んで追加します。 `"yourname@yourdomain"` 式エディターで、「 **[!UICONTROL OK]**.

1. ジャーニーをテストモードに設定.

1. 選択 **[!UICONTROL トリガーとイベント]**.

1. 以下を追加します。 `CRM ID` 対象 `Stanleigh Stooke` 内 **[!UICONTROL プロファイル識別子]** フィールド： `4f34057d9d9e792c28ba18ecae378e98`

**結果：** パーソナライズされた *Luma — プラチナステータス — ようこそ* 電子メール。

メールの内容は以下になります。

![Luma — ステータスアップグレード — ようこそ eMail](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB 作業内容の確認]

セグメントは、次のようになります。

![Luma - platinum status- segment](/help/challenges/assets/segment-luma-platinum-status.png)

ジャーニーは次のようになります。

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
