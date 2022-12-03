---
title: 夏物コレクションのお知らせの作成 — チャレンジ
description: 新しい Luma の夏季コレクションをプロモーションするために、夏期コレクションのお知らせを既存の顧客のセグメントに送信します。
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: 4314f8090d4462ea8735279078fa53b70c5de551
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 3%

---

# 夏物コレクションのお知らせの作成 — チャレンジ

![AJO 夏コレクションのお知らせバナー](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| 課題 | 夏物コレクションのお知らせの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[セグメントの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [HTML 電子メールコンテンツの読み込みと作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[ユースケース - セグメントの読み取り](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| ダウンロードするアセット | [季節ごとのコレクションの電子メールファイル](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## ザストーリー

架空のスポーツアパレル会社、Luma は、最新のアパレルやギアコレクションの宣伝や、既存顧客の売り上げの促進を目指しています。 Luma は新しい夏物コレクションを開始しており、様々な顧客セグメントを具体的にターゲットにしたいと考えています。

## 課題

Luma マーケティングチームから、Journey Optimizerで夏物コレクションのマーケティングキャンペーンを実装するように求められます。 課題は次のとおりです。

* プロモーションを受け取る資格のあるプロファイルを定義するセグメントを作成します。
* ジャーニーの構築

### 手順 1:セグメントの定義 — アクティブな顧客

>[!BEGINTABS]

>[!TAB タスク]

#### Journey Optimizerでのセグメントの作成

* Journey Optimizerで `Active Customers`.
* セグメントには、アクティブな Luma の顧客のみを含める必要があります。
* アクティブな顧客は、Luma のロイヤルティプログラム（シルバー、ゴールド、プラチナ、ダイヤモンド）の層を持つ顧客と定義されます。


>[!TAB 達成基準]

セグメントビルダーで、認定済みプロファイルの推定数を確認できます。 トレーニングサンドボックスデータを使用する場合、1.29 KB 中 753 個の認定プロファイルがあります。

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


### 手順 2:ジャーニーの作成 — 夏のコレクションのお知らせ

>[!BEGINTABS]

>[!TAB タスク]

#### 夏物コレクションのお知らせを送信

1 つの代理店が、E メールのデザインを含む 4 つのHTMLファイルを提供しました。

* SeasonalCollectionEmail.html
* Luma Men&#39;s Collection の E メール
* Luma Women&#39;s Collection の E メール
* Luma - 20%オフコレクション電子メール

1. [季節ごとのコレクションの電子メールファイルをダウンロード](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. という名前のジャーニーを作成します。 `Luma - Summer collection announcement` 次のガイドラインに従います。

   1. 送信 *Luma — 新しい夏物コレクションのお知らせ* 電子メールの送信先 *アクティブな顧客* セグメントに含まれ、10%のオーディエンスをコントロール母集団として含む
      * メッセージタイトル `Luma - Summer Collection Announcement`.
      * 件名 `(recipient's first name), the new Luma summer collection is here!`.
      * 提供されたHTMLファイルを使用 *SeasonalCollectionEmail.html* 電子メール本文の
   2. 2 日待ってから、よりターゲットを絞ったコンテンツを含むフォローアップメールメッセージを送信します。
      * 男性の顧客が **ルマメンズコレクション** 電子メール。
         * メッセージタイトル： `Luma Men's Collection`
         * 件名: `(recipient's first name), explore Men's New athletic gear!`
         * メール本文： *MensCollectionEmail.html* 電子メール本文の
      * 女性のお客様が **Luma Women&#39;s Collection** 電子メール。
         * メッセージタイトル： `Luma Women's Collection`
         * 件名: `(recipient's first name), explore Luma's Women Collection!`
         * メール本文： *WomensCollectionEmail.html*
      * その他のお客様は、 **Luma - 20 %オフコレクション** 電子メール。
         * メッセージタイトル： `Luma - 20 % off Collection`
         * 件名: `(recipient's first name), enjoy 20% off sales!`
         * メール本文： *20OffCollectionEmail.html*
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
   2. ID 値: `4f34057d9d9e792c28ba18ecae378e98`
1. テストプロファイルを選択します。スタンレイストーク
2. 自分に配達確認を送信

結果:\
E メールが届きます。 件名は「Stanleigh, explore Men&#39;s New astletic gear!」と読むべきです。 電子メールの本文は、プレビューで確認した内容と一致します。 [ルマメンズコレクション](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>配達確認を受け取るまでに数分かかる場合があります。

**電子メールメッセージ#3 - Luma Women&#39;s Collection**

テストプロファイル「Louise Petti」で E メールをプレビューします。

* 件名は次のようになります。 *ルイーズ、ルマの女性コレクションを探索！*
* E メールの本文は、プレビューで確認した内容と一致します。 [Luma Women&#39;s Collection](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**メールメッセージ#4 - Luma 20 %オフコレクション**

テストプロファイル「Louise Petti」で E メールをプレビューします。

* 件名は次のようになります。 *ルイーズ、20%の売り上げを楽しむ！*
* E メールの本文は、プレビューで確認した内容と一致します。 [Luma 20 %オフコレクション](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)

**忘れずにメールを公開してください。**

#### ジャーニーのテスト

>[!IMPORTANT]
>
>ジャーニーをテストモードに設定する前に、次の手順を実行します。
>
>1. 「セグメントを読み取り」アクティビティの名前空間がに設定されていることを確認します。 **Luma CRM ID(lumaCrmId)**
>1. 各電子メールで、電子メールが電子メールアドレスに送信されるように、電子メールのデフォルトの電子メールパラメーターを上書きします。
   >    * 目の記号をクリックして、非表示の値を表示します。
   >    * E メールパラメータで、T 記号をクリックします（パラメータの上書きを有効にする）。

      >
      >      ![E メールパラメーターの上書き](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * 「アドレス」フィールドをクリックします。
   >    * 次の画面で、括弧内にメールアドレスを追加します。 `"yourname@yourdomain"` 式エディターで、「 ok 」をクリックします。

>


ジャーニーをテストし、自分のアカウントにメールを送信します。

1. ジャーニーをテストモードにする
2. 一度に 1 つのプロファイルを選択
3. 待機時間：タイマーを 120 秒に設定します（フィールドに入力します）。
4. トリガープロファイルの入口
5. 各分岐をテストするには、次のいずれかの電子メールアドレスをプロファイル識別子として使用します。
   * 女性：Louise Petti、ID 値： *d1f132f9f9502bba047a6ec86c4b61f9*
   * 男性：スタンレイ・ストーク、ID 値： `4f34057d9d9e792c28ba18ecae378e98`
   * 性別が指定されていません：Leora Dietsche, a8f14eab3b483c2b96171b575ecd90b1

6. プロファイルの入口をトリガーすると、最初の E メールが届き、選択したプロファイルに応じてヘッダーがパーソナライズされます。
7. ジャーニーは各分岐に続き、関連する E メールを受け取る必要があります（例えば、Jenna を選択した場合は、「Luma Women&#39;s Collection」という E メールを受け取る必要があります）。
8. 2 つ目の E メールを開くと、ジャーニーは終了します
9. 手順 4 を繰り返すことができます。 - 7. を設定します。
10. タイムアウトをテストするには、待機時間を 30 秒に設定し、再度トリガーを設定します。
11. 受信したメールを開かない ( メール (!) をプレビューしない ) 待ち時間が過ぎ去る

次の電子メールが届きます。

* Luma — 新しい季節物集の発表
* 使用したテストプロファイルに応じて、次のいずれかの電子メールが届きます。
   * ジェナ：Luma Women&#39;s Collection
   * クリス：ルマメンズコレクション
   * ベニー：Luma - 20%引きのコレクション
* 2 通目の E メールを開いていない場合は、次の手順に従います。Luma - 20%引きのコレクション

>[!TAB 作業内容を確認する]

ジャーニーは次のようになります。

![ジャーニー](/help/challenges/assets/c3-j1-journey.png)

**条件 — コントロール母集団：**

![コントロール母集団](/help/challenges/assets/c3-j1-condition-control-group.png)

**条件 — 性別：**\

![条件 — 性別](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
