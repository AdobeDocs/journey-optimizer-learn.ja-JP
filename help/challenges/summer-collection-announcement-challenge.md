---
title: 夏物コレクションのお知らせの作成 — 課題
description: 既存の顧客のセグメントに夏物コレクションのお知らせを送信して、新しい Luma 夏物コレクションを宣伝します。
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: cfd438e198fdf62859569eed0c6ac22087ddbc75
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---

# 夏物コレクションのお知らせの作成 — 課題

![AJO 夏コレクションのお知らせバナー](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| 課題 | 夏物コレクションのお知らせの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [HTML 電子メールコンテンツの読み込みと作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[ユースケース - セグメントの読み取り](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| ダウンロードするアセット | [季節ごとのコレクションの電子メールファイル](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## 物語

架空のスポーツアパレル会社、Luma は、最新のアパレルとギアコレクションを推進し、既存顧客の売り上げを促進しています。 Luma は新しい夏物コレクションを開始しており、様々な顧客セグメントを具体的にターゲットにしたいと考えています。

## 課題

Luma マーケティングチームから、Journey Optimizerで Summer Collection マーケティングキャンペーンを実装するように求められます。 課題は次のとおりです。

* プロモーションを受け取る資格のあるプロファイルを定義するセグメントを作成します。
* ジャーニーの構築.

### 手順 1:セグメントの定義 — アクティブな顧客

>[!BEGINTABS]

>[!TAB タスク]

#### でのセグメントの作成 [!DNL Journey Optimizer]

* でのセグメントの作成 [!DNL Journey Optimizer] 呼び出し *アクティブな顧客*.
* セグメントには、アクティブな Luma の顧客のみを含める必要があります。
* アクティブな顧客は、Luma のロイヤルティプログラム（ブロンズ、シルバー、ゴールドまたはプラチナ）の層を持つ顧客と定義されます。


>[!TAB 達成基準]

セグメントビルダーで、認定済みプロファイルの推定数を確認できます。 トレーニングサンドボックスデータを使用する場合、1.29 KB 中 753 個の認定済みプロファイルがあります。

>[!NOTE]
>既存のプロファイルをバックフィルする必要があるので、既存のプロファイルに対してセグメントのメンバーシップが表示されるまでに最大 24 時間かかる場合があります。

**適格なプロファイルがセグメントに追加されました：**

セグメントの詳細ビューに表示されるプロファイルのいずれかに移動して、セグメントに追加されたプロファイルが適合しているかどうかを確認できます。

プロファイルページで、 [!UICONTROL 属性] 」タブで、次の条件を満たしていることを確認します。層は、銀、金、プラチナ、ダイヤモンドである必要があります。

![プロファイル属性](assets/C1-S1-profile-attributes.png)

また、 [!UICONTROL セグメントのメンバーシップ] タブ：セグメントが表示されます。

![セグメントのメンバーシップ](assets/C1-S1-profile-segment-membership.png)

>[!TAB 作業内容を確認する]

セグメントフィールド： [!UICONTROL 属性] > [!UICONTROL XDM 個人プロファイル] > [!UICONTROL ロイヤルティ] > [!UICONTROL 層]

セグメントは次のようになります。

![セグメント — アクティブな顧客](/help/challenges/assets/C1-S1.png)

コードは次のようになります。

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### 手順 2:ジャーニーの作成 — Summer Collection のお知らせ

>[!BEGINTABS]

>[!TAB タスク]

#### 夏物コレクションのお知らせの送信

1 つの代理店が、E メールのデザインを含む 4 つのHTMLファイルを提供しました。

* `SeasonalCollectionEmail.html`
* Luma Men&#39;s Collection の E メール
* Luma Women&#39;s Collection の E メール
* Luma - 20%オフコレクション電子メール

1. [季節ごとのコレクションの電子メールファイルをダウンロード](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. という名前のジャーニーを作成します。 *Luma - Summer Collection のお知らせ* 次のガイドラインに従います。

   1. 送信 *Luma — 新しい夏物コレクションのお知らせ* 電子メールの送信先 *アクティブな顧客* セグメントに含まれ、10%のオーディエンスをコントロール母集団として含む
      * メッセージタイトル *Luma — 夏物コレクションのお知らせ*
      * 件名 *（受信者の名）、新しい Luma サマーコレクションが登場します。*
      * 提供されたHTMLファイルを使用 `SeasonalCollectionEmail.html` 電子メール本文の
   2. 2 日待ってから、よりターゲットを絞ったコンテンツを含むフォローアップメールメッセージを送信します。
      * 男性の顧客が **ルマメンズコレクション** 電子メール。
         * メッセージタイトル： *ルマメンズコレクション*
         * 件名： *（受信者の名），メンズニューアスレチックギアを探索！*
         * メール本文： `MensCollectionEmail.html` 電子メール本文の
      * 女性のお客様が **Luma Women&#39;s Collection** 電子メール。
         * メッセージタイトル： *Luma Women&#39;s Collection*
         * 件名： *（受信者の名）、Luma の Women Collection を参照してください。*
         * メール本文： `WomensCollectionEmail.html`
      * その他のお客様は、 **Luma - 20 %オフコレクション** 電子メール。
         * メッセージタイトル： *Luma - 20 %オフコレクション*
         * 件名： *（受信者の名）、20%オフの販売をお楽しみください。*
         * メール本文： `20OOffCollectionEmail.html`
   3. 上記のターゲット E メールを送信した後、E メールが開かれるまで 2 日待ちます
   4. ターゲットとする E メールが 2 日以内に開封されない場合は、 **Luma - 20 %off コレクションのメール** 最終的なリターゲティングの試みとして


>[!TAB 達成基準]

#### E メールのプレビュー

**電子メールメッセージ#1 - Luma — 夏コレクションのお知らせ**

E メールのプレビュー：

1. テストプロファイルを追加します。ルイーズ・ペッティ：
   1. ID 名前空間： *Luma CRM ID*
   2. ID 値： *d1f132f9f9502bba047a6ec86c4b61f9*

結果:
* 件名は次のようになります。ルイーズ新しいルマコレクションが登場！
* E メールの本文は、プレビューで確認した内容と一致します。 [新しい季節のコレクション発表](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**メールメッセージ#2 - Luma メンズコレクション**

自分に配達確認を送信する：

1. テストプロファイルを追加します。スタンレイ・ストーク：
   1. ID 名前空間： *Luma CRM ID*
   1. ID 値: `4f34057d9d9e792c28ba18ecae378e98`
1. テストプロファイルを選択します。スタンレイ・ストーク。
1. 自分に配達確認を送る。

結果:\
E メールが届きます。 件名は次のようになります。 *スタンレイメンズニューアスレチックギアを探索！* 電子メールの本文は、プレビューで確認した内容と一致します。 [ルマメンズコレクション](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>配達確認を受け取るまでに数分かかる場合があります。

**E メールメッセージ#3 - Luma Women&#39;s Collection**

テストプロファイルで E メールをプレビュー *ルイーズ・ペッティ。*

* 件名は次のようになります。 *ルイーズ、ルマの女性コレクションを探索！*
* E メールの本文は、プレビューで確認した内容と一致します。 [Luma Women&#39;s Collection](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**E メールメッセージ#4 - Luma 20%オフコレクション**

テストプロファイルで E メールをプレビュー *ルイーズ・ペッティ。*

* 件名は次のようになります。 *ルイーズ、20%の売り上げを楽しむ！*
* E メールの本文は、プレビューで確認した内容と一致します。 [Luma 20 %オフコレクション](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)


#### ジャーニーのテスト

>[!IMPORTANT]
>
>ジャーニーをテストモードに設定する前に、次の手順を実行します。
>
>1. 必ず [!UICONTROL セグメントを読み取りアクティビティ] には、名前空間がに設定されています **Luma CRM ID(lumaCrmId)**
>1. 各電子メールで、電子メールが電子メールアドレスに送信されるように、電子メールのデフォルトの電子メールパラメーターを上書きします。
   >    * 目の記号をクリックして、非表示の値を表示します。
   >    * 電子メールパラメータで、T 記号をクリックします（パラメータの上書きを有効にします）。

      >
      >      ![E メールパラメーターの上書き](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * をクリックして、 [!UICONTROL 住所] フィールド
   >    * 次の画面で、電子メールアドレスを括弧で囲んで追加します。 `"yourname@yourdomain"` 式エディターで、「 ok 」をクリックします。

>


ジャーニーをテストし、自分のアカウントにメールを送信します。

1. ジャーニーをテストモードにします。
1. 一度に 1 つのプロファイルを選択します。
1. 待機時間：タイマーを 120 秒に設定します（フィールドに入力します）。
1. トリガープロファイルの入口
1. 次のいずれかを使用して、各ブランチをテストできます *Luma CRM Id* プロファイル識別子として：
   * 女性：Leora Dietsche、ID 値：`a8f14eab3b483c2b96171b575ecd90b1`
   * 男性：スタンレイ・ストーク、ID 値： `4f34057d9d9e792c28ba18ecae378e98`
   * 性別が指定されていません：Louise Petti、ID 値： `d1f132f9f9502bba047a6ec86c4b61f9`

1. プロファイルの入口をトリガーした後、最初の E メールが届きます。 ヘッダーは、選択したプロファイルに応じてパーソナライズする必要があります。
1. ジャーニーは、それぞれの分岐に進み、関連する E メールを受け取る必要があります ( 例： *ジェナ*&#x200B;を返した場合、 *Luma Women&#39;s Collection* 電子メール ) を確認します。
1. 2 つ目の E メールを開くと、ジャーニーは終了します。
1. 手順 4 を繰り返すことができます。 - 7. を設定します。
1. タイムアウトをテストするには、待機時間を 30 秒に設定し、再度トリガーを設定します。
1. 受信したメールを開かない ( メール (!) をプレビューしない ) 待ち時間が過ぎ去る

次の電子メールが届きます。

* Luma — 新しい季節物集の発表
* 使用したテストプロファイルに応じて、次のいずれかの電子メールが届きます。
   * レオラ：Luma Women&#39;s Collection
   * スタンレイ：ルマメンズコレクション
   * ルイーズ：Luma - 20%引きのコレクション
* 2 通目の E メールを開いていない場合は、次の手順に従います。Luma - 20%引きのコレクション

>[!TAB 作業内容を確認する]

ジャーニーは次のようになります。

![ジャーニー](/help/challenges/assets/c3-j1-journey.png)

**条件 — コントロール母集団：**

![コントロール母集団](/help/challenges/assets/c3-j1-condition-control-group.png)

**条件 — 性別：**\

![条件 — 性別](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
