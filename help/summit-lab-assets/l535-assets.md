---
title: L535 チートシート
description: このページには、L535 Summit Labで使用されているテキストとリンクがあります。
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: 3917e11cdf8c0450c19ce653a0964f6dc9da6a3c
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 16%

---

# Summit Lab L535- チートシート

このページには、L535 Summit Labで使用されているテキストとリンクがあります。 これらを使用して、コンテンツをコピーし、Journey Optimizerメッセージに貼り付けることができます。

## リンク

* [SecurFinancial Web サイト](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U){target="_blank"}
* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys){target="_blank"}
* [L535 Workbook](/help/summit-lab-assets/assets/summit_lab_manual_l535-final-v4.pdf){target="_blank"}
* [アプリをダウンロード](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html){target="_blank"}

## 演習のコピー&amp;ペースト

### 演習2.1 - Journey Optimizerへのログイン

次の詳細を使用してログインします。

電子メールアドレス：    L535+*座席番号*@adobeeventlab.com

パスワード：       Adobe4Summit!


### 演習2.3 - メールメッセージの作成

#### プロンプト

```
Generate a welcome email for new SecurFinancial customers who just opened a new checking account. 
Add a call to action to install the SecurFinancial mobile app.
```

### 演習3.1 - SMS メッセージに動的コンテンツを適用する

#### コード

```
{%#if select _Push_details1 from profile.pushNotificationDetails where
_Push_details1.token.isNotNull()%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Open the
app
{%else%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Click here
to install the app: https://demo-systemnext.
s3.amazonaws.com/dxdemo/summit/index.html
{%/if%} 
```

### 演習4.2 – 処理の設定

#### タイトル

```
Welcome to SecurFinancial
```

#### 本文

```
Did you know you can find an ATM near in the SecurFinancial app? Try it now!
```

#### URL

```
dxdemo://atm
```

### 演習6 - コンテンツカード

#### タイトル

```
Welcome to SecurFinancial!
```

#### 本文

```
Thank you for downloading the app. You can find ATMs, track your spending and more. All within the app.
```

#### メディア URL

```
https://demo-system-next.s3.amazonaws.com/assets/securfinancial/home-loan.jpg
```

#### ボタンのタイトル

```
Find ATMs
```

#### ターゲット URL

```
dxdemo://atm
```

## 画像

![SecureFinancial ロゴ ](/help/summit-lab-assets/assets/SecureFinancial-logo.png)


![携帯電話](/help/summit-lab-assets/assets/online-banking-app-01.png)
