---
title: データ構造の手動設定
description: 必要な ID 名前空間を作成し、Luma サンプルデータ構造を定義します。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: b91d6ccdb54213873b91b7ffa9d95d7cb5261ee8
workflow-type: ht
source-wordcount: '1021'
ht-degree: 100%

---

# データの手動設定

この節では、必要な ID 名前空間を作成し、[[!UICONTROL スキーマ]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja)を作成して [!DNL Luma] サンプルデータ構造を定義します。

>[!TIP]
>開始する前に、[ID のマッピング](/help/set-up-data/map-identities.md)のビデオチュートリアルをご覧ください。

## 手順 1：ID 名前空間の作成

この手順では、`lumaLoyaltyId`、`lumaCrmId` および `lumaProductSKU` という名前の [!DNL Luma] カスタム ID フィールドの ID 名前空間を作成します。ID 名前空間は、同じ名前空間内の 2 つの一致する値により、2 つのデータソースで ID グラフを構成できるので、リアルタイム顧客プロファイルを作成するうえで重要な役割を果たします。

まず、[!DNL Luma Loyalty ID] スキーマの[!UICONTROL 名前空間]を作成します。

1. Journey Optimizer ユーザーインターフェイスの左側のナビゲーションで、**[!UICONTROL 顧客]**／**[!UICONTROL ID]** に移動します。

1. 「**[!UICONTROL ID 名前空間を作成]**」を選択します。

1. 次の詳細を入力します。

   | 表示名 | ID シンボル | タイプ |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL クロスデバイス ID] |

1. 「**[!UICONTROL 作成]**」を選択します。

   ![名前空間の作成](assets/createNamespace.png)

1. 同じ手順で、さらに 2 つの名前空間を作成します。

   | 表示名 | ID シンボル | タイプ |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL クロスデバイス ID] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL 人物以外の識別子] |

## 手順 2：スキーマの作成

この手順では、6 つの [[!UICONTROL スキーマ]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja)を作成して、サンプルデータの構造を定義します。

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] スキーマ](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>開始する前に、[スキーマの作成](/help/set-up-data/create-schema.md)のビデオチュートリアルをご覧ください。

### [!DNL Luma Loyalty Schema] の作成 {#create-luma-loyalty-schema}

この節では、[!DNL Luma Loyalty] スキーマを作成しフィールドグループを設定する方法を説明します。

#### スキーマの作成

1. 左側のナビゲーションで&#x200B;**[!UICONTROL データ管理]**／**[!UICONTROL スキーマ]**&#x200B;に移動します。

1. 右上の「**[!UICONTROL スキーマを作成]**」を選択します。

1. ドロップダウンメニューから、「**[!UICONTROL XDM 個人プロファイル]**」を選択します。

   このオプションを選択するのは、個々の顧客の属性（ポイント、ステータスなど）をモデリングするからです。

#### 既存のフィールドグループの追加

次に、グループを使用してスキーマにフィールドグループを追加するように求められます。既存のフィールドグループを追加し、フィールドグループを作成する必要があります。

1. [!UICONTROL スキーマ]ページで、フィールドグループモーダルが自動的に開かなかった場合は、「**[!UICONTROL 追加]**」を選択します。

   ![フィールドグループを追加](assets/add_field_group.png)

1. **[!UICONTROL フィールドグループを追加]**&#x200B;ページで、次のフィールドグループを有効にします。

   * **[!UICONTROL デモグラフィックの詳細]**：名前や生年月日などの基本的な顧客データ。

   * **[!UICONTROL 個人の連絡先の詳細]**：メールアドレスや電話番号などの基本的な連絡先詳細。

   * **[!UICONTROL ロイヤルティの詳細]**：ポイント、加入日、ステータスなどのロイヤルティの詳細。ロイヤルティフィールドグループはリストの下の方にあるので、検索するのが最も簡単です。

1. 「**[!UICONTROL フィールドグループを追加]**」を選択して、3 つのフィールドグループをすべてスキーマに追加します。

   ![標準フィールドグループの選択](assets/addstandardFieldGroups.png)

1. スキーマの一番上のノードを選択します。

1. 「**[!UICONTROL 表示名]**」として `Luma Loyalty Schema` を入力します。

#### [!UICONTROL フィールドグループ]の作成 {#create-field-group}

スキーマ間の一貫性を確保するために、すべてのシステム識別子を 1 つのグループで管理することをお勧めします。

1. [!UICONTROL フィールドグループ]の下にある「**[!UICONTROL 構成]**」セクションから、「**[!UICONTROL 追加]**」を選択します。

1. 「**[!UICONTROL 新しいフィールドグループを作成]**」を選択します。

1. 「**[!UICONTROL 表示名]**」として `Luma Identity Profile Field Group` を追加します。

1. 「**[!UICONTROL 説明]**」として `system identifiers for XDM Individual Profile class` を追加します。

1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

   ![新しいフィールドグループの作成](assets/addnewfieldgroup.png)

#### 新しい[!UICONTROL フィールドグループ]にフィールドを追加します。

新しい空のフィールドグループがスキーマに追加されます。 「+」ボタンを使用すると、階層内の任意の場所に新しいフィールドを追加できます。この例では、ルートレベルにフィールドを追加する必要があります。

1. スキーマ名の横にある「**[!UICONTROL +]**」を選択します。

   この手順では、**テナント ID** 名前空間の下にフィールドを追加して、カスタムフィールドと標準フィールド間の競合を管理します。

1. **[!UICONTROL フィールドプロパティ]**&#x200B;サイドバーで、新しいフィールドの詳細を追加します。

   * **フィールド名：**`systemIdentifier`

   * **[!UICONTROL 表示名]：**`System Identifier`

   * **タイプ：**&#x200B;オブジェクト

   * **[!UICONTROL フィールドグループを割り当て]：**[!DNL Luma identifiers]

1. 「**[!UICONTROL 適用]**」を選択します。

   ![システム識別子の追加](assets/addsysteidentifier.png)

   `systemIdentifier` オブジェクトの下に 2 つのフィールドを追加します。

   | [!UICONTROL フィールド名] | [!UICONTROL 表示名] | [!UICONTROL タイプ] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL 文字列] |
   | `crmId` | `CRM Id` | [!UICONTROL 文字列] |

