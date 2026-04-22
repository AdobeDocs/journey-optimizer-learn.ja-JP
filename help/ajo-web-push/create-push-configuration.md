---
title: プッシュチャネルの作成
description: プッシュチャネル設定は、アプリケーション設定やプラットフォーム固有の詳細など、web プッシュ通知の配信方法を定義します。 また、プッシュ設定をVAPID キーなどの必要な資格情報にリンクして、AJOが購読者に通知を送信できるようにします。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# プッシュチャネルの作成

最初のステップは、Adobe Journey Optimizerでプッシュチャネルを作成することです。 この設定の一環として、Web プッシュ通知の認証と有効化に必要なVAPID キーを生成する必要があります。 これらのキーはプッシュチャネル設定で使用され、AJOが登録者に安全に通知を送信できるようにします。

## VAPID キーの生成

VAPID （Voluntary Application Server Identification）は、公開鍵と秘密鍵のペアを使用してサーバーがサービス（Chrome、Edgeなど）をプッシュすることを識別できるweb プッシュ標準です。これにより、プッシュプロバイダーは誰が通知を送信しているかを把握できます。

これは、web プッシュのgenerate-vapid-keysのようなツールを使用して生成され、公開鍵（ブラウザーと共有）と秘密鍵（サーバーに保存）を作成し、プッシュメッセージを認証して安全に送信するために一緒に使用します。

このチュートリアルでは、Node.jsを使用してVAPID キーを生成しました。

Node.jsがインストールされていることを確認します。 次のコマンドを実行します
```npm install web-push -g ```

![web プッシュ &#x200B;](assets/install-web-push.png)

```web-push generate-vapid-keys```

![vapid](assets/vapid-keys.png)

## プッシュ資格情報の作成

* Journey Optimizerへのログイン

* 管理に移動| チャネル | プッシュ設定| プッシュ資格情報| プッシュ資格情報の作成

* ![&#x200B; プッシュ資格情報](assets/push-credential.png)

## チャネル設定の作成

* Journey Optimizerへのログイン

* 管理に移動| チャネル | チャネル設定の作成
  ![channel-configuration](assets/push-channel.png)
