---
title: 注文確認メールの作成
description: トランザクションメッセージの作成およびパーソナライズ方法に関する知識をテストします。
jira: KT-7531
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 8b8d163b65dbd34f769a26231638f0bfeb6eb0b1
workflow-type: ht
source-wordcount: '654'
ht-degree: 100%

---


# 注文確認メールの作成

![注文確認](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 課題 | 注文確認トランザクションメールの作成 |
|---|---|
| ペルソナ | ジャーニーマネージャー |
| 必要なスキル | <ul><li>[メッセージエディターでのメールコンテンツの作成](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/create-content-with-the-email-designer.html?lang=ja)</li> <li>[パーソナライゼーションに関するコンテキストイベント情報の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=ja)</li><li>[パーソナライゼーションへのヘルパー関数の使用](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=ja)</li></ul> |
| ダウンロードするアセット | [注文確認アセット](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

{style="table-layout:auto"}

## ストーリー

Luma はオンラインストアを立ち上げようとしており、優れたカスタマーエクスペリエンス（顧客体験）を実現したいと考えています。顧客が注文したら、顧客に注文確認メールを送信します。

## 課題

Luma の顧客がオンラインでの注文を完了したときに注文確認メールを送信するジャーニーを作成します。

>[!BEGINTABS]

>[!TAB タスク]

1. `Luma - Order Confirmation` という名前のジャーニーを作成します。

1. イベント `LumaOnlinePurchase` を使用します。

1. `Luma - Order Confirmation` という&#x200B;**トランザクション**&#x200B;メールを作成します。

   * 件名「`FirstName` 様、ご購入いただきありがとうございます。」

   * `Luma - Order summary` テンプレートを使用し、それを変更します。

      * `You may also like` セクションの削除

      * メールの下部への購読解除リンクの追加

メールは次のような構造にしてください。

<table>
<tr>
<td>
  <div>
     <strong>ヘッダーセクション</strong>
      </div>
  </td>
  <td>
      <p>
     <li>luma_logo.png</li>
    <li>Luma の web サイト https://.adobedemo.com/content/luma/us/en.html へのリンクが必要です。</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>注文確認セクション
 </strong>
  </td>
  <td>
    <p>
    <strong>テキスト</strong><p>
    <em>{firstName} 様</em><p>
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
      <li>姓と名はプロファイルから取り込まれます。
      <li>テンプレートのハードコーディングされた住所を<b>出荷先住所</b>に置き換えます
      <li>住所の詳細は、イベントから得られるコンテキスト属性（番地 1、市区町村、郵便番号、都道府県）です。
      <li> <i>ディスカウント、合計、到着</i>の削除</p>
  </td>
  <td>
  <p> 出荷先：</p>
      <em>{firstName} {lastName}<br>
 {Street 1}<br>
 {City}、{State}、{postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>注文の詳細セクション</strong>
      </div>
       <p><li>このセクションを<b>出荷先</b>セクションの下に追加します。
      </p><br>
      <p><b>ヒント：</b>
      <li>このセクションには、構造コンポーネント <b>1:2 列左</b>を使用します
      <li>これは、コンテキストイベント情報です。
      <li>[!UICONTROL helper function] の [!UICONTROL Each] を使用します。
      <li>コードエディターの形式に切り替えて、コンテキストデータを追加します。
  </td>
  <td>
    <strong>ヘッダー</strong>
    <p>
  注文：<em>{purchaseOrderNumber}</em>
    </p>
    <strong>注文された製品のリスト：</strong>
  <p>注文の各製品を、画像、価格、名前と共にリストします。
  <p>各項目のレイアウトは次のようになります。
 <img alt="順序" src="./assets/c2-order.png"> 
<p><b>リンクを買い物かごに追加</b>
<p>URL 内の注文 ID を発注番号に置き換えます。
 <i>https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId=90845952-c2ea-4872-8466-5289183e4607</i>
</td>
  </tr>
</table>

>[!TIP]
>
>ジャーニーのトラブルシューティングを可能にするベストプラクティスは、タイムアウトやエラーの場合に、すべてのメッセージアクションに代替パスを追加することです。

>[!TAB 成功基準]

テストモードで作成したジャーニーをトリガーし、自身にメールを送信します。

1. テストモードに切り替える前に、テストメールに送信するメールパラメーターを上書きして、メールアドレスに送信します。
   1. メールの詳細表示を開きます。
   1. メールパラメーターセクションで、T 記号をクリックします（パラメーターの上書きを有効にする）
   1. 「アドレス」フィールドをクリック
   1. 次の画面で、式エディターの括弧内にメールアドレス *&quot;yourname@yourdomain&quot;* を入力し、「OK」をクリックします。
1. ジャーニーをテストモードにする
1. 次のパラメーターを使用してイベントをトリガーします。
   * プロファイル識別子の設定：ID 値：`a8f14eab3b483c2b96171b575ecd90b1`
   * イベントタイプ：commerce.purchases
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 90845952-c2ea-4872-8466-5289183e4607
   * `SKU:` LLMH09
   * `City:`サンノゼ
   * `Postal Code:` 95119
   * `State`：CA
   * `Street:` 245 Park Avenue

パーソナライズされた購入確認メールが届きます。

* 件名には、テストプロファイルの名の Leora が含まれている必要があります。

* メール本文は、次のようになります。

![メール](/help/challenges/assets/c2-email.png)

>[!TAB 作業内容の確認]

**ジャーニー**

![ジャーニー](/help/challenges/assets/c2-journey.png)


**メール**

**件名：**

`{{ profile.person.name.firstName }}` 様、ご購入いただきありがとうございます。

**出荷先セクション：**

コードは、次のようになります。

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* は別の番号になります。

ヒント：各行を個別にパーソナライズする

**注文詳細セクション:**

コードは、次のようになります。

ヘッダー：

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**製品のリスト：**

ヘルパー関数「each」を使用して、製品のリストを作成します。テーブルに表示します。コードは、次のようになります（イベント ID などの特定の変数を `454181416` の代わりに使用し、`techmarketingdemos` の代わりに組織 I を使用します）。

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p></div></div></th></tr> {{/each}}
```

**表示順序ボタン：**

`https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId={{context.journey.events.454181416.commerce.order.purchaseOrderNumber}}`

**価格合計：**

合計：`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]