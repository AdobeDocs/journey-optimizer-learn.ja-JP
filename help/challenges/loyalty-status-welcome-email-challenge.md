---
title: ロイヤルティステータスのウェルカムメールの作成 - 課題
description: ロイヤルティ層に到達した顧客にウェルカムメールを自動的に送信するジャーニーを作成します。
jira: KT-8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 7861e0ca17a616273f5ea1b4d850310f1f4ec8b8
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 100%

---

# ロイヤルティステータスのウェルカムメールの作成 - 課題

| 課題 | ロイヤルティステータスのウェルカムメールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ja)</li> <li>[セグメントの選定](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=ja)</li><li>[HTML コンテンツのインポート](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=ja)</li></ul> |
| ダウンロードするアセット | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style="table-layout:auto"}

## ストーリー

Luma は、顧客を引き付け維持する手段としてロイヤルティプログラムを提供しています。このプログラムには、ブロンズ、シルバー、ゴールド、プラチナの 4 種類の層が用意されています。それぞれのロイヤルティ層では、リピート客への報酬として様々な特典や割引、その他の特別なインセンティブを受け取ります。

Luma は、特別なプラチナステータスを強調するために、プラチナ層に達した顧客にウェルカムメールを送信したいと考えています。

## 課題

プラチナロイヤルティ層に到達した顧客にウェルカムメールを自動的に送信するジャーニーを設定するよう求められました。

>[!BEGINTABS]

>[!TAB タスク]

ロイヤルティ顧客がプラチナ層の資格を得たら、その顧客にお祝いのメールを送信し、新しい特典を通知します。メール本文を含んだ HTML ファイル **[Luma - ステータスアップグレード - ウェルカムメール](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)**&#x200B;がクリエイティブチームから提供されました。

1. Journey Optimizer で `Luma - platinum status` という名前の[!UICONTROL セグメント]を作成します。

1. `Luma - New Status - platinum` という名前のジャーニーを作成します。

   1. 顧客はプラチナロイヤルティ層の資格を得ると、このジャーニーに進みます。

   1. `Luma - Platinum Status - Welcome` というラベルの付いたメールメッセージが顧客に届きます。メールの件名は「`Welcome to Platinum Status, {firstName}!`」で、メール本文はクリエイティブチームから提供されたものです。 これは、[!UICONTROL トランザクション]メールです。

   1. この HTML ファイルをアップロードすると、メールが「プラチナ」ではなく「ダイヤモンド」ステータスを参照していることがわかります。クリエイティブチームに新しいファイルを要求するのではなく、[!UICONTROL E メールデザイナー]でメールを更新します。

>[!TAB 成功基準]

ジャーニーをテストします。

1. [!UICONTROL セグメントを読み取りアクティビティ]の[!UICONTROL 名前空間]が **[!DNL Luma CRM id(lumaCrmId)]** に設定されていることを確認します。

1. デフォルトの[!UICONTROL メールパラメーター]を上書きして、独自のメールアドレスに設定します。
   * **[!UICONTROL メールパラメーター]**&#x200B;で、T 記号をクリックします（パラメーターの上書きを有効にします）。

   * 「**[!UICONTROL 住所]**」フィールドをクリックします。

   * 次の画面で、括弧内にメールアドレスを追加します。式エディターで `"yourname@yourdomain"` を入力し、「**[!UICONTROL OK]**」をクリックします。

1. ジャーニーをテストモードに設定します。

1. 「**[!UICONTROL イベントをトリガー]**」を選択します。

1. `Stanleigh Stooke` の `CRM ID`（`4f34057d9d9e792c28ba18ecae378e98`）を「**[!UICONTROL プロファイル識別子]**」フィールドに追加します。

**結果：**&#x200B;パーソナライズされた *Luma - プラチナステータス - ウェルカム*&#x200B;メールが届きます。

メールは次のような内容になります。

![Luma - ステータスアップグレード - ウェルカムメール](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB 作業内容の確認]

セグメントは、次のようになります。

![Luma - platinum status- segment](/help/challenges/assets/segment-luma-platinum-status.png)

ジャーニーは次のようになります。

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
