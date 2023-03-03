---
title: 手動でのデータ構造の設定
description: 必要な ID 名前空間を作成し、Luma サンプルデータ構造を定義します。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 10%

---

# 手動でのデータの設定

この節では、必要な ID 名前空間を作成し、 [!DNL Luma] サンプルデータ構造を作成する [[!UICONTROL スキーマ]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja).

>[!TIP]
>ビデオチュートリアルを見る [ID をマッピング](/help/set-up-data/map-identities.md) 始める前に

## 手順 1:ID 名前空間の作成

この手順では、の ID 名前空間を作成します [!DNL Luma] カスタム id フィールド名 `lumaLoyaltyId`, `lumaCrmId`、および `lumaProductSKU`. ID 名前空間は、同じ名前空間内の 2 つの一致する値によって 2 つのデータソースが ID グラフを形成できるので、リアルタイム顧客プロファイルの構築に重要な役割を果たします。

最初に、 [!UICONTROL 名前空間] の [!DNL Luma Loyalty ID] schema:

1. Journey Optimizerユーザーインターフェイスで、に移動します。 **[!UICONTROL 顧客]** > **[!UICONTROL ID]** をクリックします。

1. 選択 **[!UICONTROL ID 名前空間を作成]**.

1. 次の詳細を入力します。

   | 表示名 | ID シンボル | タイプ |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL クロスデバイス ID] |

1. 「**[!UICONTROL 作成]**」を選択します。

   ![名前空間を作成](assets/createNamespace.png)

1. 同じ手順で、さらに 2 つの名前空間を作成します。

   | 表示名 | ID シンボル | タイプ |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL クロスデバイス ID] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL 人以外の識別子] |

## 手順 2:スキーマを作成

この手順では、6 つの [[!UICONTROL スキーマ]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] スキーマ](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>次のビデオチュートリアルをご覧ください。 [スキーマの作成](/help/set-up-data/create-schema.md) 始める前に

### 作成 [!DNL Luma Loyalty Schema] {#create-luma-loyalty-schema}

この節では、 [!DNL Luma Loyalty] スキーマを作成し、フィールドグループを設定します。

#### スキーマの作成

1. に移動します。 **[!UICONTROL データ管理]** > **[!UICONTROL スキーマ]** をクリックします。

1. 選択 **[!UICONTROL スキーマを作成]** 右上に

1. ドロップダウンメニューから、 **[!UICONTROL XDM 個人プロファイル]**.

   このオプションを選択するのは、個々の顧客の属性（ポイント、ステータスなど）をモデリングするためです。

#### 既存のフィールドグループを追加

次に、グループを使用して、スキーマにフィールドグループを追加するよう求められます。 既存のフィールドグループを追加し、フィールドグループを作成する必要があります。

1. の [!UICONTROL スキーマ] ページを開き、「フィールドグループ」モーダルが自動的に開かなかった場合は、「 **[!UICONTROL 追加]**.

   ![フィールドグループを追加](assets/add_field_group.png)

1. の **[!UICONTROL フィールドグループの追加]** ページで、次のフィールドグループを有効にします。

   * **[!UICONTROL 人口統計の詳細]** （名前や生年月日などの基本的な顧客データ）。

   * **[!UICONTROL 個人の連絡先の詳細]** ：基本的な連絡先の詳細（電子メールアドレスや電話番号など）。

   * **[!UICONTROL ロイヤルティの詳細]** ロイヤルティの詳細（ポイント、結合日、ステータスなど）。 ロイヤルティフィールドグループはリストのずっと下にあるので、検索が最も簡単です。

1. 選択 **[!UICONTROL フィールドグループを追加]** :3 つのフィールドグループをすべてスキーマに追加します。

   ![標準フィールドグループを選択](assets/addstandardFieldGroups.png)

1. スキーマの最上位のノードを選択します。

1. 入力 `Luma Loyalty Schema` を **[!UICONTROL 表示名]**.

#### の作成 [!UICONTROL フィールドグループ] {#create-field-group}

スキーマ間の一貫性を確保するため、Adobeでは、1 つのグループ内のすべてのシステム識別子を管理することをお勧めします。

1. 次の **[!UICONTROL 構成]** 下のセクション [!UICONTROL フィールドグループ]を選択します。 **[!UICONTROL 追加]**.

1. 選択 **[!UICONTROL 新しいフィールドグループを作成]**.

1. 追加 `Luma Identity Profile Field Group` を **[!UICONTROL 表示名]**.

1. 追加 `system identifiers for XDM Individual Profile class` を **[!UICONTROL 説明]**.

1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

   ![新しいフィールドグループを作成](assets/addnewfieldgroup.png)

#### 新しい [!UICONTROL フィールドグループ]

新しい空のフィールドグループがスキーマに追加されます。 「+」ボタンを使用すると、階層内の任意の場所に新しいフィールドを追加できます。 この場合、ルートレベルにフィールドを追加する必要があります。

1. 選択 **[!UICONTROL +]** をクリックします。

   この手順では、以下にフィールドを追加します。 **テナント id** 名前空間を使用して、カスタムフィールドと標準フィールドの競合を管理します。

1. 内 **[!UICONTROL フィールドプロパティ]** サイドバーで、新しいフィールドの詳細を追加します。

   * **フィールド名:** `systemIdentifier`

   * **[!UICONTROL 表示名]：**`System Identifier`

   * **タイプ：** オブジェクト

   * **[!UICONTROL フィールドグループを割り当て]:** [!DNL Luma identifiers]

1. 「**[!UICONTROL 適用]**」を選択します。

   ![システム識別子を追加](assets/addsysteidentifier.png)

   以下に 2 つのフィールドを追加します。 `systemIdentifier` オブジェクト：

   | [!UICONTROL フィールド名] | [!UICONTROL 表示名] | [!UICONTROL タイプ] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL 文字列] |
   | `crmId` | `CRM Id` | [!UICONTROL 文字列] |

