---
title: Adobe Journey Optimizerでの JSON コンテンツを使用したPersonalizationの配信
description: Adobe Journey Optimizer（AJO）の JSON コンテンツタイプを活用して、柔軟なデータ駆動型のパーソナライゼーションエクスペリエンスを構築します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-18T00:00:00Z
jira: KT-18387
recommendations: noDisplay, noCatalog
source-git-commit: 9f5b52063605832a9b00c05fb1a93bf60ec7686f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Adobe Journey Optimizerでの JSON コンテンツを使用したPersonalizationの配信

この節は、フロントエンドでのオファーのレンダリング方法をより詳細に制御したい上級ユーザー向けの追加リソースとして提供されます。

コードベースエクスペリエンス（CBE）で JSON コンテンツタイプを使用すると、構造化されたオファーデータを返し、JavaScriptを使用して動的にレンダリングを処理できます。 JSON コンテンツタイプは、カスタムレイアウト、条件付きロジック、またはコンテキストデータとの統合（天気、場所、デバイスタイプなど）が必要なシナリオで特に便利です。

基本的なオファー配信には必要ありませんが、このアプローチにより、開発者は標準のHTML レンダリングの機能を超えて、パーソナライズされたデータ駆動型のエクスペリエンスを柔軟に構築することができます。

## JSON コンテンツタイプを使用して、コードベースのエクスペリエンス（CBE）を作成します。

まず、Adobe Journey Optimizerで新しいコードベースエクスペリエンス（CBE）を作成し、コンテンツ形式を JSON に設定します。 コンテンツタイプは、AJOに対し、構造化されたオファーデータ（offerText、画像、メタデータなど）を、レンダリングされたHTMLではなく JSON オブジェクトとして返すように指示します。 プラットフォーム（Web など）、オファーが表示されるターゲット URL、ページ上の場所（offerContainer などのコンテナ ID）を定義します。 この設定により、web アプリケーションはオファーデータを受け取り、JavaScriptを使用して動的にレンダリングできます。

![json-content-type](assets/cbe-json-content.png)

## CBE とキャンペーンの決定ポリシーの関連付け

JSON コンテンツタイプを使用したコードベースのエクスペリエンス（CBE）を作成すると、決定ポリシーを通じてキャンペーンにリンクされます。 決定ポリシーでは、プロファイルまたはコンテキストデータに基づいて、オファーの実施要件、ランキングおよび配信のロジックを定義します。

決定ポリシーをPersonalization エディターに挿入する場合（アプリ内メッセージやメールの場合など）、出力が有効な JSON 構造を維持していることを確認することが重要です。

キャンペーン内のPersonalization エディター（PE）に決定ポリシーを挿入すると、Adobe Journey Optimizerでは選択したポリシーに基づいて Handlebars ループが自動的に生成されます。 例：
![default-code](assets/handlebar-code-default.png)
このループは、ポリシーによって返されたすべての決定項目を反復処理し、各オファーから offerText フィールドを挿入します。 このデフォルトの構造はHTML コンテンツタイプには適していますが、JSON コンテンツを操作する場合、有効な JSON 配列またはオブジェクトを生成するには、再構築が必要になる場合があります（特に、結果がプログラムで解析されている場合）。

![restructured-code](assets/restructured-code.png)

この Handlebars テンプレートは、オファーオブジェクトの JSON 配列を出力するように設計されています。この配列では、各オブジェクトに単一の offerText フィールドが含まれています。 指定した決定ポリシーによって返された決定項目をループし、各 offerText を JSON オブジェクト形式でラップします。

## JSON オファー応答の解析

AJOからの応答には、`propositions[].items[].data.content[]` 構造の下にパーソナライズされた意思決定項目が JSON 形式で含まれます。 各コンテンツ項目には、offerText などのフィールドが含まれます。

```javascript
(response.propositions || []).forEach(p => {
  (p.items || []).forEach(item => {
    const contents = item.data?.content || [];
    contents.forEach(contentItem => {
      const html = contentItem.offerText || "";
      const wrapper = document.createElement("div");
      wrapper.className = "offer";
      wrapper.innerHTML = html;
      document.getElementById("offerContainer").appendChild(wrapper);
    });
  });
});
```

### サンプルアセット

開始するのに役立つように、サンプルのHTML ファイルとJavaScript ファイルをダウンロードします。これらのファイルでは、JSON ベースのオファーを使用し、web ページ上で動的にレンダリングする方法を示しています。

[JavaScript コード &#x200B;](assets/weather-related-offers-script-multiple-json.js)
[HTML ファイル &#x200B;](assets/multiple-json.html)