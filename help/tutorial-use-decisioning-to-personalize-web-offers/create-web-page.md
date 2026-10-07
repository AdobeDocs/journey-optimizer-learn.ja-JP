---
title: ソリューションをテストするWeb ページの作成
description: 決定を使用して配信されたパーソナライズされたオファーをテストするweb ページ。
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
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
source-wordcount: '223'
ht-degree: 0%
---
# 解決策をテストするためのweb ページの作成

このweb ページは、Adobe Journey Optimizer Decisioningを通じて配信されるパーソナライズされたオファーをテストするために作成されました。 sendEvent呼び出しをトリガーし、返されたオファーコンテンツをレンダリングできる制御された環境を提供し、エンドツーエンドのパーソナライゼーション設定を検証し、意思決定が期待どおりに機能することを確認するのに役立ちます。

次のスクリプトは、Adobe Journey Optimizerを使用してパーソナライズされたオファーを取得し、web ページに表示する役割を担っています。

1. HTML エンティティのデコード：

   オファーコンテンツ内の特殊文字を読み取り可能なHTMLに安全に変換するヘルパー機能があります。

1. パーソナライゼーションの実行：

   呼び出されると、ページ上の特定の領域（`#ajo-offer`要素）に対してパーソナライズされたコンテンツを取得するためのリクエスト（`sendEvent`）がAdobeのWeb SDKに送信されます。

   オファーが返されると、HTMLがデコードされ、ページに挿入されます。

   何も返されない場合は、警告がログに記録されます。

1. SDKを待ちます。

   AdobeのSDK（alloy）が非同期で読み込まれるため、スクリプトは完全に読み込まれるまで待ってからリクエストを行います。

   200 ミリ秒ごとに、最大20回まで合金をチェックし、エラーを回避します。

1. ページ読み込み時：

   ページの読み込みが完了すると、スクリプトは`waitForAlloy()`を呼び出してプロセスを開始します。



```javascript
< script >
    function decodeHtmlEntities(html) {
        const txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }


function runPersonalization() {
    console.log("🚀 Sending personalization request to AJO...");
    alloy("sendEvent", {
        renderDecisions: false,
        personalization: {
            surfaces: ["#ajo-offer"]
        }
    }).then(result => {
        console.log("🔍 Web SDK decision response:", result);

        const decision = result.propositions?.[0];
        const html = decision?.items?.[0]?.data?.content;

        const container = document.getElementById("ajo-offer");
        if (html && container) {
            const decodedHtml = decodeHtmlEntities(html);
            console.log("✅ Offer HTML content (decoded):", decodedHtml);
            container.innerHTML = decodedHtml;
        } else {
            console.warn("⚠️ No personalized offer returned.");
        }


    }).catch(error => {
        console.error("❌ sendEvent failed:", error);
    });
}

function waitForAlloy(callback, retries = 20) {
    if (typeof alloy === "function") {
        callback();
    } else if (retries > 0) {
        console.log("⌛ Waiting for Alloy...");
        setTimeout(() => waitForAlloy(callback, retries - 1), 200);
    } else {
        console.error("❌ alloy is not loaded after waiting.");
    }
}

// Trigger initial personalization on page load
document.addEventListener("DOMContentLoaded", function() {
    waitForAlloy(() => runPersonalization());
}); <
/script>
```

[サンプルのHTML ページと関連アセットは、こちらからダウンロードできます](assets/web-page-assets.zip)
