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
source-git-commit: 83b23f54594b796ec528526a360c5c40164fb5cb
workflow-type: tm+mt
source-wordcount: '346'
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
ID フィールド **_crmid_** を追加します。 crmid フィールドを ID およびプライマリとしてマークします。
_**同意および環境設定の詳細**_ フィールドグループをスキーマに追加します。 [ 同意および環境設定 ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/profile/consents) は、XDM 個人プロファイル クラスの標準フィールドグループで、個々の顧客の同意および環境設定情報を収集するものです。ここに格納される環境設定によって、チャネルレベルのコミュニケーション環境設定が決定します。


![profile-schema](assets/finwise-profile-schema.png)

## サンプルデータの準備

ダミーメールアドレスを実際のメールアドレスに更新します。 これらは、後でAdobe Journey Optimizerでメッセージを送信する際に使用されます。 emailConsent を y に設定して、プロファイルのメール配信を有効にします。

|   | crmId | firstName | lastName | メール | loyaltyStatus | zipCode | annualIncome | emailConsent |
|---|--------|-----------|----------|-------------------------|---------------|---------|--------------|--------------|
|   | FIN001 | アリス | ウォン | alice.wong@example.com | ゴールド | 92128 | 120000 | y |
|   | FIN002 | Bob | Smith | bob.smith@example.com | シルバー | 92126 | 85000 | y |
|   | FIN003 | チャーリー | キム | charlie.kim@example.com | Platinum | 60614 | 175000 | y |
|   | FIN004 | ダイアナ | リー | diana.lee@example.com | ゴールド | 30303 | 98000 | y |
|   | FIN005 | イーサン | ブラウン | ethan.brown@example.com | ブロンズ | 75201 | 60000 | y |

## CSV ファイルの取り込み

* 前の手順で作成した **_FinWiseProfileSchema_** に基づいて、**_FinWiseCustomerDataSetWithAnnualIncome_** というデータセットを作成します

* 接続/ ソース / ローカルシステムに移動します。
* ローカルファイルをアップロードして、**_データを追加_** を選択します。 必ず _**FinWiseCustomerDataSetWithAnnualIncome**_ をターゲットデータセットとして選択してください。
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* 次の画面に移動します。 [csv ファイルをアップロードし ](assets/finwise_profiles.csv) マッピングを確認します
  ![ マッピング ](assets/mappings.png)

* 「終了」をクリックしてデータ取り込みプロセスを開始します。

## プロファイルの検証

* 顧客/プロファイルに移動し、FIN001 または他の有効な値と等しい FinWise CRM ID を検索します
  ![verify-profile](assets/verify-profiles.png)
