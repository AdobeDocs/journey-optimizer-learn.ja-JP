---
title: ログインアクティビティを模倣するためのサンプルアプリケーションの構築
description: ログインフローをシミュレートするためのサンプル Node.js アプリケーションの構築
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: e080149c-0ac0-4559-b99d-ebad9f03b98b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%
---
# ログインアクティビティを模倣するためのサンプルアプリケーションの構築

Node.js サーバーに構築およびデプロイされたこのサンプルアプリケーションは、ユーザーがログインしたときにCRM IDをAdobe Experience Platform（AEP）に送信する方法を示しています。 このアプリケーションは、ユーザーの資格情報がサーバー側で検証されるログインフローをシミュレートします。 ログインが成功すると、ユーザーのCRM IDが取得され、adobeDataLayerにプッシュされ、Adobe Experience Platform Tags （旧Adobe Launch）で対応するルールがトリガーされます。

attachLoginHandler関数は、送信イベントリスナーをログインフォームに添付します。 フォーム送信時に、デフォルトのアクションを防ぎ、事前定義されたユーザーのオブジェクトに対して資格情報を検証し、有効な場合はCRM IDを取得します。 この関数は、CRM IDと認証状態を持つuserloggedin イベントをadobeDataLayerにプッシュし、Adobe Experience Platform TagsはそれをピックアップしてデータをAdobe Experience Platform（AEP）に送信します。


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
                event: "UserLoggedIn",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

Adobe Experience Platform タグスクリプトは、`<script>` タグを使用してHTML ページの`<head>` セクションに含まれます。通常は次のようになります。

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

AEP Tags スクリプトは、前の手順で作成したWeb SDK対応プロパティを公開し、「環境」タブから埋め込みコードをコピーすることによって取得されました。