![フィールド](./assets/add_fields.png)

#### ID の設定

これで、[!UICONTROL 名前空間]と [!DNL Luma Loyalty schema] が設定されました。データを取り込む前に、ID フィールドにラベルを付ける必要があります。[!UICONTROL リアルタイム顧客プロファイル]で使用する各スキーマには、プライマリ ID が指定されている必要であり、取り込んだ各レコードにはそのフィールドの値が必要です。

1. **プライマリ ID** を設定します。

   **[!DNL Luma Loyalty Schema]** から：

   1. 「**[!DNL Luma Identity Profile Field Group]**」を選択します。

   2. **[!DNL loyaltyId]** フィールドを選択します。

   3. **[!UICONTROL フィールドプロパティ]**&#x200B;で、「**[!UICONTROL ID]**」チェックボックスを有効にします。

   4. 「**[!UICONTROL プライマリ ID]**」チェックボックスを有効にします。

   5. **[!UICONTROL ID 名前空間]**&#x200B;ドロップダウンメニューから `Luma Loyalty Id` 名前空間を選択します。

   6. 「**[!UICONTROL 適用]**」を選択します。

      ![プライマリ ID](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. **セカンダリ ID** を設定します。

   **[!DNL Luma Loyalty Schema]** から：

   1. 「**[!DNL Luma Identity Profile Field Group]**」を選択します。

   2. `crmId` フィールドを選択します。

   3. **[!UICONTROL フィールドプロパティ]**&#x200B;で、「**[!UICONTROL ID]**」チェックボックスを有効にします。

   4. **[!UICONTROL ID 名前空間]**&#x200B;ドロップダウンから `Luma CRM Id` 名前空間を選択します。

   5. 「**[!UICONTROL 適用]**」を選択します。

#### プロファイルへの有効化とスキーマの保存

1. スキーマの一番上のノードを選択します。

1. [!UICONTROL フィールドプロパティ]で、「**[!UICONTROL プロファイル]**」を有効にします。

   スキーマは次のようになります。

   ![Luma ロイヤルティスキーマ](assets/lumaloyaltyschema.png)

1. 「**[!UICONTROL 保存]**」を選択します。

### [!DNL Luma Product Catalog Schema] の作成 {#create-luma-product-catalog-schema}

1. 左側のナビゲーションで&#x200B;**[!UICONTROL データ管理]**／**[!UICONTROL スキーマ]**&#x200B;に移動します。

1. 「**[!UICONTROL スキーマを作成]**」（右上）を選択します。

1. クラスを作成するには、ドロップダウンメニューから「**[!UICONTROL すべてのスキーマタイプを参照]**」を選択します。

1. 「**[!UICONTROL 新しいクラスを作成]**」を選択します。

1. 表示名 `Luma Product Catalog Class` を追加します。

1. クラスを割り当てます。

1. [!UICONTROL フィールドグループ]を作成します。

   * 表示名：`Luma Product Catalog Field Group`

1. 次のフィールドを **[!DNL Luma Product Catalog Field Group]** に追加します。

   * フィールド名: `product`

   * 表示名：`Product`

   * タイプ：[!UICONTROL オブジェクト]

   * フィールドグループ：[!DNL Luma Product Catalog Field Group]

1. 「**[!UICONTROL 適用]**」を選択します。

1. 次のフィールドを **[!DNL Product]** オブジェクトに追加します。

   | [!UICONTROL フィールド名] | [!UICONTROL 表示名] | [!UICONTROL タイプ] |
   |-------------|-----------|----------|
   | `sku` | `Product SKU` | [!UICONTROL 文字列] |
   | `name` | `Product Name` | [!UICONTROL 文字列] |
   | `category` | `Product Category` | [!UICONTROL 文字列] |
   | `color` | `Product Color` | [!UICONTROL 文字列] |
   | `size` | `Product Size` | [!UICONTROL 文字列] |
   | `price` | `Product Price` | [!UICONTROL 倍精度浮動小数点] |
   | `description` | `Product Description` | [!UICONTROL 文字列] |
   | `imageUrl` | `Product Image URL` | [!UICONTROL 文字列] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL 文字列] |
   | `url` | `Product URL` | [!UICONTROL 文字列] |

