---
title: オーディエンスを作成
description: Adobe Experience Platformで、プッシュ通知を受け取る資格のあるユーザーをターゲットとするセグメントを定義します。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---

# オーディエンスの作成

キャンペーンのオーディエンスを作成するには、Adobe Experience Platformで、プッシュ通知の受信資格を持つユーザーをターゲットとするセグメントを定義します。このチュートリアルでは、アクティブなプッシュサブスクリプションを持つユーザー（プッシュトークンが存在するユーザー）、通知をオプトアウトしていないユーザー（プッシュブロックリストに加えるフラグがfalseの場合）、指定されたアプリケーション設定に関連付けられているユーザー（アプリケーション識別子が`my-first-push`に等しい場合）。 これらのユーザーは、Adobe Journey Optimizerのキャンペーンまたはジャーニーを通じてweb プッシュ通知を受け取る完全な資格があります。オーディエンスを作成した後、プロファイルが入力され、ターゲティングの準備が整うように評価されていることを確認します。
このオーディエンスは、キャンペーンで使用され、購読者ユーザーにのみスケジュールされたweb プッシュメッセージを配信します。

![create-audience](assets/push-audience.png)
