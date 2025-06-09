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
source-git-commit: a9fc14da78e1c67b01aef5dcdd417ce02d36d50a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# ソリューションのテスト

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

   AJOから返されたオファーを受信します。

   HTML コンテンツをデコードします。

   オファーをに動的に挿入します。 <div id="offerContainer"> 要素にオファーコンテンツが返されます。

7. **サンプルAssets**

   ソリューションのテストに使用する Web ページをダウンロードできます

[Web ページ](assets/weather-offers.html)

[JavaScript コード](assets/weather-related-offers-script.js)

