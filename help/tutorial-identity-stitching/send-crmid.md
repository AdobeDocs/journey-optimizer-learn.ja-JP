---
title: ログインアクティビティを模倣するサンプルアプリケーションの構築
description: ログインフローをシミュレートするためのサンプル Node.js アプリケーションを作成します
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: e080149c-0ac0-4559-b99d-ebad9f03b98b
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# ログインアクティビティを模倣するサンプルアプリケーションの構築

このサンプルアプリケーションは、Node.js サーバーで構築およびデプロイされ、ユーザーがログインしたときに CRM ID をAdobe Experience Platform（AEP）に送信する方法を示します。 アプリケーションは、ユーザー資格情報がサーバーサイドで検証されるログインフローをシミュレートします。 ログインに成功すると、ユーザーの CRM ID が取得されて adobeDataLayer にプッシュされ、Adobe Experience Platform タグ（旧称：Adobe Launch）で対応するルールがトリガーされます。

attachLoginHandler 関数は、送信イベントリスナーをログインフォームにアタッチします。 フォームの送信時には、デフォルトのアクションを回避し、事前定義済みのユーザーのオブジェクトに対して資格情報を検証し、有効な場合は CRM ID を取得します。 この関数は、CRM ID および認証状態を持つ userloggedin イベントを adobeDataLayer にプッシュし、Adobe Experience Platform タグが取得してデータをAdobe Experience Platform（AEP）に送信します。


```javascript
function attachLoginHandler() {
    const form = document.getElementById("loginForm");
    if (!form) return;

    form.addEventListener("submit", function(e) {
        e.preventDefault();
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;

        if (users[username] && users[username].password === password) {
            const crmid = users[username].crmid;
            window.adobeDataLayer = window.adobeDataLayer || [];
            debugger;
            window.adobeDataLayer.push({
                event: "userloggedin",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

Adobe Experience Platform タグスクリプトは、通常は次のように、`<script>` タグを使用してHTML ページの `<head>` セクションに含まれます。

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

AEP タグスクリプトは、前の手順で作成した web SDK対応のプロパティを公開し、「環境」タブから埋め込みコードをコピーすることで取得されました。
