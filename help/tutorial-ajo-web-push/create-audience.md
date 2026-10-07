---
title: オーディエンスを作成
description: Adobe Experience Platformで、プッシュ通知を受け取る資格のあるユーザーをターゲットとするセグメントを定義します。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%
---
# オーディエンスの作成

キャンペーンのオーディエンスを作成するには、Adobe Experience Platformで、プッシュ通知の受信資格を持つユーザーをターゲットとするセグメントを定義します。 このチュートリアルでは、アクティブなプッシュサブスクリプションを持つユーザー（プッシュトークンが存在するユーザー）、通知をオプトアウトしていないユーザー（プッシュブロックリストに加えるフラグがfalseの場合）、指定されたアプリケーション設定に関連付けられているユーザー（アプリケーション識別子が`my-first-push`に等しい場合）。 これらのユーザーは、Adobe Journey Optimizerのキャンペーンまたはジャーニーを通じてweb プッシュ通知を受け取る完全な資格があります。オーディエンスを作成した後、プロファイルが入力され、ターゲティングの準備が整うように評価されていることを確認します。
このオーディエンスは、キャンペーンで使用され、購読者ユーザーにのみスケジュールされたweb プッシュメッセージを配信します。

![create-audience](assets/push-audience.png)
