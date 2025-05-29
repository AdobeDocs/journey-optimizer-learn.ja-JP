---
title: ランキング式を作成
description: Adobe Journey Optimizerのランキング式は、Offer Decisioning の実行中、特に選択戦略内で使用され、実施要件を満たすオファーの優先順を決定します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---


# ランキング式を作成

Adobe Journey Optimizerのランキング式は、Offer Decisioning の実行中、特に選択戦略内で使用され、実施要件を満たすオファーの優先順を決定します。 ランキング式は、実施要件フィルタリングの後に、特定のプロファイルに対して複数のオファーが適合するが、ビジネスロジックまたはプロファイルコンテキストに基づいて上位 1 つ（または少数）のみを提示する必要がある場合に有効になります。

* Journey Optimizerにログインします

* 決定/戦略の設定/ランキング式/式を作成

ランキング式
![name_description](assets/formuala-ranking.png)

ランキング式の条件とは、オファーにスコアを割り当てるために使用される条件付きルールを指します。 これらの条件では、オファーの属性とプロファイルまたはコンテキストを比較して、特定の個人に対するオファーの関連度を判断します。



条件 1
![criteria_one](assets/criteria1.png)

条件 1 には、次の 3 つの条件があります。

* オファー。_techmarketingdemos.offerDetails.zipCode == &quot;92128&quot; - オファーに関連付けられている郵便番号を確認します。

* _techmarketingdemos.zipCode == &quot;92128&quot; - ユーザーのプロファイルの郵便番号を確認します。

* _techmarketingdemos.annualIncome > 100000 - ユーザーのプロファイルから収入レベルをチェックします。

これらの条件がすべて満たされた場合、オファーのスコアは 40 になります。






条件 2
![criteria_two](assets/criteria2.png)

条件 2 には、次の 3 つの条件があります。

* オファー。_techmarketingdemos.offerDetails.zipCode == &quot;92126&quot; - オファーに関連付けられている郵便番号を確認します。

* _techmarketingdemos.zipCode == &quot;92126&quot; - ユーザーのプロファイルの郵便番号を確認します。

* _techmarketingdemos.annualIncome &lt; 100000 - ユーザーのプロファイルから収入レベルをチェックします。

これらの条件がすべて満たされた場合、オファーのスコアは 30 になります。




