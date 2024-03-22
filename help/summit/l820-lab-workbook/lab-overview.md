---
title: Lab ワークブック — L820 - Adobe Journey Optimizerでパーソナライズされたモバイルモーメントを構築
description: 様々なモバイルシナリオを調べ、Journey Optimizerで Web およびモバイル用にパーソナライズされたエクスペリエンスを実装する方法を学びます。
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14977
thumbnail: KT-14977.jpeg
source-git-commit: d53c2218ee69c81881b12dedc435826034a710e3
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---


# LAB ワークブック

![Adobe Summit — 代替テキスト](/help/summit/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

>[!IMPORTANT]
>
>セッションからソーシャルメディアに写真やスクリーンショットを投稿するのはお控えください。
>
>**Adobeの機密性**
>本研究室で今日共有されている情報と製品開示は、Adobeの機密情報です。
>参加者は、個人または団体に対し、秘密情報を複製、使用、普及、開示することはできません。
>製品の開示は、情報提供のみを目的とし、将来の機能を保証するものではなく、いつでも変更される可能性があります。 したがって、このような製品の機能は、Adobeとの間での契約の一部ではなく、あるいは何らかの方法でお客様に約束されたものでもありません。
>
>**免責事項**
>Adobeは、生成 AI テクノロジーを利用した機能への早期アクセスを提供します。 これらの機能はまだ開発中で、予期しない、または不正確な応答が発生する可能性があることに注意してください。 この機能を市場に投入する際に、皆様のご意見をお待ちしております。

## L820 - Adobe Journey Optimizerでパーソナライズされたモバイルモーメントを構築

この実践ラボでは、様々なモバイルシナリオを参照し、Journey Optimizerで Web およびモバイル用にパーソナライズされたエクスペリエンスを実装する方法を学びます。

### 重要ポイント

* サポートされる様々なモバイルエクスペリエンスを理解します。
* プッシュキャンペーンを設定します。
* モバイルアプリ内キャンペーンの設定方法を説明します。
* Web アプリ内メッセージを設定します。
* パーソナライズされた独自のシナリオをテストします。

### 前提条件

* 座席番号を知る：ラボマシンのデスクトップで、座席番号を確認できます。

![座席番号](/help/summit/l820-lab-workbook/assets/locate-seat-number.png)
次へのアクセス権が必要です：

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}   — 練習中にログインの詳細が表示されます。
* [Fréscopa の Web サイト](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### 使用例を理解する

ダイナミックで革新的な企業である Fréscopa は、独自のコーヒーサブスクリプションサービスと、そのウェブサイトやモバイルアプリで利用可能な様々なコーヒー関連製品を組み合わせ、コーヒー体験を革新する専門会社です。 Fréscopa は、優れた品質と風味を提供する取り組みを持ち、利便性とプレミアムオプションを求めるコーヒー愛好者に対して対応しています。

Fréscopa のビジネスの中心は、コーヒーのサブスクリプションサービスにあり、お客様に厳選された高品質の豆を提供しています。 このパーソナライズされたアプローチは、コーヒー愛好者の好みに合わせた新鮮で楽しい体験を楽しむことができます。

Fréscopa のウェブサイトとモバイルアプリは、サブスクリプションサービスを補完し、コーヒー関連の製品の包括的な範囲を提供し、顧客がコーヒーの儀式を探索し、強化することができます。 醸造設備から職人用アクセサリーまで、フレスコパは品質と利便性を追求したコーヒー愛好家向けのワンストップショップを提供しています。

Fréscopa の卓越性に対する取り組みは、シームレスで楽しいカスタマージャーニーの構築に尽力しているため、製品を超えて拡大しています。 革新的な技術と顧客中心のアプローチの組み合わせにより、Fréscopa は進化するコーヒー業界の最前線に位置しています。 要するに、Fréscopa は情熱と技術の融合を体現し、個人の経験やコーヒーの楽しみ方を再定義します。 品質、利便性、パーソナライズされたサービスに焦点を当てた Fréscopa は、コーヒー愛好家を招き、彼らの目の前に届く、味の旅に着手する。



