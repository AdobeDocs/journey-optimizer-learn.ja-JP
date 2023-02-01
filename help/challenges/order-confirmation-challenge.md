---
title: 注文確認メールの作成
description: トランザクションメッセージの作成およびパーソナライズ方法に関する知識をテストします
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 70815c3cd30de22aad7ec667b8baf9b4c8642491
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 82%

---


# 注文確認メールの作成

![注文確認](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 課題 | 注文確認トランザクションメールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[メッセージエディターでのメールコンテンツの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=ja)</li> <li>[パーソナライゼーションに関するコンテキストイベント情報の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=ja)</li><li>[パーソナライゼーションへのヘルパー関数の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=ja)</li></ul> |
| ダウンロードするアセット | [注文確認アセット](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## ストーリー

Luma は、オンラインストアを立ち上げようとしており、顧客が注文したら注文確認メールを送信して、優れたカスタマーエクスペリエンス（顧客体験）を実現したいと考えています。



## 課題

Luma の顧客がオンラインでの注文を完了したときに注文確認メールを送信するジャーニーを作成します。

>[!BEGINTABS]

>[!TAB タスク]

1. 「`Luma - Order Confirmation`」というジャーニーの作成
2. イベントの使用： `LumaOnlinePurchase`
3. `Luma - Order Confirmation` という注文確認メールを作成します。

* カテゴリはトランザクション - 必ずトランザクションメールサーフェスを選択します。
* 件名は、受信者の名前（名）でパーソナライズする必要があり、「ご購入いただきありがとうございます」というフレーズを含める必要があります。
* `Luma - Order summary` テンプレートを使用し、それを変更します。
   * を削除します。 `You may also like` セクション
   * E メールの下部に配信停止リンクを追加

メールは次のような構造にしてください。
<table>
<tr>
<td>
  <div>
     <strong> ヘッダーセクション</strong>
      </div>
  </td>
  <td>
      <p>
     <li>luma_logo.png</li>
    <li>Luma の web サイト（https://publish1034.adobedemo.com/content/luma/us/en.html）へのリンクが必要です。</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>注文確認セクション</strong>
  </td>
  <td>
    <p>
    <strong>テキスト</strong><p>
    <em>おい {firstName}</em><p>
   <div>
    <p>
     <em>注文が完了しました。
    <p>パッケージが出荷されると、追跡番号が記載されたメールが送信されますので、注文を追跡できます。</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong>出荷先セクション</strong>
      </div>
      <p>
      <li>姓と名はプロファイルから取得されます。
      <li>テンプレートのハードコードされたアドレスを <b>配送先住所</b>
      <li>住所の詳細は、イベント（番地 1、市区町村、郵便番号、都道府県）のコンテキスト属性です
      <li> ディスカウント、合計、到着の削除</p>
  </td>
  <td>
  <p> 出荷先：</p>
      <em>{firstName} {lastName}<br>
     { 番地 1}<br>
     {City}、{State}、{postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>注文の詳細セクション</strong>
      </div>
       <p><li>このセクションを <b>送付先</b> 」セクションに入力します。
      </p><br>
      <p><b>ヒント:</b>
      <li>このセクションの構造コンポーネント「1:2 列左」を使用
      <li>これは、コンテキストイベント情報です。
      <li>[!UICONTROL helper function] の [!UICONTROL Each] を使用します。
      <li>コードエディターの形式に切り替えて、コンテキストデータを追加します。
  </td>
  <td>
    <strong>ヘッダー</strong>
    <p>
    <em>注文：`purchaseOrderNumber`</em>
    </p>
    <strong>注文された製品のリスト：</strong>
  <p>各項目は、次のような形式にする必要があります：
   <img alt="順序" src="./assets/c2-order.png"> 
</p>
</td>
  </tr>
</table>


>[!TIP]
>
>ジャーニーのトラブルシューティングを可能にするベストプラクティスは、タイムアウトやエラーの場合に、すべてのメッセージアクションに代替パスを追加することです。

>[!TAB 成功基準]

テストモードで作成したジャーニーをトリガーし、自身にメールを送信します。

1. 目のアイコンをクリックして、非表示の値を表示します。
   1. メールパラメーターで、T 記号をクリックします（パラメーターの上書きを有効にする）
      ![メールパラメーターの上書き](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. 「アドレス」フィールドをクリック
   3. 次の画面で、式エディターの括弧内にメールアドレス *yourname@yourdomain* を入力し、「OK」をクリックします。
2. ジャーニーをテストモードにする
3. 次のパラメーターを使用してイベントをトリガーします。
   * プロファイル識別子の設定：ID 値：`a8f14eab3b483c2b96171b575ecd90b1`
   * イベントタイプ：commerce.purchases
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 6253728
   * `SKU:` LLMH09
   * `City:` ワシントン
   * `Postal Code:` 20099
   * `State`:DC
   * `Street:` ティエラーテラス

指定された製品が記載された、パーソナライズされた購入確認メールが届きます。

* 件名には、テストプロファイルの名の Leora が含まれている必要があります。
* 注文詳細セクションには、テスト中に入力した注文詳細を入力する必要があります

>[!TAB 作業内容の確認]

**ジャーニー**

![ジャーニー](/help/challenges/assets/c2-journey.png)


**メール**

**件名：**

ご購入ありがとうございました。 {{ profile.person.name.firstName }}!

電子メールの本文は次のようになります。

![メール](//help/challenges/assets/c2-email.png)

**出荷先セクション：**

コードは、次のようになります。

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* は別の番号になります。

ヒント：各行を個別にパーソナライズする

**注文詳細セクション：**

コードは、次のようになります。

ヘッダー：

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**製品のリスト：**

ヘルパー関数「each」を使用して、製品のリストを作成します。テーブルに表示します。これは、コードが次のようになるものです（イベント ID などの特定の変数を使用した場合）。 `454181416` お客様の組織 ID が `techmarketingdemos` ):

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p><p>Quantity: {{context.journey.events.454181416.productListItems.quantity}}</p></div></div></th></tr> {{/each}}
```

**価格合計：**

合計：`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]