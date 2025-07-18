---
title: ソリューションのテスト
description: シンプルな web ページを作成して、オファーのインプレッションとクリックイベントを取り込みます。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# ソリューションのテスト

ソリューションをエンドツーエンドでテストするには、[weather-offers.html](assets/weather-offers.html) および [capture-impressions-click-events.js](assets/capture-impressions-click-events.js) ファイルを web サーバーまたは Github ページなどの公開ホスティングサービスでホストする必要があります。 ブラウザーの Geolocation API は HTTPS または localhost でのみ機能するので、これが必要になります

## 提供されたファイルをダウンロードします

[HTML ファイル](assets/weather-offers.html)

[Javascript ファイル](assets/capture-impressions-click-events.js)

## Javascript ファイルのサーフェス URL を更新します

`capture-impressions-click-events.js` を開き、` "web://yourdomain.com/weather/weather-offers.html#offerContainer"` をHTML ファイルがホストされている実際のドメインに置き換えて、`yourdomain.com` を更新します。


## Adobe Experience Platform タグプロパティの更新

Weather-offers.html ファイルをテキストエディターで開き、スクリプトタグを、このチュートリアルの前の手順で作成したAdobe Experience Platform タグプロパティのスクリプトタグに置き換えます。 必ずファイルを保存してください。

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## オファーの操作

- お気に入りのブラウザーで Web ページを開きます。

- 許可 _**位置追跡**_. これは、場所に基づいて天気の詳細を取得するために必要です。

- インタラクトイベントをトリガーにするオファーのボタンをクリックします。

## レポートを表示

- Journey Optimizerにログインします

- ジャーニー管理/ キャンペーンに移動します。

- キャンペーンをクリックして、レポートメニューから適切なレポートを選択します。
