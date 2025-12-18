---
title: ラボワークブック - L820 - Adobe Journey Optimizerでパーソナライズされたモバイルモーメントの作成
description: 様々なモバイルシナリオを解説し、Journey Optimizerを使用して web とモバイル向けにパーソナライズされたエクスペリエンスを実装する方法を説明します。
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# ラボワークブック

![Adobe Summit – 代替テキスト ](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820 - Adobe Journey Optimizerでパーソナライズされたモバイルモーメントの作成

この実践ラボでは、様々なモバイルシナリオを探索し、Journey Optimizerを使用して web とモバイル向けにパーソナライズされたエクスペリエンスを実装する方法を学びます。


>[!IMPORTANT]
>
>セッション中の写真やスクリーンショットをソーシャルメディアに投稿することは差し控えてください。
><br>
>**Adobeの機密性**
>このラボで本日共有された情報および商品の開示は、Adobeの機密情報です。
>参加者は、いかなる個人または団体に対しても、機密情報を複製、使用、流布、または開示することはできません。
>製品の開示は情報提供のみを目的としており、将来の機能を保証するものではなく、いつでも変更される可能性があります。 そのため、このような製品の機能は、Adobeとの契約には含まれず、その他の方法でお客様に提供されることはありません。
><br>
>**免責事項**
>Adobeでは、ジェネレーティブ AI テクノロジーを活用した機能への早期アクセスを提供しています。 これらの機能は開発中であり、予期しない応答や不正確な応答が生じる場合があることに注意してください。 この機能を市場に投入する際には、フィードバックをお待ちしています。


### 重要ポイント

* サポートされる様々なモバイルエクスペリエンスについて説明します。
* プッシュキャンペーンを設定します。
* モバイルのアプリ内キャンペーンを設定する方法を説明します。
* Web アプリ内メッセージを設定します。
* 独自にパーソナライズしたシナリオをテストします。

### 前提条件

* シート番号の確認：シート番号は、ラボマシンのデスクトップに表示されます。

![ シート番号 ](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/locate-seat-number.png)
次へのアクセス権が必要です。

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} - ログインの詳細は演習中に提供されます。
* [Fréscopa web サイト ](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### ユースケースについて

動的で革新的な企業である Fréscopa は、独自のコーヒーサブスクリプションサービスと、Web サイトやモバイルアプリで利用できる多様なコーヒー関連製品を組み合わせることで、コーヒーエクスペリエンスに革命をもたらすことを専門としています。 Fréscopa は、優れた品質と風味を提供することを約束し、利便性とプレミアムなオプションを求めるコーヒー愛好家に対応しています。

Fréscopa のビジネスの中心は、コーヒーのサブスクリプションサービスにあり、厳選された高品質の豆を玄関先で提供します。 このパーソナライズされたアプローチにより、コーヒー愛好家は、自分の好みに合わせた新鮮で楽しいエクスペリエンスを楽しむことができます。

Fréscopa のウェブサイトとモバイルアプリは、そのサブスクリプションサービスを補完し、コーヒー関連の製品の包括的な範囲を提供し、お客様がコーヒーの儀式を探索し、強化することができます。 醸造設備から職人のアクセサリーまで、Fréscopa は品質と利便性を求めるコーヒー愛好家のためのワンストップショップを提供しています。

Fréscopa は、シームレスで楽しいカスタマージャーニーの構築に取り組んでいるため、製品にとどまらず、エクセレンスへの取り組みを強化しています。 革新的なテクノロジーと顧客中心のアプローチの組み合わせにより、Fréscopa は進化するコーヒー業界の最前線に立っています。 本質的に、Fréscopa は情熱と技術の融合を体現し、個人がコーヒーを体験し、楽しむ方法を再定義します。 品質、利便性、パーソナライズされたサービスに重点を置いて、Fréscopa はコーヒー愛好家に、彼らの玄関先に届けられる味の旅に乗り出すよう誘います。
