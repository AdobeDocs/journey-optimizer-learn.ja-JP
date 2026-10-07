---
title: 解決策をテスト
description: シンプルなweb ページを作成して、オファーのインプレッションとクリックイベントをキャプチャします。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18526
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%
---
# 解決策をテスト

## サンプルアセットのデプロイ

Node.jsがインストールされていない場合は、ここからダウンロードして[&#x200B; インストールします](https://nodejs.org/)

次のコマンドを実行してインストールを確認します。

`node -v`

`npm -v`

## プロジェクトフォルダーの設定

次のコマンドを使用して、サンプルアプリ用の新しいディレクトリを作成します。

`mkdir frequency-capping `

`cd frequency-capping `

## プロジェクトの初期化

`npm init -y`

## 必要なフレームワークのインストール

`npm install express`

## アセットファイルをコピー

* [server.zip](assets/server.zip)の内容を解凍して、`frequency-capping` フォルダーに配置します。
* [public.zip](assets/public.zip)のコンテンツを「frequency-capping」フォルダーに抽出します

## JavaScript ファイルのサーフェス URLを更新します

`public\scripts`にある`frequency-capping.js`を開き、キャンペーンで使用されているチャネル設定と一致するようにSURFACES プロパティを更新します

## 開始ノード js サーバー

`c:\frequency-capping` フォルダーに移動します。 `node server.js` コマンドを実行して、ポート 3000でノード js サーバーを開始します


## Adobe Experience Platform Tags プロパティの更新

テキストエディターで`public` フォルダーにある`frequency-capping.html` ファイルを開き、このチュートリアルの前の手順で作成したAdobe Experience Platform タグプロパティのスクリプトタグにスクリプトタグを置き換えます。 必ずファイルを保存してください

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## オファーの操作

* お気に入りのブラウザーで[web ページ &#x200B;](http://localhost:3000)を開きます。
* オファーの操作
* ページの更新
* 頻度の上限ルールに応じて、新しいオファーが表示されます

## レポートを読む

* Journey Optimizerへのログイン
* ジャーニー管理/ キャンペーンに移動します
* キャンペーンをクリックし、レポートメニューから適切なレポートを選択します。
