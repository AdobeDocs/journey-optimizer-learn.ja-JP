---
title: 郵便番号をターゲットにした場所ベースのオファーの作成
description: 決定のオファー項目は、メッセージ、画像、プロモーション、レコメンデーションなど、パーソナライズされたコンテンツの単一の部分を表し、定義されたルールと条件に基づいてユーザーに配信できます。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---


# 郵便番号をターゲットにした場所ベースのオファーの作成

オファーを作成する前に、オファー項目スキーマを拡張して新しいフィールド zipcode を含めるようにしました。 このカスタムフィールドを使用すると、各オファーをターゲットの郵便番号で明示的にタグ付けし、意思決定時に場所ベースのフィルタリングとランキングを行うことができます。

スキーマが更新され、2 つのパーソナライズされたオファーが作成されました。

* オファー 1:「Mira Mesa （92126）向け柔軟な投資計画」
92126 内の若いプロフェッショナルやテクノロジーを重視する居住者に合わせた内容で、ETF や長期的な成長を目指した投資信託など、柔軟な投資オプションを促進します。 「郵便番号」フィールドは「92126」に設定されます。

* オファー 2:「ランチョ・ベルナルド用の高収量 CD （92128）」
92128 内の財政的に安定した退職後に備えた個人を対象に、このオファーは、リターンが保証された高利回りの預金証書（CD）を特徴としています。 「郵便番号」フィールドは「92128」に設定されます。

これらのオファーは、場所メタデータでエンリッチメントされ、後の手順でユーザープロファイルの郵便番号に基づいて動的に選択およびランク付けできるようになりました。

次のスクリーンショットは、オファー項目スキーマに追加されたカスタム属性を示しています。

![offers-meta-data](assets/offers-meta-data.png)


## 92126 に対するオファー

郵便番号のオファーのオファーテキス 92126

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #f9f9f9; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Boost Your Financial Game with Smart Investment Options   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     In Mira Mesa (92126), ambition meets opportunity. Whether you're building wealth or just getting started, our     <strong>diversified investment plans</strong> — including <strong>tech-focused ETFs</strong> and     <strong>flexible mutual funds</strong> — are designed to grow with your goals.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Enjoy expert guidance, low fees, and strategies built for busy professionals who want more from their money — without the hassle.   </p>   <a href="#start-investing" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Start Investing Smarter   </a> </div>
```


## 92128 に対するオファー

郵便番号のオファーのオファーテキス 92128

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #fdfdfd; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Grow Your Savings with Confidence – Exclusive CD Rates for 92128   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Live in Rancho Bernardo? Take advantage of your financial momentum with our <strong>high-yield Certificates of Deposit</strong>, offering up to <strong>5.25% APY</strong>.     Designed for peace of mind and smart growth, our flexible CD options let you lock in guaranteed returns while enjoying the stability you deserve.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Whether you're planning retirement or simply securing your future, this offer is tailored for residents like you.   </p>   <a href="#explore-cd-options" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Explore CD Options   </a> </div>
```

## 汎用オファー（フォールバックオファー）

汎用オファーのオファーテキスト（郵便番号が関連付けられていない）

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #ffffff; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">
  <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">
    Invest Smarter: Build Wealth with Flexible Financial Plans
  </h2>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Looking to take control of your financial future? Our flexible investment solutions are designed to meet a wide range of goals — from growing savings to planning for retirement.
    Choose from diversified mutual funds, ETFs, and professionally managed portfolios, all with expert guidance and minimal hassle.
  </p>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Whether just starting out or optimizing an existing strategy, this offer provides the tools to invest with confidence — no matter where you live.
  </p>
  <a href="#explore-investment-plans" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
    Explore Investment Plans
  </a>
</div>
```

これらのオファーを **_GenericOffers_** というコレクションにグループ化します

オファーはすべての訪問者が使用できます。つまり、厳密な実施要件制約はないので、ランキング式は、プロファイルコンテキストに基づいてどのオファーを表示するかを決定する上で重要になります。
実施要件ルールはオファーをフィルタリングしないので、3 つとも候補として扱われます。
選択方法は、3 つすべてを取得します。
ランキング式では、プロファイル属性（郵便番号、annualIncome など）に基づいてスコアを付け、最適な属性を選択します。



