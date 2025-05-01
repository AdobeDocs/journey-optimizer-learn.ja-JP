---
title: Web フォームの作成
description: HTMLページで投資環境設定を選択できるフォームを作成します
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Web フォームの作成

次のHTML フォームは、ユーザーの環境設定を取り込むために作成されました
![html-form](assets/web-form.png)

ユーザーが web ページのボタンをクリックすると、選択した金融環境設定（株式、債券、CD など）がキャプチャされ、Adobe Data Layer にプッシュされます。 このイベント（assetClassSelection）は、ユーザーの選択をリアルタイムで保存します。 次に、Adobe Launch はこのイベントをリッスンし、選択した投資オプション（PreferredFinancialInstrument）を取得し、データをAdobe Experience Platform（AEP）に送信したり、パーソナライゼーションルールを更新したりといったトリガーアクションを実行できます

フォームの送信を処理するために、次のJavaScriptが作成されました

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

[サンプルのHTML フォームは、このチュートリアルの一部として提供されています](assets/webform.zip)
