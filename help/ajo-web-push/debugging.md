---
title: AJOでのWeb プッシュのデバッグ
description: このページでは、Web SDK リクエストの検証など、web プッシュ通知フローをデバッグする際に役立つヒントを提供します。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# AJOでのWeb プッシュのデバッグ

このページでは、Web プッシュ通知フローをデバッグする際に役立つヒントを提供します。これには、Web SDK リクエストの検証、AEPでのECIDとユーザープロファイルの確認、price.dropなどのイベントの正しい送受信の確認などが含まれます。

- **Adobe Experience Platform Debugger（Chrome拡張機能）を使用**\
  Chrome[用の](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob)AEP Debugger拡張機能をインストールして、Web SDK アクティビティをより簡単に調べることができます。

このツールを使用すると、次のことが可能になります。
- Web SDKのリクエストと応答を表示する\
- ECID （Experience Cloud ID）を確認します\
- データストリーム設定とペイロードの検証

- **ユーザーが識別されているかどうかを確認する（ECID）**\
  AEP Debuggerまたはブラウザーコンソールを使用して、ECIDが生成されていることを確認します。 このIDは、AEPとAJO間でユーザーを追跡するために使用されます。

- **「ネットワーク」タブを使用してリクエストを確認する**\
  ブラウザーのデベロッパーツールで&#x200B;**Network タブ**&#x200B;を開き、Web SDKで行われたリクエストをフィルタリングします（`/collect`または`interact`を探してください）。
   - ページの読み込み時とアクションのトリガー時に確認リクエストが送信されます
   - `price.drop` イベントがペイロードに含まれていることを確認してください

- **AEPでユーザープロファイルを検索**\
  ECIDを使用して、Adobe Experience Platformでユーザーのプロファイルを検索します。 これにより、ユーザーが認識され、データ（プッシュ通知の購読など）が正しく保存されていることを確認できます。

- **`price.drop` イベントが受信されたことを確認します**\
  Web ページからイベントをトリガーした後、イベントが取り込まれ、同じECIDに関連付けられているかどうかをAEPで確認します。
`feedback.status`のmessage.feedback イベントのjsonを確認してください。 ステータス値は`sent`である必要があります
  ![値下げ](assets/price-drop-profile-event.png)

- **プッシュ通知が有効になっていることを確認する**\
  次のことを確認します。
   - ユーザーはブラウザー通知プロンプトに同意しました
   - プッシュトークンがユーザープロファイルに存在します

- **ジャーニーの設定を確認**\
  ジャーニーが公開され、`price.drop` イベントをリッスンするように設定されていることを確認してください。

