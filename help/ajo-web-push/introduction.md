---
title: AJOでのweb プッシュ
description: このチュートリアルでは、Adobe Journey Optimizer（AJO）を使用してweb プッシュ通知を実装する方法を説明します。 Web SDKでユーザーオプトインを取得する方法、スケジュールされたキャンペーンを通じて通知を送信する方法、AEP Tagsでカスタム price.drop イベントを使用してリアルタイムのプッシュメッセージをトリガーする方法について説明します。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Adobe Journey Optimizerでのweb プッシュ

web プッシュ通知は、顧客をリアルタイムでリエンゲージする強力な方法です。このチュートリアルでは、Adobe Journey Optimizer（AJO）を使用して、プッシュ通知を実装する方法を説明します。 まず、Web SDKを使用して、プッシュ通知のユーザーオプトイン設定を取得し、シームレスでコンプライアンスに準拠したサブスクリプション体験を実現します。 次に、オプトインしたユーザーにプッシュ通知を送信するキャンペーンを作成し、オーディエンスベースのエンゲージメントを可能にします。 最後に、AEP Tagsを活用してカスタム値下げイベントをトリガーし、AJOでジャーニーを開始して、リアルタイムのユーザー行動にもとづいてパーソナライズされたプッシュ通知をタイムリーに配信する方法について解説します。

ユーザーが通知をオプトインできるようにするサンプル web ページ

![enable-notifications](assets/enable-notifications.png)

Web ページからトリガーへの値下げイベントのサンプル

![トリガー価格低下](assets/trigger-price-drop-event.png)

## 前提条件

このチュートリアルは、実践的でわかりやすいように設計されています。 深い専門知識は必要ありませんが、次の概念に関する基本的な知識が役立ちます。

- Adobe Journey Optimizer（ジャーニーまたはキャンペーンの作成）
- AEP Data Collection （Tags）とWeb SDK
- スキーマやイベントなどの基本的なAdobe Experience Platformの概念
- JavaScriptと一般的なweb開発のコンセプト
- 基本的なNode.jsの知識（VAPID キーの生成とシンプルな設定エンドポイントの提供）

これらの分野に不慣れであれば、心配はいりません。チュートリアルでは、重要なステップを順を追って説明します。
このチュートリアルでは、エンドツーエンドのweb プッシュ通知ユースケースの実装に焦点を当てているので、上記のツールと概念に関する実用的な知識があれば、効果的にフォローするのに役立ちます。


## 🔔 ブラウザー通知の有効化

通知がブロックされるか表示されない場合は、ブラウザーの設定で通知を有効にする必要がある場合があります。 以下のガイドを参照してください。

- **Google Chrome （Windows/macOS）**\
  <https://support.google.com/chrome/answer/3220216>

- **Microsoft Edge （Windows）**\
  <https://support.microsoft.com/en-us/microsoft-edge/manage-website-notifications-in-microsoft-edge>

- **Safari （macOS）**\
  <https://support.apple.com/guide/safari/customize-website-notifications-sfri40734/mac>

- **Safari （iPhone/iPad）**\
  <https://support.apple.com/en-us/HT213893>


## サンプルアプリケーション


これを確認するために、完全なサンプルアプリケーションが用意されています。

- [ ライブデモ – オプトイン：](https://ajo-web-push.onrender.com/)

- [トリガー値下げイベント：](https://ajo-web-push.onrender.com/price-drop-trigger.html)

- [Source コード：](https://github.com/gbedekar489/ajo-web-push)

ライブデモを見て実際のフローを確認したり、リポジトリを複製してプロジェクトをローカルで実行したりできます。

