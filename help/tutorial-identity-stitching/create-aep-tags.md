---
title: Adobe Experience PlatformへのCRMIDの送信
description: Adobe Experience Platform タグを作成して、ブラウザーから受信したCRMIDをAdobe Experience Platformに送信する
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 894ad6b7-c4b4-465e-8535-3fdcd77e00eb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 10%
---
# Adobe Experience PlatformへのCRMIDの送信

Adobe Experience Platform Tagsは、CRMIDをAdobe Experience Platform（AEP）に送信するために使用されます。これは、ブラウザーから直接ID データを送信するための柔軟なイベント駆動型メカニズムを提供するからです。 ユーザーログイン後にCRMIDを送信すると、AEPは匿名のECIDを既知のCRM プロファイルにリンクさせ、正確なID合成を可能にします。 この連携は、Adobe Journey Optimizer（AJO）で統合された顧客プロファイルを構築し、オーディエンスを選定して、リアルタイムでパーソナライズされた体験を提供するための基盤となります。

_&#x200B;**FinWise**&#x200B;_&#x200B;という名前のExperience Platform Tags プロパティが作成されます。 Tags プロパティに次の拡張機能が追加されました

![tags-extensions](assets/tags-extensions.png)

前の手順で作成したFinancial Advisors DataStreamを使用して、AEP Web SDK拡張機能を設定します。
Experience Cloud ID サービスは、デバッグ目的でタグプロパティに追加されるオプションの拡張機能です。

## タグデータ要素

次のデータ要素を作成します

| データ要素 | 拡張機能 | データ要素タイプ | カスタム設定 |
|--------------|-----------------------------------|---------------------------|----------------------------------------|
| crmid | Adobe Client Data Layer | データレイヤーの計算状態 | user.crmid |
| ECID | Experience Cloud ID サービス | ECID |                                        |
| ID | Adobe Experience Platform Web SDK | ID マップ | ![画像](assets/identity-settings.png) |
| XDMVariable | Adobe Experience Platform Web SDK | Variable | ![画像](assets/xdmvariable.png) |

## ルールを作成

次のイベントとアクションを含むLoginEventというルールを作成します

イベント
![&#x200B; イベント &#x200B;](assets/data-pushed-event1.png)

変数アクションを更新
![update-variable](assets/update-variable1.png)
イベント送信アクション
![send-event](assets/send-event1.png)

## 保存してビルド

変更を保存し、ライブラリを作成および構築します。
