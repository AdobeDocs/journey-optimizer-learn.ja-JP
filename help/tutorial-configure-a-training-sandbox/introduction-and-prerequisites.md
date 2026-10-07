---
title: トレーニングサンドボックスの設定 - 概要
description: サンドボックスをトレーニング用に設定する方法について説明します。 スキーマの設定、サンプルデータの取り込みおよびイベントの作成に必要な手順を調べます。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00.000Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
    internal-label: Data management activity
  - id: d556b755-390a-43f0-be32-a08cf6236126
    internal-label: Configuration
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
    internal-label: Administration
subfeature_v2:
  - id: d2e8a157-b3b0-4143-9ff3-809bf400be56
    internal-label: Sandboxes
  - id: efb19423-4da4-4fd1-88d8-5ee8c71ae766
    internal-label: Application settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 100%
---
# トレーニングサンドボックスの設定 - 概要と前提条件

![バナーチュートリアル - トレーニングサンドボックスの設定](./assets/ajo-banner-configure-training-sandbox.png)

このチュートリアルは、Adobe [!DNL Journey Optimizer] トレーニング環境の提供を担当する管理者およびデータエンジニアを対象としています。 スキーマの設定、サンプルデータの取り込みおよびイベントの作成に必要な手順を説明します。 また、3 つのテストプロファイルを作成して、学習者が自分の作業を確認できるようにします。

提供されるサンプルデータは、_[!DNL Luma]_という架空のスポーツアパレル会社に基づいています。 [!DNL Luma] には、複数の国に店舗があり、web サイトとモバイルアプリを備えたオンラインプレゼンスがあります。 [!DNL Luma] は、Adobe Journey Optimizer を使用して、コンテキストに応じた、つながりのあるパーソナライズされたエクスペリエンスを顧客に提供しています。

このチュートリアルの終わりには、[Journey Optimizer の課題](/help/challenges/introduction-and-prerequisites.md)の節の実践的な演習で扱っている [!DNL Luma] ユースケースをサポートするサンドボックスが得られます。

## 前提条件

トレーニングサンドボックスの設定を開始する前に、次のものが用意されていることを確認してください。

1. 専用の開発[サンドボックス](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=ja)。

1. マーケティングメッセージとトランザクションメッセージ用に設定された[メールメッセージプリセット](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=ja)。

1. トレーニングサンドボックスの&#x200B;**[!UICONTROL ジャーニー管理者]**&#x200B;権限と&#x200B;**[!UICONTROL データマネージャー]**&#x200B;権限。

1. [組織 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ja)。

1. Journey Optimizer インスタンスに設定された、サンプルデータを含んだ JSON ファイル。

   1. このチュートリアルに必要なすべての JSON ファイルを含んだ `luma-sample-data.zip` ファイルを[こちら](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip)からダウンロードします。

   1. ダウンロードフォルダーから `luma-data.zip` ファイルをコンピューター上の目的の場所に移動し、解凍します。

      これらのファイルには、トレーニングサンドボックスのサンプルデータが格納されています。

   1. 各ファイルを開き、**`yourOrganizationID`** を見つけて、ご自身の[組織 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ja) に置き換えます。

   1. ファイルを保存します。

## それでは、始めましょう。

[手動データの設定](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md)から始めます。

この手順では、必要なデータ構造を定義します。 データの設定が完了したら、データをサンドボックスに取り込んだあと、イベントを設定できます。
