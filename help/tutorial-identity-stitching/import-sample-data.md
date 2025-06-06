---
title: サンプル CRM データのAEP プロファイルデータセットへの読み込み
description: サンプルレコード（CRMID、電子メール、収入、郵便番号など）を読み込んで、ECID などの共有識別子に基づいて、AEPがそれらのプロファイルを匿名 web 訪問者と正しくステッチできるかどうかを検証します。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# サンプル CRM データのAEP プロファイルデータセットへの読み込み

ID ステッチを開始するには、サンプルの CRM プロファイルデータを、Adobe Experience Platformのプロファイル対応スキーマに結び付けられたデータセットにインポートします

## カスタム名前空間の作成

* 顧客/ ID / ID 名前空間の作成に移動します。
* 「個々のクロスデバイス ID」を選択し、表示名と ID 記号を入力します（以下のスクリーンショットを参照）。
  ![custom-namespace](assets/custom-namespace.png)

## プロファイルが有効なスキーマの作成

**_FinWiseProfileSchema_** という個別プロファイルスキーマを作成します。 innualIncome、email、firstName、lastName、loyaltyStatus などのフィールドを含めます。
SystemIdentifier オブジェクトの下に ID フィールド **_crmid_** を追加します。 Crmid フィールドを ID およびプライマリとしてマークします。


![profile-schema](assets/finwise-profile-schema.png)

## サンプルデータの準備

| crmId | firstName | lastName | メール | loyaltyStatus | zipCode | annualIncome |
|--------|-----------|----------|-------------------------|---------------|---------|--------------|
| FIN001 | アリス | ウォン | alice.wong@example.com | ゴールド | 92128 | 120000 |
| FIN002 | Bob | Smith | bob.smith@example.com | シルバー | 92126 | 85000 |
| FIN003 | チャーリー | キム | charlie.kim@example.com | Platinum | 60614 | 175000 |
| FIN004 | ダイアナ | リー | diana.lee@example.com | ゴールド | 30303 | 98000 |
| FIN005 | イーサン | ブラウン | ethan.brown@example.com | ブロンズ | 75201 | 60000 |

## CSV ファイルの取り込み

* 前の手順で作成した **_FinWiseProfileSchema_** に基づいて、**_FinWiseCustomerDataSetWithAnnualIncome_** というデータセットを作成します

* 接続/ ソース / ローカルシステムに移動します。
* ローカルファイルをアップロードして、**_データを追加_** を選択します。 必ず _&#x200B;**FinWiseCustomerDataSetWithAnnualIncome**&#x200B;_ をターゲットデータセットとして選択してください。
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* 次の画面に移動します。 [csv ファイルをアップロードし ](assets/finwise_profiles.csv) マッピングを確認します
  ![ マッピング ](assets/mappings.png)

* 「終了」をクリックしてデータ取り込みプロセスを開始します。

## プロファイルの検証

* 顧客/プロファイルに移動し、FIN001 または他の有効な値と等しい FinWise CRM ID を検索します
  ![verify-profile](assets/verify-profiles.png)
