---
title: 動的な決定とランキングをテストするオファーを作成します。
description: 決定のオファー項目は、メッセージ、画像、プロモーション、レコメンデーションなど、パーソナライズされたコンテンツの単一の部分を表し、定義されたルールと条件に基づいてユーザーに配信できます。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: ee940654-6c6c-42d2-8c33-e0b1dfa5c3ed
source-git-commit: 95a8abd08fbf57900870826112b01a8cd375fe96
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# 動的な決定とランキングをテストするオファーを作成

これらのオファーは、Adobe web SDK（alloy （&quot;sendEvent&quot;））を通じて渡される、リアルタイムのコンテキスト入力（気温など）に基づく動的な意思決定とランキングをテストするように設計されています。

オファーを作成する前に、オファー項目スキーマを拡張して新しいフィールド offerText を含めるようにしました。

![offer-schema](assets/offer-schema.png)。

次の 3 つのオファーを作成します


## Hot Weather Offer （Tag:hot）

hot weather オファー用のオファーテキスト

```html
<div data-tags="weather hot skincare sunscreen" style="border: 1px solid #e0e0e0; padding: 1.5rem; border-radius: 10px; background-color: #fff3e0;">   <h2 style="color: #e65100;">Protect Your Skin This Summer</h2>   <p>High temperatures mean high UV risk. Get <strong>20% off</strong> our dermatologist-recommended sunscreens and skin protection kits.</p>   <p>Offer valid this week only for areas with temperatures over 90°F.</p> <button  class="ajo-cta"> Shop Sunscreen</button>   </div>
```


## 穏やかな天気のオファー（Tag:spring）

穏やかな天候に対するオファーテキスト

```html
<div class="offer-content" style="text-align: center; padding: 1rem;">   <img     src="https://raw.githubusercontent.com/gbedekar489/gbedekar489.github.io/c857d12d92603daa50e9f707db0ba6ee87372eec/weather/spring.jpeg"     alt="Spring gardening scene"     style="width: 100%; max-width: 450px; border-radius: 12px; margin-bottom: 1rem;"   >   <h2>Grow More Than Just Flowers 🌿</h2>   <p>     Spring is here, and it's the perfect time to cultivate your garden — and your savings!     Enjoy <strong>$50 off</strong> when you spend $250 or more on gardening tools, seeds, and accessories.   </p>   <p><strong>Promo Code:</strong> <code>GROWSPRING</code></p>   <p><em>Offer valid through May 31. Let your garden — and your wallet — thrive.</em></p> <button  class="ajo-cta"> YES,I want this offer</button> </div>
```

## 寒冷提供（Tag:cold）

寒い天気オファー用のオファーテキスト

```html
<div class="offer-content" style="text-align: center; padding: 1rem;">   <img src="https://raw.githubusercontent.com/gbedekar489/gbedekar489.github.io/main/weather/pexels-romanp-16170.jpg"         alt="Winter clothing"         style="width: 100%; max-width: 400px; border-radius: 12px; margin-bottom: 1rem;">   <h2>Cold Weather, Hot Deals 🧤</h2>   <p>Stay warm in style with our exclusive <strong>25% off</strong> winter outerwear. From puffer jackets to wool scarves, find the perfect layers to beat the chill.</p>   <p><strong>Use code:</strong> <code>WINTER25</code> at checkout</p>   <p><em>Limited time offer. While supplies last.</em></p><button  class="ajo-cta"> Shop Sunscreen</button> </div>
```

### コレクションを作成

**_決定/カタログ/コレクション/コレクションを作成_** に移動します。
コレクションに **天候関連オファー** という名前を付ける

ルールビルダーを使用して、これらのオファーをこのコレクションにグループ化します。

