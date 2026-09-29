---
title: Web フォームの作成
description: HTMLのページで、投資の環境設定を選択できるフォームを作成します
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 20de8dec-aac8-43ed-8305-e723f82a5dd9
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%
---
# Web フォームの作成

次のHTML フォームは、ユーザー設定をキャプチャするために作成されました
![html-form](assets/web-form.png)

オーディエンスがweb ページのボタンをクリックすると、選択した財務情報（在庫、債券、CDなど）が取り込まれ、Adobeデータレイヤーにプッシュされます。 このイベント（assetClassSelection）は、ユーザーの選択をリアルタイムで保存します。 Adobe Launchは、このイベントをリッスンし、選択した投資オプション（PreferredFinancialInstrument）を取得します。また、データをAdobe Experience Platform（AEP）に送信したり、パーソナライゼーションルールを更新したりするなど、アクションをトリガーできます

次のJavaScriptは、フォームの送信を処理するために作成されました

```javascript
function handleSubmission() {
  window.adobeDataLayer = window.adobeDataLayer || [];

  const selectedAssetClass = document.querySelector('input[name="assetclass"]:checked');
  const errorMessage = document.getElementById("error-message");
  const messageBox = document.getElementById("message");

  if (!selectedAssetClass) {
    errorMessage.textContent = "Please select a financial instrument.";
    messageBox.textContent = "";
    return;
  }

  errorMessage.textContent = "";

  const subscriptionEvent = {
    event: "assetClassSelection",
    xdm: {
      eventType: "assetClassSelection",
      eventID: "investment_preference_event",
      timestamp: new Date().toISOString(),
      FinancialInterest: {
        PreferredFinancialInstrument: selectedAssetClass.value
      }
    }
  };

  console.log("📩 Sending asset class data to AEP:", subscriptionEvent);
  window.adobeDataLayer.push(subscriptionEvent);

  // ✅ Show thank-you message
  messageBox.textContent = `Thank you for selecting "${selectedAssetClass.value}". We'll use this to personalize your experience.`;
}
```

[HTML フォームのサンプルは、このチュートリアルの一部として提供されています](assets/webform.zip)
