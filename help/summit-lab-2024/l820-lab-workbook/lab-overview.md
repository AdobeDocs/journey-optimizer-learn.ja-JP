---
title: Lab Workbook - L820 - Adobe Journey Optimizerでパーソナライズされたモバイルモーメントを構築
description: さまざまなモバイルシナリオについて説明し、Journey Optimizerを使用して、webとモバイルにパーソナライズされたエクスペリエンスを実装する方法を紹介します。
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00.000Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
    internal-label: Administration
subfeature_v2:
  - id: fdac7813-bd56-47ae-9f6d-fa94ad1c5dee
    internal-label: Overview
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%
---
# ラボワークブック

![Adobe Summit - alt text](/help/summit-lab-2024/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820 - Adobe Journey Optimizerでパーソナライズされたモバイルモーメントを構築する

このラボでは、Journey Optimizerを利用して、さまざまなモバイルシナリオを検証し、webとモバイルにパーソナライズされたエクスペリエンスを実装する方法を学ぶことができます。


>[!IMPORTANT]
>
>セッションの写真やスクリーンショットをソーシャルメディアに投稿することは控えてください。
><br>
>**Adobeの機密性**
>このラボで共有された情報と製品の開示は、Adobeの機密情報です。
>参加者は、いかなる個人または団体に対しても、機密情報を複製、使用、配布、または開示することはできません。
>製品の開示は情報提供のみを目的としており、将来の機能を保証するものではなく、いつでも変更される可能性があります。 そのため、そのような製品の機能は、Adobeとの契約の一部ではなく、その他の方法でお客様に約束されるものではありません。
><br>
>**免責事項**
>Adobeでは、生成AI テクノロジーを活用したこれらの機能に早期にアクセスできます。 これらの機能はまだ開発中であり、予期せぬ、または不正確な応答が生成される可能性があることに注意してください。 この機能を市場に投入する際のフィードバックを歓迎します。


### 重要な留意点

* サポートされている様々なモバイルエクスペリエンスを把握します。
* プッシュキャンペーンの設定。
* モバイルのアプリ内キャンペーンを設定する方法について説明します。
* web アプリ内メッセージを設定します。
* パーソナライズされた独自のシナリオをテスト。

### 前提条件

* 座席番号を知る：ラボマシンのデスクトップで座席番号を確認できます。

![席番号](/help/summit-lab-2024/l820-lab-workbook/assets/locate-seat-number.png)
次のアクセス権が必要です：

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} - ログインの詳細は、練習中に提供されます。
* [&#x200B; フレスコパ web サイト &#x200B;](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### ユースケースを理解する

ダイナミックで革新的な企業であるFréscopaは、独自のコーヒー購読サービスと、web サイトやモバイルアプリで利用できる多様なコーヒー関連製品の融合により、コーヒー体験の変革を推進しています。 優れた品質と風味を提供するという取り組みにより、フレスコパは利便性とプレミアムオプションを求めるコーヒー愛好家に対応しています。

Fréscopaのビジネスの中心は、コーヒーのサブスクリプションサービスにあり、お客様の目の前に届けられる高品質な豆の厳選されたセレクションを提供しています。 このパーソナライズされたアプローチにより、コーヒー愛好家は、自分の好みに合わせた新鮮で楽しい体験を楽しむことができます。

サブスクリプションサービスを補完するFréscopaのweb サイトとモバイルアプリは、コーヒー関連の包括的な商品を提供しており、顧客はコーヒーの儀式を探求し、強化することができます。 醸造設備から職人のアクセサリーまで、フレスコパは品質と利便性を求めるコーヒー愛好家のためのワンストップショップを提供しています。

Fréscopaの優れた取り組みは、製品の枠を超えて、シームレスで楽しいカスタマージャーニーの構築に取り組んでいます。 革新的なテクノロジーと顧客中心のアプローチを組み合わせることで、進化するコーヒー業界の最前線に立つことができます。 本質的に、フレスコパは情熱と技術の融合を体現し、個人がコーヒーを体験し、楽しむ方法を再定義しています。 品質、利便性、パーソナライズされたサービスに重点を置き、Fréscopaはコーヒー愛好家を招いてフレーバーの旅に出かけ、その先に届けます。