1. プライマリ ID として **[!DNL SKU]** を設定します。
1. **[!UICONTROL 表示名]** `Luma Product Catalog Field Group` を[!UICONTROL フィールドグループ]に追加します。

1. 「**[!UICONTROL 保存]**」を選択します。

### [!DNL Luma Product Inventory Event Schema] の作成 {#create-luma-product-inventory-event-schema}

1. 左側のナビゲーションで&#x200B;**[!UICONTROL データ管理]**／**[!UICONTROL スキーマ]**&#x200B;に移動します。

1. 右上の「**[!UICONTROL スキーマを作成]**」ボタンを選択します。

1. ドロップダウンメニューから、「**[!UICONTROL すべてのスキーマタイプを参照]**」を選択します。

1. 「**[!UICONTROL 新しいクラスを作成]**」を選択します。

1. 表示名 `Luma Business Event Class` を追加します。

1. *[!UICONTROL 時系列]*&#x200B;タイプを選択します。

1. クラスを割り当てます。

1. [!UICONTROL フィールドグループ]を作成します。

   * 表示名：`Luma Product Inventory Event Details Field Group`

1. **[!UICONTROL 表示名]** `Luma Product Inventory Event Schema` をスキーマに追加します。

1. 次のフィールドを **[!DNL Luma Product Inventory Event Details Field Group]** に追加します。

   * フィールド名：`inventoryEvent`

   * 表示名：`Inventory Event`

   * タイプ：[!UICONTROL オブジェクト]

   * フィールドグループ：`Luma Product Inventory Event Details Field Group`

1. 次のフィールドを `Product Inventory Event Details` オブジェクトに追加します。

   | [!UICONTROL フィールド名] | [!UICONTROL 表示名] | [!UICONTROL タイプ] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 文字列] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL 文字列] |

   1. `stockEventType` を列挙に設定するには、`string` タイプを選択します。

   2. **[!UICONTROL フィールドプロパティ]**&#x200B;の一番下までスクロールします。

   3. 「**[!UICONTROL 列挙]**」を有効にします。

   4. **[!UICONTROL 値]（[!UICONTROL ラベル]**）を `restock`（`Restock`）と入力します。

   5. 「**[!UICONTROL 行を追加]**」を選択します。

   6. **[!UICONTROL 値]（[!UICONTROL ラベル]**）を `outOfStock`（`Out of Stock`）と入力します。

   7. 「**[!UICONTROL 適用]**」を選択します。

      ![列挙](assets/enum.png)

1. **[!DNL LumaProductSKU namespace]** を使用して、`inventory.Event.sku` フィールドを&#x200B;**[!UICONTROL プライマリ ID]** として設定します。

1. `sku` フィールドを選択し、**[!DNL Luma Product catalog Schema]** スキーマの `product.sku` フィールドへの関係を定義します。

   1. **[!UICONTROL フィールドプロパティ]**&#x200B;の一番下までスクロールします。

   2. 「**[!UICONTROL 関係]**」を有効にします。

      1. **[!UICONTROL 参照スキーマ]**：[!DNL Luma Product Catalog Schema]。

      2. **[!UICONTROL 参照 ID 名前空間]**：[!DNL LumaProductSKU]。
   3. 「**[!UICONTROL 適用]**」を選択します。

      スキーマは次のようになります。

      ![SKU 関係](assets/sku_relationship.png)


1. **プロファイル**&#x200B;に対して有効にします。

1. 「[!UICONTROL 保存]」を選択してスキーマを保存します。

### 追加スキーマの作成 {#create-additional-schemas}

次の追加[!UICONTROL スキーマ]を作成します。

| [!UICONTROL 表示名] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL クラス]** | [!UICONTROL XDM 個人プロファイル] | [!UICONTROL XDM エクスペリエンスイベント] | [!UICONTROL XDM 個人プロファイル] | [IUICONTROL XDM ExperienceEvent] |
| **[!UICONTROL 既存のフィールドグループの追加]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL 関係]** |  | `productListItems.SKU`：<br> 参照スキーマ `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`：<br> 参照スキーマ `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL プライマリ ID] [!UICONTROL 名前空間]）** | `systemIdentifier.crmId` |  | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL プロファイルへの有効化]** | ○ | ○ | ○ | ○ |

## 次の手順

データ構造を作成したので、[データセットを作成してサンプルデータを取り込むことができます](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md)。