![フィールド](./assets/add_fields.png)

#### ID を設定

これで、 [!UICONTROL 名前空間] そして [!DNL Luma Loyalty schema] 設定済み データを取り込む前に、ID フィールドにラベルを付ける必要があります。 で使用する各スキーマ [!UICONTROL リアルタイム顧客プロファイル] はプライマリ id を指定する必要があり、取り込まれる各レコードにはそのフィールドの値が必要です。

1. を **プライマリ ID**:

   次の **[!DNL Luma Loyalty Schema]**:

   1. 「**[!DNL Luma Identity Profile Field Group]**」を選択します。

   2. を選択します。 **[!DNL loyaltyId]** フィールドに入力します。

   3. 内 **[!UICONTROL フィールドプロパティ]**、を有効にします。 **[!UICONTROL ID]** ボックス

   4. を有効にします。 **[!UICONTROL プライマリID]** ボックス

   5. を選択します。 `Luma Loyalty Id` 名前空間 **[!UICONTROL ID 名前空間]** ドロップダウンメニュー。

   6. 「**[!UICONTROL 適用]**」を選択します。

      ![プライマリ ID](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. を設定します。 **セカンダリ ID**:

   次の **[!DNL Luma Loyalty Schema]**:

   1. 「**[!DNL Luma Identity Profile Field Group]**」を選択します。

   2. を選択します。 `crmId` フィールドに入力します。

   3. 内 **[!UICONTROL フィールドプロパティ]**、を有効にします。 **[!UICONTROL ID]** ボックス

   4. を選択します。 `Luma CRM Id` 名前空間 **[!UICONTROL ID 名前空間]** ドロップダウン。

   5. 「**[!UICONTROL 適用]**」を選択します。

#### プロファイルを有効にしてスキーマを保存

1. スキーマの最上位のノードを選択します。

1. 内 [!UICONTROL フィールドプロパティ]，有効 **[!UICONTROL プロファイル]**.

   スキーマは次のようになります。

   ![Luma ロイヤルティスキーマ](assets/lumaloyaltyschema.png)

1. 「**[!UICONTROL 保存]**」を選択します。

### 作成 [!DNL Luma Product Catalog Schema] {#create-luma-product-catalog-schema}

1. に移動します。 **[!UICONTROL データ管理]** > **[!UICONTROL スキーマ]** をクリックします。

1. 選択 **[!UICONTROL スキーマを作成]** （右上）。

1. クラスを作成するには、「 **[!UICONTROL すべてのスキーマタイプを参照]** を選択します。

1. 選択 **[!UICONTROL 新しいクラスを作成]**.

1. 表示名を追加します。 `Luma Product Catalog Class`.

1. クラスを割り当てます。

1. の作成 [!UICONTROL フィールドグループ]:

   * 表示名： `Luma Product Catalog Field Group`

1. 次のフィールドを **[!DNL Luma Product Catalog Field Group]**.

   * フィールド名: `product`

   * 表示名： `Product`

   * タイプ： [!UICONTROL オブジェクト]

   * フィールドグループ: [!DNL Luma Product Catalog Field Group]

1. 「**[!UICONTROL 適用]**」を選択します。

1. 次のフィールドを **[!DNL Product]** オブジェクト：

   | [!UICONTROL フィールド名] | [!UICONTROL 表示名] | [!UICONTROL タイプ] |
   |-------------|-----------|----------|
   | `sku` | `Product SKU` | [!UICONTROL 文字列] |
   | `name` | `Product Name` | [!UICONTROL 文字列] |
   | `category` | `Product Category` | [!UICONTROL 文字列] |
   | `color` | `Product Color` | [!UICONTROL 文字列] |
   | `size` | `Product Size` | [!UICONTROL 文字列] |
   | `price` | `Product Price` | [!UICONTROL Double] |
   | `description` | `Product Description` | [!UICONTROL 文字列] |
   | `imageURL` | `Product Image URL` | [!UICONTROL 文字列] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL 文字列] |
   | `url` | `Product URL` | [!UICONTROL 文字列] |

