---
title: ソリューションをテストする Web ページの作成
description: 意思決定を使用して配信されたパーソナライズされたオファーをテストする Web ページ。
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# ソリューションをテストする Web ページの作成

このサンプルアプリケーションでは、CRM ID がAdobe Experience Platform（AEP）に送信される前に、ユーザーの資格情報がサーバーサイドで検証される、実際のログインフローをシミュレートします。 ローカルの Node.js サーバーを使用すると、web ページを安全に提供し、基本的な認証ロジックを処理し、Adobe Launch や web SDKの機能に干渉する可能性のあるブラウザー制限（ローカルファイルへのアクセスのブロックや CORS ヘッダーの欠落など）を回避できます。 このセットアップにより、実際の実稼動環境に近いエクスペリエンスが得られます。

パーソナライズされたオファーは、ユーザーがログインした後に表示されます。この時点で、ユーザーの CRM ID と ECID （Experience Cloud ID）の間の ID のステッチが完了します。 この ID ステッチにより、Adobe Journey Optimizer（AJO）がプロファイルを正確に認識し、ターゲットオファーを返すことができるようになります。

ログインに成功すると、パーソナライゼーションリクエストがAJOに送信され、使用可能なオファーが取得されます。 これらのオファーはHTML フラグメントとして返され、それぞれが data-tags 属性（data-tags=&quot;ajo offer-vacation-based-cd zip-92128 income-high&quot;など）を持つ埋め込まれます。この属性には、オファー名と、郵便番号や収入レベルなどのセグメント化の詳細が含まれます。

JavaScriptは、次にこれらのHTML ブロックを解析して、各ブロックをカルーセルアイテムコンテナ内にラップします。 項目はカルーセルトラック内で水平方向に配置され、切り替え可能なナビゲーションを実現します。 前へボタンおよび次へボタン（◀ および ▶）を使用すると、パーソナライズされたオファーを 1 つずつ確認できます。

このセットアップにより、レスポンシブでカスタマイズされたエクスペリエンスが提供され、各ユーザーの ID がプラットフォーム間で安全に結び付けられた後にのみ、財務プロファイルに関連するオファーが各ユーザーに表示されるようにします。

## このソリューションのテスト

* 既存の Node.js プロジェクト内に ranking-formula という名前のフォルダーを作成します。

* [ 提供されたファイルをこのランキング式フォルダー ](assets/ranking-formula.zip) に解凍します。

* フォルダーに移動し、サーバーを起動して、アプリを実行します。
   * `cd ranking-formula`

   * `node server.js`


* ブラウザーを開き、http://localhost:3000/formula.htmlに移動します。

* alice/pass123 を使用してログイン

Alice は 92128 の郵便番号に存在するので、その場所に合わせたオファーが表示されます。