---
title: Web フォームの作成
description: HTMLのページで、投資の環境設定を選択できるフォームを作成します
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 20de8dec-aac8-43ed-8305-e723f82a5dd9
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
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
