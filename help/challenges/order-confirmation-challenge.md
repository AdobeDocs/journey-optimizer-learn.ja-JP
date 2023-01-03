---
title: 注文確認メールの作成
description: トランザクションメッセージの作成およびパーソナライズ方法に関する知識をテストします
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 4268144ade6588e48fc38cae7e542c227af96827
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 100%

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

Luma の顧客がオンラインでの注文を完了したときに注文確認メールを送信するジャーニーを作成します。Luma

>[!BEGINTABS]

>[!TAB タスク]

1. 「`Luma - Order Confirmation`」というジャーニーの作成
2. イベント `LumaOnlinePurchase` をトリガーとして使用します。
3. `Luma - Order Confirmation` という注文確認メールを作成します。

* カテゴリはトランザクション - 必ずトランザクションメールサーフェスを選択します。
* 件名は、受信者の名前（名）でパーソナライズする必要があり、「ご購入いただきありがとうございます」というフレーズを含める必要があります。
* `Luma - Order summary` テンプレートを使用し、それを変更します。

メールは次のような構造にしてください。
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
    <em>{first name} 様</em><p>
    <li>Alignment: left  </li>
   <li>Text color: rgb(69, 97, 162) #4461a2; 
   <li>font-size: 20px</li>
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
      <p><li>テンプレートのハードコーディングされた住所を出荷先住所に置き換えます。 
      <li>住所の詳細は、イベントから得られるコンテキスト属性（番地、市区町村、郵便番号、都道府県）です。
      <li>姓と名はプロファイルから取得されます。
      <li> ディスカウント、合計、到着の削除</p>
  </td>
  <td>
  <p> 出荷先：</p>
      <em>姓名<br>
住所</em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>注文の詳細セクション</strong>
      </div>
       <p><li>このセクションは、「<b>出荷先</b>」セクションと「<b>注文を表示</b>」ボタンの後に追加します。
      </p><br>
      <p><b>ヒント:</b>
      <li>これは、コンテキストイベント情報です。
      <li>[!UICONTROL helper function] の [!UICONTROL Each] を使用します。
      <li>コードエディターの形式に切り替えて、コンテキストデータを追加します。
      <li>DIV タグを使用して、コンテナに情報を配置します。
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
<strong>製品画像：</strong>
<li>class: cart-item-chair
<li>style: border-box: min-height:40px</li>
<li>padding top and bottom:20px</li>
<li>padding-left:80px</li>
<li>border-radius:0px</li>
<li>コンテナの背景画像として使用</li>
<li>background-position: 0% 50%</li>
<li>background-size: 60px</li>
<li>background-repeat: no-repeat</li>
<p>
<strong>価格：</strong>
<li>形式 = H5</li>
<li>style = box-sizing:border-box</li>
<li>margin-bottom:5px</li>
<li>margin-top:0px;</li>
<p>
<strong>名前と数量：</strong>
<li>class=text-small</li>
<li>style=box-sizing: border-box</li>
<li>padding-top: 5px</li>
<li>color: rgb(101, 106, 119)</li>
<li>font-size:14px</li>
<p>
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
   * 名前：Sprite Yoga Companion Kit
   * 数量：1
   * `Price Total:` 61
   * `Purchase Order Number:` 6253728
   * `SKU:` 24-WG080
   * `productImageURL:` <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>
   * `City:` サンノゼ
   * `Postal Code:` 95110
   * `State`：CA
   * `Street:` 345 Park Ave

指定された製品が記載された、パーソナライズされた購入確認メールが届きます。

* 件名には、テストプロファイルの名の Leora が含まれている必要があります。
* 注文詳細セクションには、テスト中に入力した注文詳細を入力する必要があります

>[!TAB 作業内容の確認]

**ジャーニー**

![ジャーニー](/help/challenges/assets/c2-journey.png)


**メール**

**件名：**

{{ profile.person.name.firstName }} 様、ご購入いただきありがとうございます。

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

![注文詳細セクション](/help/challenges/assets/c2-order-detail-section.png)

コードは、次のようになります。

ヘッダー：

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**製品のリスト：**

ヘルパー関数「each」を使用して、製品のリストを作成します。テーブルに表示します。コードは、次のようになります。

```javascript
<div class="text-container" contenteditable="true">
  <p><span class="acr-expression-field" contenteditable="false">{{#each context.journey.events.454181416.productListItems as |product|}}
    </span></p>
  <div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
    <h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</h5>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</div>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div>
  </div>
  <div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
  {{/each}}<p></p>
  <p></p>
</div>
```

**価格合計：**

合計：`${{context.journey.events.1627840522.commerce.order.priceTotal}}`

**顧客情報セクション**

![顧客の住所](assets/c2-customer-information.png)

パーソナライゼーションは、次のようになります。

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

>[!ENDTABS]