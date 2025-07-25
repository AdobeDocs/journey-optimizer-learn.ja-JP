---
title: インプレッション数およびインタラクションイベントのキャプチャ
description: インプレッションおよびインタラクションイベントをキャプチャし、Journey Optimizer内でレポート用のデータを準備します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: 7e6014b5-c5a6-467b-8e31-58c5d966464c
source-git-commit: bfeab1e933f2a510506c0ecf911df41e66cb959b
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# インプレッション数およびインタラクションイベントのキャプチャ

AJO Decisioning でオファーのインプレッション数およびクリック数のレポートを有効にするには、次のコンポーネントを設定する必要があります。
>[!NOTE]
>
> これらの前提条件は、[ 前のチュートリアル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset) のスキーマとデータセットの作成の節で既に完了しています

## &#x200B;1. Adobe Experience Platform（AEP）のデータセット

- **XDM ExperienceEvent** スキーマに基づくデータセット。

スキーマには、ページ URL`Web Details` リファラーなどを取得するフィールドグループを含める必要があります。

## &#x200B;2. データストリーム設定

- **データストリーム** をAdobe Experience Platformで作成する必要があります。
- すべての Web SDK イベントが適切な宛先に適切に取り込まれるようにするには、このデータストリームが上記で設定したデータセットにリンクされている必要があります。

## &#x200B;3. Adobe Experience Platform タグのプロパティ

- 前の手順で作成したデータストリームを使用するように設定されたAEP Web SDK拡張機能。
- Experience Cloud ID サービスが設定されました
- ECID というデータ要素がプロパティに追加されます
- オファーがレンダリングされるサイトに実装されます。


オファーのパフォーマンスに関するレポートを有効にするには、最初の手順として、オファーが表示されるタイミング（インプレッション）とオファーがクリックされるタイミング（インタラクション）を取得します。 これらのイベントは、エンゲージメントの測定、クリックスルー率の計算、Adobe Experience Platform内でのオファーの有効性の分析の基盤となります。

alloy （&quot;sendEvent&quot;）関数は、Adobe Journey Optimizer（AJO）から返されたオファーに対するユーザーインタラクションをログに記録するために使用されます。

sendEvent ペイロードは、イベントタイプ（インプレッションの場合は decisioning.propositionDisplay、クリックの場合は decisioning.propositionInteract）、一意のイベント ID、タイムスタンプ、ユーザー ID （identityMap）を含めることで、オファーのインタラクションをキャプチャします。 また、表示またはクリックされたオファー（提案）のリストと、正確なアトリビューションを確実にするトラッキングトークンも含まれます。 この構造により、Adobe Journey Optimizerにおけるパーソナライズされたオファーのパフォーマンスのレポートと最適化が可能になります。

次の 2 種類のインタラクションイベントが取り込まれます。

## インプレッションイベント

インプレッションは、オファーがページにレンダリングされ、ユーザーに表示される際に発生します。 イベントは、decisioning.propositionDisplay イベントタイプを使用してトラッキングされます。


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

## オファーインタラクション

インタラクションは、レンダリングされたオファー内でcall-to-action（CTA）をクリックすると記録されます。 イベントは、decisioning.propositionInteract イベントタイプを使用してトラッキングされます。

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

Adobe Journey Optimizerでオファーを正確にレポートするには、クリックおよびインプレッションのイベントに提案を含めることが不可欠です。 これらの提案は、ユーザーに提示された正確なオファーを表しているので、Adobeは、ユーザーのインタラクション（インプレッション数やクリック数など）を、システムが行った特定の意思決定に帰すことができます。

提案内の各オファーには、Adobeで生成される一意の ID であるトラッキングトークンが含まれます。 このトークンは、対応するクリックまたはインプレッションイベントで、受信したとおりに（変更なしで）渡す必要があります。 トラッキングトークンの照合により、Adobeでユーザーアクションを正しいオファー決定に正確に関連付け、ダウンストリームレポートと AI ベースの最適化を可能にします。
