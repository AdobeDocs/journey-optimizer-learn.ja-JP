---
title: インプレッションとインタラクションイベントのキャプチャ
description: インプレッションやインタラクションイベントを取得し、Journey Optimizerでレポート用のデータを準備できます。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00.000Z
jira: KT-18526
exl-id: 7e6014b5-c5a6-467b-8e31-58c5d966464c
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
source-wordcount: '472'
ht-degree: 12%
---
# インプレッションとインタラクションイベントのキャプチャ

AJO decisioningからオファーのインプレッション数とクリック数に関するレポートを有効にするには、次のコンポーネントを設定する必要があります。
>[!NOTE]
>
> これらの前提条件は、以前の[&#x200B; チュートリアル &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset)の「スキーマとデータセットを作成」セクションで既に完了していました

## &#x200B;1. Adobe Experience Platformのデータセット（AEP）

- **XDM ExperienceEvent** スキーマに基づくデータセット。

スキーマには、ページ URL、リファラーなどを取得する`Web Details` フィールドグループが含まれている必要があります。

## &#x200B;2. データストリーム設定

- **データストリーム**&#x200B;をAdobe Experience Platformに作成する必要があります。
- すべてのWeb SDK イベントが適切な宛先に正しく取り込まれるようにするには、このデータストリームを上記で設定したデータセットにリンクする必要があります。

## &#x200B;3. Adobe Experience Platform Tags プロパティ

- AEP Web SDK拡張機能は、前の手順で作成したデータストリームを使用するように設定されています。
- Experience Cloud ID サービスが設定されました
- ECIDというデータ要素がプロパティに追加されます
- オファーがレンダリングされるサイトに実装されます。


オファーのパフォーマンスに関するレポートを有効にするには、最初の手順は、オファーが表示された時点（インプレッション）とクリックされた時点（インタラクション）をキャプチャすることです。 これらのイベントは、エンゲージメントの測定、クリックスルー率の計算、Adobe Experience Platform内でのオファーの効果の分析のための基盤を提供します。

alloy （&quot;sendEvent&quot;）関数は、Adobe Journey Optimizer （AJO）によって返されるオファーを使用してユーザーのインタラクションを記録するために使用されます。

sendEvent ペイロードは、イベントタイプ（インプレッションの場合はdecisioning.propositionDisplay、クリックの場合はdecisioning.propositionInteract）、一意のイベント ID、タイムスタンプ、ユーザーID （identityMap）を含めることで、オファーのインタラクションをキャプチャします。 また、表示またはクリックされたオファー（提案）のリスト、トラッキングトークンも含まれており、正確なアトリビューションを実現します。 この構造により、Adobe Journey Optimizerでのパーソナライズされたオファーパフォーマンスのレポートと最適化が可能になります。

2種類のインタラクションイベントがキャプチャされます。

## インプレッションイベント

インプレッションは、オファーがページ上でレンダリングされ、ユーザーに表示されるときに発生します。 イベントは、decisioning.propositionDisplay イベントタイプを使用して追跡されます。


```javascript
 alloy("sendEvent", {
            xdm: {
              _id: generateUUID(),
              timestamp: new Date().toISOString(),
              eventType: "decisioning.propositionDisplay",
              identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "authenticated",
                      primary: true
                    }]
                  },
              _experience: {
                decisioning: {
                  propositionEventType: {
                    display: 1
                  },
                    propositionAction: {
                            id: offerId,
                            tokens: [trackingToken]
                  },
                  
                   propositions: window.latestPropositions
                  
                }
              }
            }
          });
        }
```

## Offer Interaction

ユーザーがレンダリングされたオファー内のcall-to-action（CTA）をクリックすると、インタラクションが記録されます。 イベントは、decisioning.propositionInteract イベントタイプを使用して追跡されます。

```javascript
alloy("sendEvent", {
                xdm: {
                  _id: generateUUID(),
                  timestamp: new Date().toISOString(),
                  eventType: "decisioning.propositionInteract",
                  identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "ambiguous",
                      primary: true
                    }]
                  },
                  _experience: {
                    decisioning: {
                      propositionEventType: {
                        interact: 1
                      },
                      propositionAction: {
                        id: offerId,
                        tokens: [trackingToken]
                      },
                       propositions: window.latestPropositions
                    }
                  }
                }
              })
```

クリックやインプレッションのイベントに提案を含めることは、Adobe Journey Optimizerでの正確なオファーレポートに不可欠です。 これらの提案は、提示されたオファーを正確に表すもので、Adobe Adobeがユーザーとのやり取り（インプレッションやクリックなど）を、システムが行った具体的な意思決定に結びつけることができます。

提案内の各オファーには、アドビで生成される一意の ID であるトラッキングトークンが含まれます。 このトークンは、対応するクリックイベントまたはインプレッションイベントで、受信したとおりに（変更せずに）渡す必要があります。 一致するトラッキングトークンにより、アドビではユーザーアクションを正しいオファーの決定に正確に関連付けることができ、ダウンストリームレポートと AI ベースの最適化が可能になります。
