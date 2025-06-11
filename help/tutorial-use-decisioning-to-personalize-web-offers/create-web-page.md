---
title: ソリューションをテストする Web ページの作成
description: 意思決定を使用して配信されたパーソナライズされたオファーをテストする Web ページ。
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
source-git-commit: 13c891c02a9a2da3ff742afaab7ceb449a417b5e
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# ソリューションをテストする web ページを作成

この web ページは、Adobe Journey Optimizer Decisioning を通じて配信された、パーソナライズされたオファーをテストするために作成されました。 これは、sendEvent 呼び出しをトリガーし、返されるオファーコンテンツをレンダリングできる制御された環境を提供し、エンドツーエンドのパーソナライゼーション設定の検証を支援し、意思決定が期待どおりに動作することを確認するのに役立ちます。

次のスクリプトは、Adobe Journey Optimizerを使用して、web ページ上でパーソナライズされたオファーを取得し、表示します。

1. HTML エンティティをデコードします。

   オファーコンテンツ内の特殊文字を読み取り可能なHTMLに安全に変換するヘルパー関数があります。

1. 実行パーソナライゼーション：

   呼び出されると、Adobeの Web SDKにリクエスト（`sendEvent`）が送信され、ページの特定の領域（`#ajo-offer` 要素）に対応するパーソナライズされたコンテンツが取得されます。

   オファーが返された場合、そのオファーはHTMLをデコードしてページに挿入します。

   何も返されない場合、警告をログに記録します。

1. SDKを待ちます。

   AdobeのSDK（alloy）は非同期で読み込むので、スクリプトは完全に読み込まれるまで待ってからリクエストを実行します。

   エラーを回避するために、200 ミリ秒ごとに最大 20 回 Alloy をチェックします。

1. ページの読み込み時：

   ページの読み込みが完了すると、スクリプトは `waitForAlloy()` を呼び出してプロセスを開始します。



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

[サンプルのHTML ページと関連アセットは、こちらからダウンロードできます。](assets/web-page-assets.zip)
