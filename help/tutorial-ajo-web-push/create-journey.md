---
title: ジャーニーを作成
description: price.drop イベントでトリガーされるジャーニーを作成
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 14342b47-5485-4f7f-9312-cff1ee0f8972
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# ジャーニーを作成

この手順では、カスタム price.drop イベントによってトリガーされるジャーニーをAdobe Journey Optimizerで作成します。 このイベントを受信すると、ジャーニーはリアルタイムで開始され、オプトインしたユーザーにプッシュ通知を送信し、イベント主導のエンゲージメントを可能にします。

price.drop イベントでトリガーされるジャーニーを作成するには、次の手順に従います

* Journey Optimizerにログインします
* ジャーニー管理に移動| ジャーニー | ジャーニーの作成

![create-journey](assets/create-journey.png)

## PriceDropEventを追加

「`PriceDropEvent`」を「イベント」セクションからキャンバスにドラッグします。
![price-drop-event](assets/add-price-drop-event.png)

## プッシュアクションを追加

「アクション」セクションを展開します。 `Action` アクティビティをキャンバスにドラッグ&amp;ドロップし、アクションタイプとして「プッシュ」を選択します
![&#x200B; プッシュアクション &#x200B;](assets/add-push-action.png)

## プッシュアクションの設定

プッシュ通知アクティビティを選択し、「設定」アクションをクリックします

![configure-push-action](assets/configure-push-action.png)

## プッシュ通知チャネルの設定

チュートリアルの前に作成した`MyFirstWebPushChannel`設定をこのプッシュ通知に関連付けます

![channel-configuration](assets/journey-actions.png)

## プッシュ通知メッセージの作成

パーソナライゼーションエディターを使用して、プッシュ通知に静的コンテンツと動的コンテンツの組み合わせを追加し、メッセージをより魅力的で関連性の高いものにします。

メッセージの作成を開始するには、`Content`をクリックして「コンテンツ」タブを開き、固定テキストとイベントデータから派生した動的フィールドの両方を定義できます。
![content-push](assets/compose-message.png)

プッシュメッセージのタイトルを指定し、パーソナライゼーションエディターを開いてメッセージ本文を構成します。 コンテンツには、価格が下がった製品名が動的に含まれます。 これには、各[&#x200B; ヘルパー関数を使用します](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/functions/helpers#each)
商品リストを繰り返し表示し、メッセージ内に商品の名前を表示します。

## メッセージ本文の作成

ヘルパー関数メニューから`Each`関数を選択して挿入します。
![&#x200B; ヘルパー関数](assets/journey-content-helper-function.png)

コンテキスト属性を選択| Journey Orchestration | イベント | PriceDropEvent | productListItems |名前

「+」アイコンをクリックして、パーソナライゼーションエディター内の各ループに配列を挿入します。 次に、参照スクリーンショットに表示されている形式に合わせてメッセージコンテンツを更新します。 環境に表示されるイベント IDは、表示されているものと異なる場合があります。

![contextual-attributes](assets/journey-content-context-attributes.png)

最後に、変更内容をすべて保存し、ジャーニーを公開します。 公開されると、ジャーニーはアクティブになり、price.drop イベントが受信されるのをリッスンします。 そのようなイベントを受信するたびに、ジャーニーがリアルタイムでトリガーされ、通知の受信をオプトインしたユーザーにプッシュ通知が送信され、タイムリーで関連性の高いエンゲージメントが保証されます。

## 解決策をテスト

price.drop イベントをトリガーするには、[値下げトリガーページを開き、](http://localhost:3000/price-drop-trigger.html)1つ以上の商品を選択し、「値下げトリガー」をクリックします。 これにより、AEP タグを使用してAdobe データレイヤーを介してイベントが送信され、その後ジャーニーが開始され、プッシュ通知がリアルタイムで配信されます。
