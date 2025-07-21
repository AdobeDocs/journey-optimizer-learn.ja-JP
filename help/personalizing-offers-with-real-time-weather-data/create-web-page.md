---
title: ソリューションのテスト
description: シンプルな web ページを作成し、リアルタイムの気温データを使用して、コンテキストオファーのパーソナライゼーションをテストします。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 609a5ddf-d6c6-4f19-bd7f-bca8c266b759
source-git-commit: 9c11ebd2e52de18792e9fa135db955eeeb243673
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# ソリューションのテスト

ソリューションをエンドツーエンドでテストするには、[weather-offers.html](assets/weather-offers.html) および [weather-related-offers-script.js](assets/weather-related-offers-script.js) ファイルを web サーバーまたは Github ページなどの公開ホスティングサービスでホストする必要があります。 これは、次の理由で必要になります。
- ブラウザーの Geolocation API は、HTTPS または localhost でのみ機能します

物事を整理し、相対パスが正しく機能するように、ソリューションをホストする際には次のフォルダー構造を推奨します。

![folder-structure](assets/folder-structure.png)

## 提供されたファイルをダウンロードします

[HTML ファイル](assets/weather-offers.html)

[Javascript ファイル](assets/weather-related-offers-script.js)


## Javascript ファイルのサーフェス URL を更新します

`weather-related-offers-script.js` を開き、` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`bt を更新して、`yourdomain.com` をHTML ファイルがホストされている実際のドメインに置き換えます。

## Adobe Experience Platform タグプロパティの更新

Weather-offers.html ファイルをテキストエディターで開き、スクリプトタグを、このチュートリアルの前の手順で作成したAdobe Experience Platform タグプロパティのスクリプトタグに置き換えます。 必ずファイルを保存してください。

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```



## Web ページの機能

Web ページは、リアルタイムの温度データを使用してコンテキストオファーのパーソナライゼーションをテストするように作成されます。 ユーザーがページを訪問すると、ブラウザーで位置情報アクセスの入力を求められます。 承認されると、ページは OpenWeatherMap API を介して現在の天気の詳細（気温、条件、市区町村など）を取得します。 このコンテキストデータはユーザーに表示され、Adobe web SDK（Alloy）を使用してAdobe Experience Platformに送信されます。

sendEvent 呼び出しは、renderDecisions: false で設定されます。つまり、Adobe Journey Optimizerから返されるオファーは手動で処理されます。 スクリプトは、判定応答を処理し、コンテンツをデコードして、最も関連性の高いオファーを指定されたコンテナ（#offerContainer）に動的に挿入します。

## JavaScriptとは

JavaScriptは、ユーザーの場所に基づいて動的に天気情報を取得し、Adobe Experience Platform（AEP）を使用してパーソナライズされたオファーを提供します。 手順の分類を次に示します。

1. **Alloy のロード待ち**

   スクリプトは、パーソナライゼーションリクエストを行う前に、Adobe Web SDK（Alloy）が完全に読み込まれるようにします。

2. **ユーザーの場所を取得**

   ブラウザーの Geolocation API を使用して、ユーザーの現在の緯度と経度を取得します。

3. **天気データを取得**

   OpenWeatherMap API を呼び出して、現在の天気の詳細を取得します。

   温度（単位：°F）

   気象条件（「雨」、「晴」など）

   市区町村名

   湿度

4. **Web ページに天気情報を表示**

   次のようなメッセージで DOM を更新します。

   「サンディエゴの現在の気温は、晴れた空で 72°F です。」

5. **AEPに天気コンテキストを送信**

   alloy （&quot;sendEvent&quot;）を使用して、コンテキストの天気データをAEPに送信します

   ```javascript
   xdm: {
   eventType: "decisioning.request",
   _techmarketingdemos: {
   temperature: temp,
   weatherConditions: condition,
   cityName: city
     }
   }
   ```

6. **オファーの取得とレンダリング**

   AJO Decisioning から返されたオファーを受信します。

   HTML コンテンツをデコードします。

   オファーをに動的に挿入します。 <div id="offerContainer"> 要素にオファーコンテンツが返されます。

## 次の手順

[AJO Decisioning の影響を測定およびレポートします。](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/reporting-on-ajo-od/introduction)