1. を **[!DNL SKU]** をプライマリ id として設定します。
1. を **[!UICONTROL 表示名]** `Luma Product Catalog Field Group` から [!UICONTROL フィールドグループ].

1. 「**[!UICONTROL 保存]**」を選択します。

### 作成 [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}

1. に移動します。 **[!UICONTROL データ管理]** > **[!UICONTROL スキーマ]** をクリックします。

1. を選択します。 **[!UICONTROL スキーマを作成]** 」ボタンを右上にクリックします。

1. ドロップダウンメニューで、「 」を選択します。 **[!UICONTROL すべてのスキーマタイプを参照]**.

1. 選択 **[!UICONTROL 新しいクラスを作成]**.

1. 表示名を追加します。 `Luma Business Event Class`.

1. タイプを選択： *[!UICONTROL 時系列]*.

1. クラスを割り当てます。

1. の作成 [!UICONTROL フィールドグループ]:

   * 表示名： `Luma Product Inventory Event Details Field Group`

1. を **[!UICONTROL 表示名]** `Luma Product Inventory Event Schema` をスキーマに追加します。

1. 次のフィールドを **[!DNL Luma Product Inventory Event Details Field Group]**:

   * フィールド名: `inventoryEvent`

   * 表示名： `Inventory Event`

   * タイプ： [!UICONTROL オブジェクト]

   * フィールドグループ: `Luma Product Inventory Event Details Field Group`

1. 次のフィールドを `Product Inventory Event Details` オブジェクト：

   | [!UICONTROL フィールド名] | [!UICONTROL 表示名] | [!UICONTROL タイプ] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 文字列] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL 文字列] |

   1. 設定する `stockEventType` 列挙に型を選択します。 `string`.

   2. 下にスクロールして **[!UICONTROL フィールドプロパティ]**.

   3. 有効にする **[!UICONTROL Enum]**.

   4. 入力 **[!UICONTROL 値] ([!UICONTROL ラベル )]**: `restock` (`Restock`) をクリックします。

   5. 選択 **[!UICONTROL 行を追加]**.

   6. 入力 **[!UICONTROL 値] ([!UICONTROL ラベル )]**: `outOfStock` (`Out of Stock`) をクリックします。

   7. 「**[!UICONTROL 適用]**」を選択します。

      ![enum](assets/enum.png)

1. 設定 `inventory.Event.sku` ～としてのフィールド **[!UICONTROL プライマリ ID]** の使用 **[!DNL LumaProductSKU namespace]**.

1. を選択します。 `sku` フィールドを開き、 `product.sku` フィールド **[!DNL Luma Product catalog Schema]** スキーマ：

   1. 下にスクロールして **[!UICONTROL フィールドプロパティ]**.

   2. 有効にする **[!UICONTROL 関係]**.

      1. **[!UICONTROL 参照スキーマ]**: [!DNL Luma Product Catalog Schema].

      2. **[!UICONTROL 参照 ID 名前空間]**: [!DNL LumaProductSKU].
   3. 「**[!UICONTROL 適用]**」を選択します。

      スキーマは次のようになります。

      ![SKU 関係](assets/sku_relationship.png)


1. 有効にする対象 **プロファイル**.

1. 選択 [!UICONTROL 保存] スキーマを保存します。

### 追加スキーマの作成 {#create-additional-schemas}

次の追加情報を作成します。 [!UICONTROL スキーマ]:

| [!UICONTROL 表示名] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL クラス]** | [!UICONTROL XDM 個人プロファイル] | [!UICONTROL XDM エクスペリエンスイベント] | [!UICONTROL XDM 個人プロファイル] | [IUICONTROL XDM ExperienceEvent] |
| **[!UICONTROL 既存のフィールドグループを追加]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL 関係]** |  | `productListItems.SKU`:<br> 参照スキーマ `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`:<br> 参照スキーマ `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL プライマリID] [!UICONTROL 名前空間])** | `systemIdentifier.crmId` |  | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL プロファイルに対して有効にする]** | ○ | ○ | ○ | ○ |

## 次の手順

これで、データ構造が作成され、 [データセットの作成とサンプルデータの取り込み](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
