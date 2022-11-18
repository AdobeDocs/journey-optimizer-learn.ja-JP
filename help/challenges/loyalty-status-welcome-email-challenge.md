---
title: ロイヤルティステータスのお知らせメールの作成 — チャレンジ
description: ジャーニーキャンバスでジャーニーを構築する基本を理解します。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
source-git-commit: 957515149af1281d29a45b24ca499ef097656eb8
workflow-type: tm+mt
source-wordcount: '365'
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

### Luma ダイヤモンドステータスセグメントを作成します。

Journey Optimizerで **あなたの名前 — Luma - Diamond Status**.

### Luma — 新しいステータス — ダイヤモンド — トランザクション用電子メールメッセージの作成

お知らせメールメッセージの作成

1. 「 」というタイトルのトランザクション E メールメッセージを作成します `(your name)_Luma – New Status – Diamond – Transactional email message`.
2. メールの件名を入力 `Welcome to Diamond Status, (recipient's first name)!`.
3. 提供されたHTMLファイルを使用 **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** 電子メール本文の


### **ジャーニー#3 - Diamond ステータスアップグレードのお知らせメール**

ロイヤルティ顧客が新しい層に移り、新しいメリットを祝福し、通知したら、E メールを送信します。

1. 顧客が Diamond の新しいロイヤルティ層に移行したとき（特に、新しい Diamond レベルのメンバーに対して定義されたセグメントを顧客が入力したとき）にトリガーされるジャーニーを作成して、「Luma - New Status - Diamond - Transactional」 E メールを送信します。
2. 完了したら、ジャーニーをテストモードにし、ジャーニーをトリガーして自分に送信する  

達成基準

パーソナライズされた「Luma - New Status- Diamond-Transactional」E メールが届きます。
