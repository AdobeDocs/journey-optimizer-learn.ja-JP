---
title: 注文の確認を作成
description: トランザクションメッセージの作成方法とパーソナライズ方法に関する知識をテストします
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 4%

---

# 注文確認トランザクション E メールの作成

![注文確認](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 課題 | 注文確認トランザクション E メールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[メッセージエディターでの電子メールコンテンツの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[パーソナライゼーションに関するコンテキストイベント情報の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[パーソナライゼーションへのヘルパー関数の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| ダウンロードするアセット | [注文確認アセット](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## ザストーリー

Luma は、オンラインストアを立ち上げており、顧客が注文した後に注文確認 E メールを送信して、優れた顧客体験を実現したいと考えています。

トランザクション注文確認メッセージを作成し、パーソナライズします。

## 必要なものは揃っているか？

## 課題

Luma の顧客がオンラインでの注文を完了したときにトリガーされる注文確認 E メールを作成します。

### 注文確認 E メールの作成

「(your name)_Luma - Order confirmation」というタイトルの新しい電子メールメッセージを作成します。 件名は、受信者の名でパーソナライズする必要があります。また、「ご購入ありがとうございました」というフレーズを含める必要があります。

Luma ブランドのガイドラインに従い、E メールは次の構造にする必要があります。

<table>
<tr>
<td>
  <div>
     <strong> ヘッダーセクション</strong>
      </div>
  </td>
  <td>
    <strong>Luma ロゴ</strong>
      <p>
     <li>luma_logo.png</li>
    <li>サイズ 35%、背景が白を中央に配置 </li>
    <li>Luma Web サイトへのリンクが必要です。https://publish1034.adobedemo.com/content/luma/us/en.html</li>
    <p>
    ヒント：アセットフォルダー内のメッセージ画像と呼ばれる画像がすべて検索されます。 <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>注文確認セクション
    </strong>
  </td>
  <td>
    <strong>画像</strong><p>
    <li>luma-transactional-order-confirmation-2.jpg </li>
    <li>利益：上、下 (10)<div>
    <p>
    <strong>テキスト</strong><p>
    <em>ご購入ありがとうございました。</em><p>
    <li>整列：left  </li>
   <li>テキストカラー：rgb(101, 106, 119);font-size:14px</li>
    <li>パディング：左 (95)、右 (95)</li><div>
    <p>
     <em>注文が完了しました。
    <p>お客様のパッケージが出荷されたら、追跡番号が記載されたメールをお送りします。お客様のご注文を追跡できます。</p></em>
    </strong><p>
    <li>整列：left  </li>
    <li>テキストカラー：rgb(101, 106, 119);font-size:14px </li>
    <li>パディング：左 (95)、右 (95)</li><div>
    </a>
    <p>
    <strong>ボタン:</strong>
   <p><em>注文を表示</em></p>
      <li>背景色：rgb(25, 121, 195)</li>
      <li>テキストカラー：白</li>
      <li>境界線なし</li>
      <li>高さ：40</li>
      <li>選択した Web サイトにリンクを追加します </li>
      <li>上のテキストに合わせて左揃えにします ( ヒント：コンテナの余白を使用 )</li>
  </td>
 <tr>
<td>
  <div>
     <strong>注文の詳細セクション</strong>
      </div>
      <p>ヒント:
      <li>これはコンテキストイベント情報です。 ジャーニーにメッセージを追加した場合（手順 2 を参照）、コンテキストにのみ追加できます。 E メールをジャーニーに追加し、コンテキストイベント情報を使用して変更する前に、E メールを公開しないでください。</li>
      <li>ヘルパー関数を使用します。各</li>
      <li>コンテキストデータは、HTMLエディターのフォーマットを使用します。 DIV タグを使用して、コンテナに情報を配置します。</li>
  </td>
  <td>
    <strong>ヘッダー</strong>
    <p>
    <em>注文 { 発注書番号 }</em>
    </p>
    <strong>注文された製品のリスト：
  </strong>
  <p>各項目は、次のような形式にする必要があります。
   <img alt="順序" src="./assets/c2-order.png"> 
</p>
<strong>製品画像：</strong>
<li>クラス：買い物かごの椅子
<li>スタイル：border-box:min-height:40px</li>
<li>padding top and bottom:20px</li>
<li>padding-left:80px</li>
<li>border-radius:0px</li>
<li>コンテナの背景画像として使用</li>
<li>background-position:0% 50%</li>
<li>background-size:60px</li>
<li>background-repeat:no-repeat</li>
<p>
<strong>価格:</strong>
<li>形式= H5</li>
<li>style = box-sizing:border-box</li>
<li>margin-bottom:5px</li>
<li>margin-top:0px;</li>
<p>
<strong>名前と数量：</strong>
<li>class=text-small</li>
<li>style=box-sizing:border-box</li>
<li>padding-top:5px</li>
<li>色：rgb(101, 106, 119)</li>
<li>font-size:14px</li>
<p>
</td>
  </tr>
</table>

### ジャーニーの作成

1. ジャーニーを「your name _Luma-Order Confirmation」と呼びます。
1. イベントの使用：LumaOnlinePurchase
1. アクション：手順 1 で作成したメッセージを追加します。
1. メッセージに戻り、コンテキスト属性を追加します。
1. 電子メールを公開

>[!TIP]
>
>ジャーニーのトラブルシューティングを可能にするベストプラクティスは、タイムアウトまたはエラーの場合に、すべてのメッセージアクションに代替パスを追加することです。

+++達成基準

テストモードで作成したジャーニーをトリガーし、自身に E メールを送信します。

1. 目の記号をクリックして、非表示の値を表示します。
   1. E メールパラメータで、T 記号をクリックします（パラメータの上書きを有効にします）。
      ![E メールパラメーターの上書き](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. 「アドレス」フィールドをクリックします。
   3. 次の画面で、括弧内にメールアドレスを追加します。 *yourname@yourdomain* 式エディターで、「 ok 」をクリックします。
2. ジャーニーをテストモードにする
3. 次のパラメーターを使用してイベントにトリガーを設定します。
   * プロファイル識別子の設定：Jenna_Palmer9530@emailsim.io
   * イベントタイプ：commerce.purchases
   * 名前：Sprite Yoga Companion Kit
   * 数量：1
   * 価格合計：61
   * 注文番号：6253728
   * SKU:24-WG080
   * productImageURL: <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>

指定した製品と共に、パーソナライズされた購入確認 E メールが届きます。

* 件名は、テストプロファイルの名で始まる必要があります。ジェナ
* 注文の詳細セクションには、テスト中に入力した注文の詳細を入力する必要があります
* 顧客情報には、テストプロファイルの市区町村と郵便番号が含まれます。

   43913 Thierer Terrace, Washington DC 20099

+++

+++作業内容を確認する

**件名:**

{{ profile.person.name.firstName }}、ご購入ありがとうございました。

**ヘッダーおよび確認セクション：**

![ヘッダーと注文の確認](/help/challenges/assets/c2-header.png)

**注文の詳細セクション：**

![注文の詳細セクション](/help/challenges/assets/c2-order-detail-section.png)

コードは次のようになります。

ヘッダー:

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

製品のリスト：

ヘルパー関数「each」を使用して、製品のリストを作成します。 コードは次のようになります。

```javascript
{{#each context.journey.events.1911672547.productListItems as|product|}}
<div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product._wwfovlab065.productImageURL}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
<h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.priceTotal}}.00</h5>
<div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.name}}</div><div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div></div><div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
{{/each}}

Total: ${{context.journey.events.1627840522.commerce.order.priceTotal}} 
```

**顧客情報セクション**

![顧客の住所](assets/c2-customer-information.png)

パーソナライゼーションは次のようになります。

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

**フッター：**
![フッター](/help/challenges/assets/c2-footer.png)

**ジャーニー**

![ジャーニー](/help/challenges/assets/c2-journey.png)

+++
