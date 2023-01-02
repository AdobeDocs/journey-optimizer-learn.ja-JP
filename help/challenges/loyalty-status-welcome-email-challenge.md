---
title: ロイヤルティステータス案内メールの作成 - 課題
description: ジャーニーキャンバスでジャーニーを構築する基本を理解します。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 7a178b9c523ead0cf27aaa87d25b3752ef53f519
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---

# ロイヤルティステータス案内メールの作成 - 課題

![ロイヤルティステータス案内メール - 課題バナー](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 課題 | ロイヤルティステータス案内メールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ja)</li> <li>[セグメントの選定](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=ja)</li><li>[HTML コンテンツのインポート](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=ja)</li></ul> |
| ダウンロードするアセット | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## ストーリー

Luma は、顧客を引き付け維持する手段としてロイヤルティプログラムを提供しています。このプログラムには、ブロンズ、シルバー、ゴールド、プラチナの 4 種類の層が用意されています。それぞれのロイヤルティ層では、リピート客への報酬として様々な特典や割引、その他の特別なインセンティブを受け取ります。

特別なプラチナステータスに下線を引きます。Luma は、プラチナ層に到達した顧客に案内メールを送信したいと考えています。

## 課題

プラチナロイヤルティ層に到達した顧客に案内メールを自動的に送信するジャーニーを設定するよう求められました。

>[!BEGINTABS]

>[!TAB タスク]

ロイヤルティ顧客がプラチナ層の資格を得たら、その顧客にお祝いのメールを送信し、新しい特典を通知します。メール本文を含んだ HTML ファイル「**[Luma - ステータスアップグレード - 案内メール](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)**」がクリエイティブチームから提供されました。

1. Journey Optimizer で `Luma – status upgrade` という名前の[!UICONTROL セグメント]を作成します。
2. `Luma – New Status – platinum` という名前のジャーニーを作成します。
   1. 顧客はプラチナロイヤルティ層の資格を得ると、ジャーニーに進みます。
   2. 顧客は、`Luma – Platinum Status - Welcome` というラベル付きのメールメッセージを受信します。件名は「`Welcome to Platinum Status, (recipient's first name)!`」で、クリエイティブチームから提供されたメール本文を含んでいます。 これは、[!UICONTROL トランザクション]メールです。
   3. HTML ファイルをアップロードすると、メールが「プラチナ」ではなく「ダイヤモンド」ステータスを参照していることがわかります。クリエイティブチームに新しいファイルを要求するのではなく、電子メールデザイナーでメールを更新します。

>[!TAB 成功基準]

ジャーニーをテストします。

1. [!UICONTROL セグメントを読み取りアクティビティ]の[!UICONTROL 名前空間]が **[!DNL Luma CRM id(lumaCrmId)]** に設定されていることを確認します。
2. デフォルトの[!UICONTROL メールパラメーター]を上書きして、独自のメールアドレスに設定します。
   * 目の記号をクリックして、非表示の値を表示します。
   * [!UICONTROL メールパラメーター]で、T 記号をクリックします（パラメータの上書きを有効にする）。

       ![メールパラメーターを上書き](/help/challenges/assets/c3-override-email-paramters.jpg)
   
   * [!UICONTROL 住所フィールド]をクリックします。
   * 次の画面で、括弧内にメールアドレスを追加します。`"yourname@yourdomain"` を式エディターに入力し、「OK」をクリックします。


3. ジャーニーをテストモードに設定
4. イベントのトリガー
5. `Stanleigh Stooke` の次の [!DNL CRM ID] を「[!UICONTROL プロファイル識別子]」フィールド（`4f34057d9d9e792c28ba18ecae378e98`）に追加します

**結果：**&#x200B;パーソナライズされた（*Luma - プラチナステータス - お知らせ*）メールを受信します。

>[!TAB 作業内容の確認]

ジャーニーは次のようになります。

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)


メールの内容は以下になります。

![Luma - ステータスアップグレード - お知らせメール](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
