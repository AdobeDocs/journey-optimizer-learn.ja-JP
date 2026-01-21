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
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 1%

---

# ソリューションのテスト

## サンプルアセットのデプロイ

Node.js がインストールされていない場合は、ダウンロードして [ ここからインストールしてください ](https://nodejs.org/)

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

* [server.zip](assets/server.zip) を解凍し、`frequency-capping` フォルダーに配置します。
* [public.zip](assets/public.zip) の内容を「frequency-capping」フォルダーに抽出します。

## Javascript ファイルのサーフェス URL を更新します

`frequency-capping.js` にある `public\scripts` を開き、キャンペーンで使用されているチャネル設定と一致するように surfaces プロパティを更新します。

## Node js サーバーを起動します。

フォルダーに移動 `c:\frequency-capping` ます。 `node server.js` コマンドを実行して、ポート 3000 で node js サーバーを起動します。


## Adobe Experience Platform タグプロパティの更新

テキストエディターの `frequency-capping.html` フォルダーにある `public` ファイルを開き、スクリプトタグを、このチュートリアルの前の手順で作成したAdobe Experience Platform タグプロパティのスクリプトタグに置き換えます。 必ずファイルを保存してください。

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## オファーの操作

* お気に入りのブラウザーで [web ページ ](http://localhost:3000) を開きます。
* オファーとのインタラクション
* ページの更新
* フリークエンシーキャッピングルールに応じて、新しいオファーが表示されます

## レポートを表示

* Journey Optimizerにログインします
* ジャーニー管理/ キャンペーンに移動します。
* キャンペーンをクリックして、レポートメニューから適切なレポートを選択します。
