---
title: L535 チートシート
description: このページには、L535 サミットラボで使用されているテキストとリンクが含まれています。
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: c1a77892652df0a91a6add1ad0dc5a4bd0770d8b
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 29%

---

# Summit Lab L535 - チートシート

このページには、L535 サミットラボで使用されているテキストとリンクが含まれています。 これらを使用して、コンテンツをコピーし、Journey Optimizerメッセージに貼り付けることができます。

## リンク

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys)
* [SecurFinancial Web サイト ](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U)
* [ アプリのダウンロード ](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html)

## 演習用にコピー&amp;ペースト

### 演習 2.3 - メールメッセージの作成

#### プロンプト

```
Generate a welcome email for new SecurFinancial customers who just opened a new savings account. 
Add a call to action to install the SecurFinancial mobile app.
```

### 演習 3.1 - SMS メッセージへの動的コンテンツの適用

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

### 演習 4.2 – 処理の設定

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

### 演習 6 - コンテンツカード

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
https://demo-systemnext.s3.amazonaws.com/assets/securfinancial/homeloan.jpg
```

#### ボタンタイトル

```
Find ATMs
```

#### ターゲット URL

```
dxdemo://atm
```

## 画像

![SecureFinancial ロゴ ](/help/summit-lab-assets/assets/SecureFinancial-logo.png)


![ 携帯電話 ](/help/summit-lab-assets/assets/online-banking-app-01.png)


