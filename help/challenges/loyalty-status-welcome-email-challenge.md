---
title: ロイヤルティステータスのお知らせメールの作成 — チャレンジ
description: ジャーニーキャンバスでジャーニーを構築する基本を理解します。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: bcd4e8f01ebb83444934d641d3ee3aafe420bd6b
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 8%

---

# ロイヤルティステータスのお知らせメールの作成 — チャレンジ

![AJO Loyalty ステータスのお知らせメール — チャレンジバナー](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 課題 | ロイヤルティステータスのお知らせメールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[メッセージエディターでの電子メールコンテンツの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[パーソナライゼーションに関するコンテキストイベント情報の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[パーソナライゼーションへのヘルパー関数の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| ダウンロードするアセット | [注文確認アセット](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## ザストーリー

Luma は、顧客を引き付け、保持する方法としてロイヤリティープログラムを提供しています。 プログラムは、次の 4 つの異なるレベルを提供します。銀、金、プラチナ、ダイヤモンド。

各ロイヤルティ層は、リピートビジネスの報酬として、様々なレベルまたは報酬、割引、その他の特別なインセンティブを受け取ります。

特殊ダイヤモンドのステータスに下線を引く。 Luma は、ダイヤモンド層に到達した顧客に歓迎のメールを送信したいと考えています。

## 課題

ダイヤモンドロイヤルティ層に到達した顧客に歓迎のメールを自動的に送信するジャーニーを設定するよう依頼されました。

>[!NOTE]
> 共有トレーニングサンドボックスで作業する場合は、作成する要素の名前にプレフィックスとして名前またはイニシャルを追加することをお勧めします。

>[!BEGINTABS]

>[!TAB タスク]

ロイヤルティ顧客がダイヤモンド層に移り、新しいメリットを祝福し、通知を受けたら、E メールを送信します。 「

1. Journey Optimizerで **Luma — ひし形ステータス**
2. 顧客が Diamond の新しいロイヤルティ層に移行したとき（特に、新しい Diamond レベルのメンバーに対して定義されたセグメントを顧客が入力したとき）にトリガーされるジャーニーを作成して、「Luma - New Status - Diamond - Transactional」 E メールを送信します。
   1. 「 」というタイトルのトランザクション E メールメッセージを作成します `(your name)_Luma – New Status – Diamond – Transactional email message`.
   2. メールの件名を入力 `Welcome to Diamond Status, (recipient's first name)!`.
   3. 提供されたHTMLファイルを使用 **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** 電子メール本文の
3. 完了したら、ジャーニーをテストモードにし、ジャーニーをトリガーして自分に送信する  

   1. 「 」というタイトルのトランザクション E メールメッセージを作成します `(your name)_Luma – New Status – Diamond – Transactional email message`.
   1. メールの件名を入力 `Welcome to Diamond Status, (recipient's first name)!`.
   1. 提供されたHTMLファイルを使用 **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** 電子メール本文の
4. 完了したら、ジャーニーをテストモードにし、ジャーニーをトリガーして自分に送信する  

### Luma — 新しいステータス — ダイヤモンド — トランザクション用電子メールメッセージの作成

お知らせメールメッセージの作成

### **ジャーニー#3 - Diamond ステータスアップグレードのお知らせメール**


>[!TAB 達成基準]

ジャーニーのテスト:

1. セグメントの選定イベントに名前空間= E メールが含まれていることを確認します。
1. デフォルトの E メールパラメーターを上書きし、独自の E メールアドレスに設定
1. ジャーニーをテストモードに設定
1. トリガーとイベント
1. 次の電子メールアドレスを「 Profile Identifier 」フィールドに追加します。Jenna_Palmer9530@emailsim.io

パーソナライズされた「Luma - New Status- Diamond-Transactional」E メールが届きます。

>[!TAB 作業内容を確認する]

ジャーニーは次のようになります。

![Diamond-status-upgrade-journey](/help/challenges/assets/journey-luma-diamond-status-upgrade.png)

>[!ENDTABS]
