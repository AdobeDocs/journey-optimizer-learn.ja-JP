---
title: ランキング式の作成
description: Adobe Journey Optimizerのランキング式は、オファーの決定時に、特に適格なオファーの優先順位を決定するために選択戦略内で使用されます。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: eee1b86e-b33f-408e-9faf-90317bc5e861
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 19%
---
# ランキング式の作成

Adobe Journey Optimizerのランキング式は、オファーの決定時に、特に適格なオファーの優先順位を決定するために選択戦略内で使用されます。 ランキング式は、適格性フィルタリングの後に使用されます。これは、複数のオファーが特定のプロファイルに適格ですが、ビジネスロジックまたはプロファイルコンテキストに基づいて上位のオファー（または少数）のみを表示する必要がある場合です。

* Journey Optimizerにログインします

* 決定 – >戦略設定 – > ランキング式 – >数式の作成

ランキング式
![name_description](assets/formuala-ranking.png)

ランキング式の基準とは、オファーにスコアを割り当てるために使用される条件付きルールを指します。 これらの基準は、オファーの属性とプロファイルまたはコンテキストを比較し、特定の個人に対するオファーの関連性を判断します。



条件1

この条件では、決定項目（オファー）がフィルタリングされ、「IncomeLevel」タグが付けられたオファーのみが&#x200B;**含まれます。**
フィルターされたオファーは、定義した追加のロジックにもとづいて、ランキングや配信などの次のステップに進みます。
![criteria_one](assets/income-related-formula.png)


ランキングスコアを作成するには、次の式を使用します

```pql
if(   offer._techmarketingdemos.offerDetails.zipCode = _techmarketingdemos.zipCode,   _techmarketingdemos.annualIncome / 1000 + 10000,   if(     not offer._techmarketingdemos.offerDetails.zipCode,     _techmarketingdemos.annualIncome / 1000,     -9999   ) )
```

数式の機能

* オファーの郵便番号がユーザーと同じ場合は、最初に選択されるように非常に高いスコアを付けます。

* オファーに郵便番号がまったく含まれていない場合（一般的なオファーの場合）は、ユーザーの収入に基づいて通常のスコアを付けます。

* オファーの郵便番号がユーザーと異なる場合は、選択されないように非常に低いスコアを付けます。

このようにして、システム：

* 常に最初に郵便番号に一致するオファーを表示しようとします。

* 一致するオファーが見つからない場合は、一般的なオファーにフォールバックし、他の郵便番号を対象としたオファーを表示しないようにします。


オファー項目がフィルター条件のいずれも満たさない場合（「IncomeLevel」タグがないなど）、オファーはデフォルトのランキングスコアである10を受け取ります。




