---
title: 決定ポリシーの作成
description: 決定ポリシーを使用して、パーソナライゼーション中にどのオファーがユーザーに配信されるかを決定するロジックを定義します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 6%

---

# 決定ポリシーの作成

決定ポリシーは、オーディエンスに応じて配信する最適なコンテンツを選択するために、[!UICONTROL &#x200B; 決定 &#x200B;] エンジンを活用するオファーのコンテナです。

1. パーソナライゼーションエディターで、左側のナビゲーションにある **[!UICONTROL 決定ポリシー]** 項目をクリックしてから、**[!UICONTROL 決定ポリシーを追加]** をクリックします。

   ![create-decision-policy](assets/decision-policy.png)

1. 「**[!UICONTROL 追加]**」をクリックして、選択方法を選択します。

   ![ 決定ポリシー ](assets/decision-policy2.png)

1. **[!UICONTROL フォールバックを選択]** をクリックして、フォールバックオファーを選択します。
1. 「**[!UICONTROL 次へ]**」をクリックして、決定ポリシーを確認します。
1. 「**[!UICONTROL 作成]**」をクリックして、決定ポリシーの作成プロセスを完了します。

## コードエディターでの決定ポリシーの使用

1. パーソナライゼーションエディターで、「**[!UICONTROL ポリシーを挿入]**」をクリックします。

   決定ポリシーに対応するコードが追加されます。

   この段階では、必要な決定属性をコード内に直接含めることができます。 これらの属性は、オファーカタログで使用されるスキーマで定義されます。 標準属性は `__experience` 名前空間の下に整理され、組織に固有のカスタム属性は `_<imsOrg>` 名前空間の下に保存されます。

   ![using_decision_policy](assets/Insert-policy.png)

   このコードは、ユーザーに選択されたパーソナライズされたオファーのリストを処理し、web ページに各オファーのテキストを表示します。 段落内の各オファーからのメッセージ（`offerText` と呼ばれます）が表示されるので、ユーザーはカスタマイズされたコンテンツを明確に確認できます。

   パーソナライズされたオファーがない場合は、スペースが空白にならないようにフォールバックオファーが表示されます。

1. 「**[!UICONTROL 保存]**」をクリックして、キャンペーンをアクティブ化します。
