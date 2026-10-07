---
title: ソリューションをテストするWeb ページの作成
description: 決定を使用して配信されたパーソナライズされたオファーをテストするweb ページ。
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00.000Z
jira: KT-18188
recommendations: noDisplay, noCatalog
exl-id: 6b1eec78-153c-4ea5-acfe-2dcc6f1e6078
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
source-wordcount: '348'
ht-degree: 0%
---
# ソリューションをテストするWeb ページの作成

このサンプルアプリケーションは、CRM IDがAdobe Experience Platform（AEP）に送信される前に、サーバーサイドでユーザーの資格情報が検証される実際のログインフローをシミュレートします。 ローカルのNode.js サーバーを使用すると、web ページを安全に配信し、基本的な認証ロジックを処理し、Adobe LaunchまたはWeb SDKの機能を妨げる可能性があるブラウザーの制限（ローカルファイルアクセスのブロックやCORS ヘッダーの欠落など）を回避できます。 この設定により、エクスペリエンスが実際の本番環境に近づきます。

パーソナライズされたオファーは、ユーザーがログインした後にのみ表示され、その時点でユーザーのCRM IDとECID （Experience Cloud ID）の間のIDの合成が完了します。 このID接続により、Adobe Journey Optimizer（AJO）がプロファイルを正確に認識し、ターゲットを絞ったオファーを返すことができるようになります。

ログインが成功すると、パーソナライゼーションリクエストがAJOに送信され、ユーザーが利用できるオファーが取得されます。 これらのオファーはHTML フラグメントとして返され、data-tags=&quot;ajo offer-vacation-based-cd zip-92128 income-high&quot;などのdata-tags属性が埋め込まれ、オファー名とセグメントの詳細（郵便番号や収入レベルなど）が含まれます。

JavaScriptは、これらのHTML ブロックを解析し、カルーセルアイテムコンテナ内で各ブロックをラップします。 アイテムはカルーセルトラック内で水平に配置され、スワイプ可能なナビゲーションを可能にします。 前と次のボタン （◀と▶）を使用すると、ユーザーはパーソナライズされたオファーを1つずつ反転できます。

この設定では、レスポンシブでカスタマイズされたエクスペリエンスを提供し、各ユーザーが自分の財務プロファイルに関連するオファーを確実に受け取れるようにします。これは、プラットフォーム間でIDが安全に接続された後に限ります。

## このソリューションをテスト

* 既存のNode.js プロジェクト内にranking-formulaという名前のフォルダーを作成します。

* 指定した[個のファイルをこのランキング式フォルダーに解凍します。](assets/ranking-formula.zip)

* フォルダーに移動してサーバーを起動し、アプリを実行します。
  * `cd ranking-formula`

  * `node server.js`


* ブラウザーを開き、http://localhost:3000/formula.htmlに移動します。

* alice/pass123を使用したログイン

Aliceは92128の郵便番号に属しているため、その場所に合わせたオファーが表示されます。
