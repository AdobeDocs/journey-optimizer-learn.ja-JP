---
title: ランキング式を作成
description: Adobe Journey Optimizerのランキング式は、Offer Decisioning の実行中、特に選択戦略内で使用され、実施要件を満たすオファーの優先順を決定します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
exl-id: eee1b86e-b33f-408e-9faf-90317bc5e861
source-git-commit: 69868d1f303fa0c67530b3343a678a850a8e493b
workflow-type: tm+mt
source-wordcount: '325'
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

この条件では、「IncomeLevel」がタグ付けされたオファーを決定項目 **オファー）** 含めるのみ）をフィルタリングします。
これらのフィルタリングされたオファーは、定義した追加ロジックに基づいて、次のステップ（ランキングや配信など）に進みます。
![criteria_one](assets/income-related-formula.png)


次の式を使用して、ランキングスコアを作成します

```pql
if(   offer._techmarketingdemos.offerDetails.zipCode = _techmarketingdemos.zipCode,   _techmarketingdemos.annualIncome / 1000 + 10000,   if(     not offer._techmarketingdemos.offerDetails.zipCode,     _techmarketingdemos.annualIncome / 1000,     -9999   ) )
```

数式の機能

* オファーの郵便番号がユーザーと同じ場合は、非常に高いスコアを付けて、最初に選択されるようにします。

* オファーに郵便番号がまったく含まれていない場合（一般的なオファーの場合）、ユーザーの収入に基づいて通常のスコアを付けます。

* オファーの郵便番号がユーザーと異なる場合は、スコアを非常に低く設定し、選択されないようにします。

このように、システムは次のことを行います。

* は常に、最初に ZIP 一致のオファーを表示しようとします。

* 一致するオファーが見つからない場合は一般的なオファーにフォールバックし、他の郵便番号を対象としたオファーを表示するのを回避します。


オファー項目がどのフィルター条件も満たさない場合（「IncomeLevel」タグがない場合など）、オファーはデフォルトのランキングスコア 10 を受け取ります。




