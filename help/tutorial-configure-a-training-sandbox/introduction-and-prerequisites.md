---
title: トレーニングサンドボックスの設定 — はじめに
description: トレーニング用にサンドボックスを設定する方法について説明します。 スキーマの設定、サンプルデータの取り込み、イベントの作成に必要な手順を実行します。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
source-git-commit: 79249cf6ecd08c38c075a4e27fa9cf74073491af
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 5%

---


# トレーニングサンドボックスの設定 — はじめにと前提条件

![バナーチュートリアル — トレーニングサンドボックスの設定](./assets/ajo-banner-configure-training-sandbox.png)

このチュートリアルは、Adobe Journey Optimizerのトレーニング環境を提供する管理者とデータエンジニアを対象としています。 スキーマの設定、サンプルデータの取り込み、イベントの作成に必要な手順を説明します。 また、3 つのテストプロファイルを作成して、学習者が自分の作業を確認できるようにします。

提供されるサンプルデータは、という架空のスポーツアパレル会社に基づいています。 _[!DNL Luma]_. [!DNL Luma] には、複数の国に店舗があり、Web サイトやモバイルアプリを使用したオンラインプレゼンスがあります。 [!DNL Luma] はAdobe Journey Optimizerを使用して、接続された、コンテキストに応じた、パーソナライズされたエクスペリエンスを顧客に提供します。

このチュートリアルの最後に、をサポートするサンドボックスがあります。 [!DNL Luma] の実践演習で扱われる使用例 [Journey Optimizerの課題](/help/challenges/introduction-and-prerequisites.md) 」セクションに入力します。

## 前提条件

トレーニングサンドボックスの設定を開始する前に、以下の点を確認してください。

1. 専門の開発 [サンドボックス](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [電子メールメッセージプリセット](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/channel-configuration/set-up-email-channel.html?lang=en) マーケティングおよびトランザクションメッセージ用に設定されます。
1. **[!UICONTROL ジャーニー管理者]** および **[!UICONTROL データマネージャ]** トレーニングサンドボックスの権限
1. お使いの [組織 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ja).

1. サンプルデータが含まれる JSON ファイルを、Journey Optimizerインスタンスに設定します。

   1. をダウンロードします。 `luma-data.zip` ファイル [ここ](/help/tutorial-configure-a-training-sandbox/assets/luma-data.zip)：このチュートリアルで必要なすべての JSON ファイルを含みます。

   1. ダウンロードフォルダーから、 `luma-data.zip` ファイルをコンピューター上の目的の場所に展開し、解凍します。

      次の 3 つの JSON ファイルが存在するはずです。 `luma-crm.json`, `luma-loyalty.json`, `luma-products.json`.

      これらのファイルは、サンドボックスに取り込むサンプルデータを保持します。

   1. 各ファイルを開き、 **`yourOrganizationID`** を置き換え、 [組織 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en).

   1. ファイルを保存します。

## 始めましょう

まず、 [手動データの設定](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). この手順では、必要なデータ構造を定義します。 データの設定が完了したら、データをサンドボックスに取り込んで、イベントを設定できます。
