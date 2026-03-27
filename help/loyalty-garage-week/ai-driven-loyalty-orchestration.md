---
title: AIを活用したロイヤルティオーケストレーション - RFMからAdobe Real-Time Personalizationへ
description: 現代のロイヤルティプログラムは、AIを活用した革命の渦中にあります。 企業は、シンプルなルールベースのセグメンテーション（RFM モデルなど）から、予測分析や自律型意思決定エンジンに進化し、それぞれの顧客に対する次善のアクションをリアルタイムでオーケストレーションしています。
feature: Overview
role: User
index: false
exl-id: 726b5620-50a9-4ecf-8e62-a10358cc772b
source-git-commit: 783cf83169c9e12e07bf4ffc162adfe1b0c33d8f
workflow-type: tm+mt
source-wordcount: '5021'
ht-degree: 0%

---

# AIを活用したロイヤルティオーケストレーション

## RFMからReal-Time Personalizationへ

### はじめに

現代のロイヤルティプログラムは、AIを活用した革命の渦中にあります。 ブランドは、シンプルなルールベースのセグメンテーション（RFM モデルなど）から、顧客一人ひとりに対する&#x200B;_次善のアクション_&#x200B;をリアルタイムで調整する予測分析および自律型意思決定エンジンへと進化しています。 この変化はロイヤルティマーケティングの再定義につながります。AIを活用したプログラムでは、顧客エンゲージメントが15～30%向上し、パーソナライゼーションの精度が20～40%向上し、運用コストが25～50%低下します[[1]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 パフォーマンスの高い企業は、マスポイントプロモーションから、顧客データの分析、行動の予測、あらゆるチャネルをまたいだアウトリーチのパーソナライズをおこなうインテリジェントなロイヤルティ「エンジン」へと移行しています。 この記事では、AIを活用したロイヤルティオーケストレーションの仕組み、基本的なセグメンテーションから自律型AIに至るまでの成熟度モデル、企業がこうした進歩をどのように実現できるのかを探ります。 アドビでは、ロイヤルティにAIを導入するための枠組み（Starbucks、Sephora、Hilton、Deltaなどの実例を含む）を提供し、マーケターが活用を開始するための実行可能なステップ、生成AIやエージェント型オートメーションを含むAIが今後2～3年でロイヤルティを再構築する方法を解説します。

## 業界の背景と課題の特定

ロイヤルティマーケティングは、転換期を迎えています。 従来、多くのプログラムは、オファーのターゲティングに&#x200B;**RFM セグメンテーション** （最新性、頻度、金銭的価値）を利用していました。 RFMは、記述的で後方見回しのツールです。過去の値で顧客をランク付けするのに役立ちますが、3つの要素[[2]](https://www.pecan.ai/blog/how-predictive-analytics-supports-rfm-modeling/)に限定されます。 将来の行動を予測したり、オファーを動的にパーソナライズしたりすることはできません。 その結果、従来のプログラムは、画一的で反応が良いものでした。 今日のデジタルでオムニチャネルの世界では、これは問題です。顧客は現在、企業が顧客を深く知り、そのニーズに合わせてカスタマイズされた、タイムリーで適切な報酬を提供することを期待しています[[3]](https://www.epsilon.com/us/insights/blog/boost-loyalty-efficiency-with-ai) [[4]](https://www.epsilon.com/us/insights/blog/boost-loyalty-efficiency-with-ai)。 ロイヤルティに欠ける画一的なコミュニケーションやタイミングの悪いコミュニケーションでは、顧客はエンゲージメントを低下させます。 実際、消費者の&#x200B;**76%は、1回のネガティブな体験で十分に離脱できると回答しています**。これは、ロイヤルティプログラムが[[5]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)を満たす必要がある高い基準です。

さらに、多くの組織では、データとチームの分断という課題に直面しています。 多くの場合&#x200B;_複数の部門 – マーケティング、ロイヤルティ、e コマース、カスタマーサービスなど。  – 同じ顧客と個別にやり取りし_、メッセージの断片化につながる[[6]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)。 例えば、ロイヤルティチームは、ポイントのオファーを電子メールで送信する一方で、インサイトチームは同時にアンケートを送信し、マーケティング部門がプロモーションをプッシュします。その結果、顧客は[[7]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)に対して迷惑メールを送信してオプトアウトしています。 こうした連携の失敗は、ロイヤルティを損ないます。 統合されたインテリジェントなオーケストレーション **に対する**&#x200B;のニーズは、かつてないほど高まっています。 そこで、AIを活用したロイヤルティエンジンの出番です。このエンジンは、サイロ化を解消し、 AIにより、顧客接点をまたいで顧客データを統合し、マシンラーニング（機械学習）を適用することで、受動的な施策から先見的なパーソナライゼーションへと大規模に移行できます。 AI モデルは、四半期ごとに更新される静的セグメントの代わりに、_どの顧客が解約のリスクにさらされているか、誰が特定の報酬に反応する可能性が高いか、そしてどのようなメッセージが影響を最大化するか_&#x200B;を予測し、その後、「次善のアクション」をリアルタイムでトリガーすることができます。

## RFMから予測、エージェンティックへ：ロイヤルティ AI成熟度モデル

先進的なロイヤルティ企業は、データとAIの活用において、明確な成熟度を示しています。

**ステージ 1 – 記述的セグメンテーション （RFM）:**\
従来のプログラムのほとんどは、ここから始まりました。 顧客は、過去の行動（過去30日間の購入履歴、年間X ドルの支出履歴など）にもとづいて分類されます。 基本的なターゲティングには便利ですが、RFMは本質的に逆向きでシンプルです[[2]](https://www.pecan.ai/blog/how-predictive-analytics-supports-rfm-modeling/)。 その他の無数の要因（製品の嗜好、閲覧データなど）を考慮することもできず、将来の行動を予測することもできません。 _Limitations :_RFMは、すべての「価値の高い」顧客を同様に扱い、下位階層[[8]](https://www.pecan.ai/blog/how-predictive-analytics-supports-rfm-modeling/)における欠陥や機会の初期兆候を見逃す可能性があります。 「事後対応」アプローチです。

**ステージ 2 – 予測分析：**\
今日の主要なプログラムは、RFMを予測モデルに拡張または置き換えました。 **予測分析は、より多くの変数（閲覧履歴、過去のオファーに対する反応、顧客デモグラフィックなど）を使用し、顧客が次に行う可能性が高いことを予測することで、RFM**&#x200B;を上回るパフォーマンスを実現します[[2]](https://www.pecan.ai/blog/how-predictive-analytics-supports-rfm-modeling/)。 一般的なモデルには、解約確率、次の購入タイミング、商品レコメンデーション、生涯価値の予測などがあります。 これらのモデルにより、_プロアクティブ_&#x200B;なキャンペーンが可能になります。例えば、顧客がリテンションオファーで離脱する可能性が高い顧客を、実際に離脱する前に自動的にターゲティングできます[[9]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 予測ロイヤルティマーケティングは、ROIを向上させます。 例えば、スターバックスでは、予測モデルを適用して、従来のRFM シグナルよりも&#x200B;**30日前**&#x200B;に離脱するリスクがある顧客を特定し、そのセグメントの解約を25%削減する介入を可能にしました[[9]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 同様に、AI ベースの傾向モデルを利用している企業は、コンバージョンとリテンションが大幅に向上することを確認しています。以下の事例でご確認ください。

**ステージ 3 - エージェンティックオートメーション：**\
今日の最先端は&#x200B;_エージェント型AI_&#x200B;です。自律型エージェントは、各シナリオに人間のルールを必要とせずに、顧客データを継続的に学習および活用します。 ロイヤルティでは、**エージェント型AI システム**&#x200B;は、顧客の階層ステータスの調整や、無数の入力に基づくリアルタイムでの報酬のパーソナライズなど、独立した意思決定を行うことができます[[10]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[11]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 これは静的な予測スコアにとどまりません。AI エージェントは、マルチステップのカスタマージャーニーを動的に順序付けし、「戦略」タスクも処理することができます。 本質的に、ロイヤルティプログラムは、AIがあらゆるインタラクションを最適化することで始まります。 最近の調査によると、高度な&#x200B;_エージェント型AI_&#x200B;のロイヤルティシステムは、チャネルをまたいで独立した意思決定を行うことができ、必要に応じて人間と共同作業を行うことができます[[10]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[11]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 この段階で本格的に取り組んでいる企業はほとんどありませんが、先進企業では、AIを利用して、ユーザーごとのオファー頻度を自動的に調整したり、チャットボットがターゲットを絞って自律的に特典を提供するなど、さまざまな要素を試験的に導入しています。 Salesforceは、4段階の「エージェンティック成熟度」モデルを企業向けに定義しており、自律型エージェントへの移行には、堅牢なデータ、ガバナンス、段階的な拡張[[12]](https://www.salesforce.com/news/stories/agentic-maturity-model/)[[13]](https://www.salesforce.com/news/stories/agentic-maturity-model/)が必要であることに留意してください。 究極のビジョン：_最小限の人間の介入で実行するロイヤルティプログラム_。AIが継続的にプロモーションをテストおよび調整し、カタログに報酬を与え、ROIを最大化するための戦略をアウトリーチします。

多くの企業は、完全な自律性に移行するのではなく、これらの段階を経て進化します。 特に、AIが拡大しても、目標を設定し、データを倫理的に活用して、AIだけでは不可能なクリエイティビティを追加するためには、人間による管理と戦略が依然として重要です。 しかし、その方向性は明らかです。 ある業界ホワイトペーパーが要約したように、ロイヤルティプログラムは、AIを触媒および差別化要因として捉え、「単純な取引プログラムから、高度で予測的かつ自律的なエンゲージメントシステムへ」進化しています[[1]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。

## AIを活用したロイヤルティオーケストレーションの仕組み

AIを活用して調整されたロイヤルティプログラムでは、あらゆる顧客とのやり取りを最適化できます。 このアプローチを定義する3つの重要な機能は次のとおりです。

**1. 次善のアクション エンジン：**\
AIを活用したエンジンは、静的なキャンペーンの代わりに、_「この顧客にとって最適な次のインタラクションは何か？」をリアルタイムで決定します。_[[14]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction) [[15]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)。 これらのエンジンは、顧客のプロファイル、コンテキスト、および可能性のある行動を評価し、適切なチャネルで適切なメッセージや報酬を適切なタイミングで配信します[[14]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction) [[15]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)。 例えば、顧客の解約リスクスコアが高く、しばらくポイントを交換していない場合、システムは、パーソナライズされたダブルポイントオファーを即座に生成して、リエンゲージする可能性があります。 別の顧客が価値の高いVIPの場合、次善のアクションは、その顧客を新製品のプレローンチに招待することです。 これは、「キャンペーン中心」のマーケティングから&#x200B;**顧客中心のオーケストレーション**&#x200B;への移行です。スケジュールに沿ってメールをブラストするのではなく、個々の顧客のニーズに積極的に対応します。 _影響は大きい&#x200B;:_McKinseyは、AIを活用した「次善のエクスペリエンス」フレームワークを実装すると、顧客満足度が15 ～ 20%向上し、収益が5 ～ 8%増加し、無関係な連絡先を削減することでサービスコストが20 ～ 30%削減されることがわかりました[[16]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)。 企業は、従来の調整されていない高頻度のコミュニケーション&#x200B;**[6]**[[17]](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)ではなく、[接点を順序付け](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)し、インテリジェントかつパーソナライズされたコンテンツをパーソナライズすることで、これらのメリットを実現します。

**2. Real-Time Personalization:**\
AIは、顧客のスピードに合わせてパーソナライゼーションを動かすことができます。 新しいデータ（購入、web サイトのクリック、カスタマーサービスへの電話）が入るとすぐに、マシンラーニングモデルは予測を更新し、関連するアクションをトリガーします。 Adobe Journey Optimizer（AJO）、Salesforce Loyalty Cloud （Einstein AIを搭載）、Brazeなどの最新のロイヤルティプラットフォームには、各インタラクション（メール、プッシュ通知、アプリ内メッセージなど）がコンテキストに沿ってカスタマイズされていることを確認するリアルタイムの意思決定エンジンが組み込まれています。 例えば、**Hilton Honorsは、24時間365日にAI エージェントを使用してゲストコミュニケーションをパーソナライズします。そのAIは、ゲストジャーニーを監視し、各段階（旅行前、宿泊中、滞在後）で最適なメッセージを送信します。**&#x200B;これにより、メンバー[[18]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)[[19]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)のエンゲージメント率が22%増加し、直接予約が15%増加しました。 別のケース：**SephoraのBeauty Insider** プログラムでは、AIを活用して、個別にパーソナライズされた商品レコメンデーションと特典（メンバーのプロファイルに合わせた誕生日ギフトなど）を提供し、オファーの引き換えが40%増加し、平均注文額が+25%増加しました[[20]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[21]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 これらの結果は、AIが各顧客の好み&#x200B;_（肌の色調、スタイルなど）を_&#x200B;学習し、その人に適切なインセンティブを生成することに起因しています[[20]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 重要なのは、AIが提供するオファーの内容&#x200B;_だけでなく、_&#x200B;いつ、どこで&#x200B;_をパーソナライズできることです。送信時間、チャネル（SMSとメールとアプリの比較）、さらにはクリエイティブ要素を最適化して、効果を最大化することができます_[22][ ](https://www.epsilon.com/us/insights/blog/boost-loyalty-efficiency-with-ai)[23][。 ](https://www.epsilon.com/us/insights/blog/boost-loyalty-efficiency-with-ai)AIなしでは、このような大規模な一対一のパーソナライゼーションは現実的ではありませんでした。

**3. 統合データとID解決：**\
AI オーケストレーションの基盤は、統合された顧客像です。 企業は、モバイルアプリ、web サイト、実店舗のPOS、電子メールの応答などをまたいでデータを接続する必要があります。 AIの脳を養う能力です。 多くの人がここで苦労しています。断片化されたデータは、AIが顧客の行動を完全に把握できないことを意味します[[24]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)。 したがって、顧客データプラットフォーム（CDP）への投資とID解決は前提条件となります。 _高度なロイヤルティプログラムでは、クラウドデータレイクとID グラフ_&#x200B;を使用して、ID （電子メール、電話番号、デバイス ID）を1つのプロファイル [[24]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)に統合することで、これを解決します。 例えば、**Popeyes UK**&#x200B;は、オフラインキオスクとオフラインのデータを単一のプラットフォーム（Bloomreach経由）に統合し、ロイヤルティゲーム「Chicken Spinner」を強化しました。 統合が完了すると、実店舗またはアプリ経由で注文した顧客に対して一貫した報酬を提供し、それに応じてオファーを調整できるようになります[[25]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses) [[26]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)。 その結果、メンバーと非メンバーの再訪問回数が30日以内に&#x200B;**倍増加しました**[27][。 ](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)これは、データ統合とAI主導のgamificationが、エンゲージメントを大幅に向上させることができることを示唆しています。 さらに、強固なID解決は、ロイヤルティの影響のアトリビューションを向上させます。 マーケターは、ロイヤルティ会員が購入に至るまでのチャネル間をどのように移動するかを把握できるようになり、プログラムの影響度に対する正確な貢献度を特定できるようになります[[28]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)。 （たとえば、店舗での販売を以前のSMS オファーに帰する）。 _業務上_&#x200B;企業は、ポイントの負債データにも取り組む必要があります。AIを活用して、引き換え率と「破綻」（未使用のポイント）をより正確に予測することで、財務部門を支援できます。これについては後ほど説明します。

これらの機能により、ロイヤルティは独立したマーケティング戦術ではなく、あらゆる顧客接点に組み込まれた&#x200B;**リアルタイムのAIを活用したエンジン**&#x200B;となります。 Starbucksのような企業は、この統合を次のように示しています。StarbucksのAI プラットフォーム（「Deep Brew」）は、週に&#x200B;**9000万件以上の取引を分析し、顧客をマイクロセグメント（毎日** 400,000件までのユニークセグメント **）にセグメンテーションし、アプリでパーソナライズされたオファーを自動化します**[29][{60]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 [](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)そうすることで、Starbucksは訪問頻度を8%向上させ、メンバーの平均支出額を12%増加させました[[29]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[31]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 言い換えれば、同社は手作業によるキャンペーン管理から脱却し、AIを活用したアプローチに移行しました。このアプローチでは、顧客ごとに少しずつ異なる体験を提供することが、全取引の推定30%を促進するプログラムの重要な要因となります。 このレベルの洗練は、ロイヤルティのベンチマークになりつつあります。

## 戦術的フレームワーク：ロイヤルティにおけるAI オーケストレーションの導入

ロイヤルティ担当者には、AIを活用するためのロードマップが必要です。 ここでは、短期的、中期的、長期的な行動に合わせた段階的なフレームワークを紹介します。

**1. データ基盤とID （月0 ～ 6）:**
まず、顧客データとテクノロジースタックを監査することから始めます。 すべてのソースからのデータを、単一の顧客像[24]に統合できることを確認します。 これには、CDPを導入することや、データ統合を向上させるためにロイヤルティプラットフォームをアップグレードすることが含まれます。 ID解決に取り組む – オフラインとオンラインのIDの照合を大幅に改善することで、パーソナライゼーションが大幅に向上します[32] [33]。 多くの企業は、ID解決が、顧客中心のマーケティングにおける最大の技術的ハードルであると考えています。これは、AIそのものよりも上に挙げられています[32]。 そこで、パートナーシップを構築するか、ツール（AmperityやLiveRampなどのサードパーティサービス、Braze、Salesforceなどの機能）を使用して、顧客レコードを一致させ、ギャップを埋めます[34] [35]。 また、データガバナンスとプライバシーコンプライアンスに先行対応することも重要です。より多くのデータをモデルに送り込むことで、同意と倫理的な使用に関するポリシーを確実に適用できます。 即座の対応：IT部門、マーケティング部門、データサイエンス部門を招集し、ロイヤルティに関連するあらゆるデータをマッピングして、統合する計画を立てます。

**2. パイロット予測モデル （月3 ～ 9）:**\
すべてを自社で構築する必要はありません。プラットフォームで利用できる実証済みのAI モデルを活用するか、オープンソースのフレームワークから始めます。 クイックウィンの一般的な試験運用には、解約予測モデル（解約する可能性の高いメンバーを特定）と次善のオファーモデル（各メンバーに最適な報酬や商品を推奨）があります。 例えば、多くのロイヤルティ SaaS ソリューション（Salesforce、Oracle CrowdTwistなど）には、設定可能な予測分析モジュールが組み込まれています。 スターバックスが予測分析を初めて導入したとき、彼らは解約予測に焦点を当て、前述のように、リテンションのインセンティブでリスクのある顧客をターゲットにするのに役立ちました（解約率を25%削減しました） [9]。 もうひとつの試験的な分野は、生成AIを利用してパーソナライズされたコンテンツです。例えば、生成AIを利用して、様々なセグメントに合わせたメールコピーを作成できます。 IDC FutureScapeのレポートによると、2027年までに、小売企業の40%が動的コンテンツにGenAIを使用し、コンバージョン率を向上させ、コンテンツコストを30%削減します。[36] まず、マーケターは、AIを活用したクリエイティブテスト（件名、オファーテキスト、画像のパーソナライゼーション）を今すぐ実施する必要があります。 コントロールグループに対してこれらのパイロットを測定し、上昇率を証明します。 初期の成功は、より広範なAI投資のためのビジネスケースを構築します。

**3. 次善のアクション決定の紹介（6 ～ 18か月）:**\
データと初期モデルを導入し、**リアルタイム決定エンジン**&#x200B;をデプロイして、チャネルをまたいでオーケストレーションします。 これは、ジャーニーオーケストレーションツール（Adobe AJOのジャーニーAI、Marketing CloudのSalesforce Einsteinなど）やスタンドアロンの意思決定ハブの一部になります。 エンジンは、イベント（サイト閲覧、購入、インバウンド顧客からの問い合わせ）を受け取り、ルールとAIを適用して次のアクションを決定する必要があります。 焦点を絞ったユースケースから始めます。たとえば、カートの放棄について：ロイヤルティメンバーがカートを放棄した場合、エンジンは、予測されるインセンティブの感度に基づいて、ポイントインセンティブとメール対アクションなしでプッシュ通知を送信するかどうかを決定します。 いくつかの価値の高いジャーニー（オンボーディング、リエンゲージメント、ウィンバック）を定義し、次善のアクションシステムによりメッセージを調整します。 ここで&#x200B;**連絡先ガバナンス** ルールを作成することが重要です。そのため、AIが過剰にコミュニケーションすることはありません。 たとえば、ある通信会社では、オープンサービスの問題を抱える顧客にマーケティングを一時停止するだけで、聴覚障害の重複を回避できるため、NPSと解約が向上したことがわかりました[37] [38]。 AIは、そのようなルールを自動的に組み込むことができます（例：「サービスチケットが開封されている場合はアップセルしない」）。 この段階で、社内に&#x200B;_AI ガバナンスカウンシル_&#x200B;を設置します。社内の部門横断的な関係者は、偏りを監視し、AIに関する意思決定がブランド価値に沿ったものであることを確認し、システムを継続的に改善します[39]。

**4. すべてのタッチポイントにPersonalizationを拡張（12～24か月）:**\
AI オーケストレーションを、モバイルアプリ、実店舗POS （チェックアウト時にスタッフにオファーを提案するなど）、コールセンター（AIを活用したインサイトをエージェントに提供する）、有料メディア（ロイヤルティデータを利用して広告のターゲティングを行う）など、ロイヤルティエコシステムのあらゆるチャネルに拡張できます。 真のオムニチャネルロイヤルティを実現するには、社内の分断を解消する必要があります。 ロイヤルティ施策を「メール配信」と分けずに、統合された顧客体験計画の一部にするため、部門やプロセスの再編が必要になる場合があります。 例えば、AI ツールを使用して、あらゆる顧客対応チームを対象としたトレーニングに投資します。コールセンターのスタッフに対して、AIが生成した、ロイヤルティの低い会員を惹きつける推奨事項を信頼し、行動するようにトレーニングします（ある航空会社の補償伝票に対するAI ガイダンスにより、ターゲティングがリスクのある顧客を210%改善し、顧客離れの意図を5559%[41}しました。 ]さらに、**アトリビューションフレームワーク**&#x200B;を調整して、クロスチャネルの影響を測定します。最新の分析では、モバイルアプリのオファービューを実店舗での購入に接続できます[28] [41]。 AI主導のパーソナライゼーションによる売上向上を示すことは、継続的な予算を確保するのに役立ちます。 オムニチャネルロイヤルティの高い企業の目標：_アクティブなロイヤルティメンバーが非会員と比較して、売上を15～25%、再購入率を20～30%向上_&#x200B;させます[[42]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)。

**5. 自律型ロイヤルティ管理への移行（24か月以上）:**\
長期的な目標（2年以上）は、**エージェント型AI**&#x200B;機能を有効にすることです。基本的には、部分的または完全に自動運転のロイヤルティプログラムです。 これは、AIをマイクロターゲットのオファーだけでなく、より高度な意思決定に役立てることを信頼することを意味します。 例えば、エージェンティックシステムでは、予測される責任とエンゲージメントの弾力性に基づいてポイント価格（減価またはポイント利回りの増加）を自律的に調整したり、メンバーが何を重視するのかを分析して新しい報酬体験を設計したりできます。 一部のプログラムでは、AIが個別のプロモーションを決定します（例：各メンバーの行動に合わせた「驚きと喜び」の報酬）。 今後のシステムでは、ロイヤルティの経済的価値をリアルタイムで管理し、さまざまなセグメントに対して&#x200B;_動的な獲得/消化率_&#x200B;などの戦略を展開して、責任と活動のバランスを取ることになるでしょう。 業界の予測によると、2026～2028年までに&#x200B;**完全自律型ロイヤルティプログラム管理が実現する可能性があります**。AIによって、戦略から実行までのあらゆる段階が管理されます[[43]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[44]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 企業は、基盤となるインフラストラクチャに投資し、ロイヤルティチームのAI リテラシーを&#x200B;**向上させることで準備する必要があります**。 その間、AIと人間のハイブリッドな「ケンタウアー」アプローチが賢明であると言えます。AIに最適化を提案させ、人間にそれらを承認および指導させ、自信を持って成長するにつれてAIの範囲を徐々に拡大させます。 「AI ロイヤルティラボ」または専用のイノベーションチームを確立すると、これらの高度なアイデアのテストを迅速化できます[[45]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[46]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。

これらの手順を通じて、**顧客体験を中心に据えます。** AIは、会社の指標を最適化するだけでなく、メンバーのロイヤルティ価値を高める必要があります。 実際には、それはAIを活用して顧客に本物の方法（パーソナライズされた認識メッセージ、タイムリーなサービス復旧オファーなど）で驚きと感動を与えることを意味します。感情的なロイヤルティを築くものですが、これについては後の記事で解説します。 AI オーケストレーションを適切に実施することで、アルゴリズムが舞台裏にいるかもしれませんが、顧客がより適切で迅速に対応できるようになり、ロイヤルティプログラムを&#x200B;_より人間味のある_&#x200B;ものにすることができます。

## 実例とデータポイント

企業がAIを活用してロイヤルティオーケストレーションを実施した結果を具体的に示すと便利です。

**Wendy&#39;s - パーソナライズされたオンボーディング：**\
ファストフードチェーンのWendy’sは、生成AIを活用して新規会員ごとにオンボーディング体験をカスタマイズする、AIを活用したロイヤルティプラットフォームを立ち上げました。 一般的なウェルカムメールの代わりに、新しいメンバーの購入履歴や購入場所を分析し、カスタマイズされた初回特典（無料で利用できる商品など）を提供します。 この取り組みにより、従来の画一的なアプローチ **[47]****[48]**&#x200B;と比較して、新規登録の完了率[が](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)23%、初回購入コンバージョン [が](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)18%増加しました。 ロイヤルティジャーニーの最初の段階でAIを利用することで、エンゲージメントを促進することを表しています。

**Starbucks - AI マイクロセグメンテーションと次善のオファー：**\
スターバックスのAI利用は（「ディープブリュー」 AI エンジンを介して）しばしばクラス最高として挙げられます。 Starbucksでは、数百万ものデータポイントを処理することで、詳細なセグメントを作成し、個別のオファーを生成しています（例えば、雨季の午後に特別な飲み物の提案を提供する、特定の顧客をターゲットにしたボーナススター付きのユニークな飲み物の提案）。 StarbucksのAIは、毎日&#x200B;**400,000以上の独自のハイパーセグメントを生成しており**、リアルタイムでマーケティングを調整しています[[49]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[50]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 効果：訪問の頻度が増加（+8%）し、ロイヤルティメンバーの訪問1回あたりの支出が増加（+12%）し、オファーの引き換え率が27%増加しました[[49]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[51]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 これは、継続的なリセグメンテーションとテストの力を示しています。こうした大規模なパーソナライゼーションは、AI アルゴリズムでのみ実現可能です。

**デルタ航空 – AI サービス エージェント：**\
デルタ航空のSkyMiles ロイヤルティプログラムは、カスタマーサービスにおけるAI 「エージェント」を活用して、一般的なロイヤルティに関する問い合わせや問題を処理します。 これらのAI エージェントは、ポイント残高に関する質問に答えたり、アカウントの単純な問題を解決したり、見逃している可能性のあるメリットをメンバーに積極的に通知したりすることができます。 Deltaによると、同社のAIがロイヤルティに関するカスタマーサービスからの問い合わせの&#x200B;**60%を自律的に処理しており**、平均応答時間を数時間から数分に短縮しています。 その結果、SkyMiles メンバーの顧客満足度スコアは19%[[52]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[53]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)上昇しました。 これは主にカスタマーサポートでAIを紹介するものですが、ロイヤルティと密接に結びついています。迅速な問題解決と情報にもとづくエンゲージメントは、メンバーの全体的なロイヤルティ体験を向上させ、アクティブであり続ける可能性を高めます。

**Target - AIによって最適化された報酬ミックス：**\
TargetのCircle ロイヤルティプログラムは、AI分析を活用して報酬構造を最適化しています。 AI システムは&#x200B;**500億を超えるデータポイントを毎月**&#x200B;分析し、どの報酬のしきい値が最も増分支出を促進するかなどの傾向を特定します[[54]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 ある事例では、AIは、ポイント引き換えのしきい値を調整することで、収益性を損なうことなく引き換えの頻度が高まり、メンバーの支出が14%増加し、_メンバーの支出が_&#x200B;全体的な引き換えコストを22%[[54]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)[[55]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)であることが分かりました。 基本的に、AIはAdobe Targetで、エンゲージメントが向上した（メンバーがより早く特典を受け取り、より多くの買い物をした）のに加えて、使用されていないポイントが少なく、信頼性が低下する、より優れたスポットを見つけるのに役立ちました。 これは、AIが顧客と企業価値のバランスを取る好例であり、静的分析では見落とされる可能性があります。

**Bloomreach ケース - Revolution Beauty:**\
Revolution Beauty （英国ブランド）のBloomreachの事例では、オムニチャネル AI オーケストレーションの利点が示されました。 同社は、ロイヤルティの高い顧客に対して、ポイント残高に関するパーソナライズされたダイレクトメールを配信し、その後、ポイントの使用を促すweb サイトポップアップを表示するキャンペーンを実施しました。 コンテンツもタイミングもデータドリブン型でパーソナライズされていました。 キャンペーン _では特別割引も提供されませんでした_。既存の特典と合わせてパーソナライゼーションをスマートに使用しました。 ブランドのダイレクトメール施策の中で過去最高のパフォーマンスを示し、期間中&#x200B;**[56]**[[57]](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)に、[ ロイヤルティの引き換えが](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)20%増加しました。 これは、AI オーケストレーション（メール + web調整、パーソナライズされたメッセージ）が、必ずしも報酬コストを増やさずに大きな成果を上げることを強調しています。

これらの例は表面的なものではありますが、AI主導のロイヤルティオーケストレーションは理論的なものではなく、注目に値する結果をもたらしています。 エンゲージメント、頻度、支出、顧客満足度など、AIをロイヤルティ戦略に慎重に適用すれば、測定可能な改善が見られます。

## AIを活用して、顧客ロイヤルティを2～3年で再構築

今後に向けて、いくつかの方法で&#x200B;**AIがロイヤルティプログラム**&#x200B;をさらに変革すると予想しています。

**完全自律型ロイヤルティ管理：**\
前述したように、エージェンティック AIによって、ほぼ自律的にロイヤルティプログラムを運用できるようになります。 2～3年以内に、パイオニアは「自動運転」ロイヤルティ機能を展開することができます。 例えば、リアルタイムデータに応じて、週単位または日単位で&#x200B;_獲得/消化率、階層の選定、プロモーションカレンダー_&#x200B;を自動的に調整するAI アルゴリズムを利用できます。 初期の兆候は前途有望です – 技術大手企業は、マーケティングにおける自律型エージェントのフレームワークを開発しています。 2026年までに、AI ガバナンスとデータインフラストラクチャに投資した企業は、今日では手動での調整が必要な多くの意思決定（ガードレール内）をAIが処理できるようになります[[43]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe) [[44]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 これにより、ロイヤルティ経済に革命がもたらされ、プログラムがより俊敏になる可能性があります。 企業は、AIによる意思決定に対する信頼を構築し、監視を確立することで準備する必要があります（そのため、AIが誤って価値を過剰に提供したり、PRのミスを犯したりすることはありません）。 データを適切に活用できる企業は、パーソナライゼーションと効率性において、競争上の大きな優位性を享受できます。

**感情AIとセンチメント報酬：**\
AIが顧客の感情を測定し、それに応じてロイヤルティに関するやり取りを調整するようになるでしょう。 今後数年以内に、AIがテキスト（アンケート、ソーシャルメディア）または音声（通話記録）から顧客センチメントを解析し、トリガーの「共感を呼ぶ」ロイヤルティの応答を生成すると予想しています。 たとえば、AIが顧客の電子メールの中で不満のあるトーンを検出し、すぐにロイヤルティポイントや謝罪特典を提供して顧客離れを未然に防ぐことができます。 あるいは、データから人生上の出来事（引っ越し、子どもを持つ）を特定し、そのマイルストーンに合わせてサプライズの報酬を提供することもできます。 予測では、2025年から2027年までに、プログラムはAIを利用して&#x200B;_感情的な状態_&#x200B;を評価し、顧客の気分や生活のコンテキスト [[58]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)[[59]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)に響く報酬を提供します。 一部の企業では、既にこの課題に取り組んでいます。たとえば、センチメント分析を活用してService Recovery Rewardsを強化しています。 この傾向は、ロイヤルティと顧客体験管理の境界線を曖昧にしますが、最終的には感情的な絆（「このブランドは私を理解している」という気持ち）を深めます。 マーケターは、**感情的なロイヤルティ指標**&#x200B;とそれに基づいて行動できるAIを組み込む方法を、取引指標だけでなく、検討する必要があります。

**AIがキュレートしたコミュニティとGamification:**\
また、AIが、ロイヤルティメンバー間のコミュニティを促進する上で役割を果たすことも確認します（記事4ではコミュニティについて詳しく説明しています）。 技術面では、AIによって顧客がグループの課題とマッチングしたり、友人を紹介したりして、プログラム内に「マイクロコミュニティ」を生み出すことができます。 たとえば、フィットネスブランドのロイヤルティアプリであれば、AIを利用して地元の会員を課題に分類することができます（例えば、ペロトン型のリーダーボードですが、同様のスキルレベルや関心のためにAIによって選別されているとします）。 これにより、ソーシャルインタラクションを通じてエンゲージメントを向上できます。 AIを活用した&#x200B;**チャレンジベースのロイヤルティ**&#x200B;要素 – パーソナライズされたクエスト、動的に調整された難易度（ビデオゲームのAIがプレーヤーに適応する方法と同様）が増加すると予想されます。 今後2～3年で、生成AIと強化学習の成熟度が高まるにつれ、ロイヤルティプログラムは基本的に&#x200B;_進化し続けるゲーム_&#x200B;を作成し、メンバーを購入の途中で夢中にさせることができます。 AIは、新しい課題のアイデアやコンテンツを継続的に生成できます（例えば、生成AIは、ポイントに対してブランドに関するユニークな疑問を作成します）。 ロイヤルティプログラムは、特に若年層の消費者にとって、より魅力的かつ魅力的なものになります。

**業界をまたいだロイヤルティエコシステム：**\
もうひとつの新たなテーマは、AIを活用して、パートナーシップと連合のロイヤルティをよりスマートに実現することです。 AIは、2027年以降、ブランド全体でデータと価値をつなぎ合わせ、顧客が様々なコンテキストでシームレスに獲得し、活用できるエコシステムを形成するのに役立ちます[[60]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 AmazonやAppleのクレジットカードのパートナーは、その報酬を他のプログラムと統合しています。 AIを活用すれば、それらの連携の複雑さを管理できます（業界をまたいで行動を追跡し、各パートナーにROIを確実に提供して、不正行為を防止します）。 顧客体験は、小売、旅行、ホスピタリティなどにまたがる「ロイヤルティウォレット」となり、AIはエコシステム全体を通じてパーソナライズします（例：顧客がエコフレンドリーな報酬を好むことを認識し、パートナーブランド全体でオプションをキュレーションする）。 マーケターは、競争の原動力を再構築する可能性があるため、この分野に注目する必要があります。現在、最も激しい競合他社が、明日のロイヤルティネットワークの一部になるかもしれず、その逆もまた真なりです。

要約すると、AIはロイヤルティの軌跡は、より自律的で、共感的で、エコシステムとのつながりを重視するようになっています。 今後、ロイヤルティマーケターの役割は、手作業による施策の実施から、AI システムの管理、戦略、クリエイティブな方向性の確立、AIがブランド価値に沿ったものであるようにすることに移行する可能性があります。 専門家の間で見られたコンセンサスは、現在AIに注力している企業のほうが、はるかに有利な立場にあるということです。 McKinseyの記事によると、_AIは単なるロイヤルティプログラムへのアップグレードではなく、企業と顧客との関係を構築する方法を根本的に変革するものです_。その結果、トランザクションベースの受動的なモデルから、先見的でインテリジェント、かつ感情的に豊かなエンゲージメントへと移行しています[[61]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 今こそ準備の時です。

## &quot;This Quarter&#39;s Playbook&quot; Checklist - What Loyalty Marketers Should Now

AIを活用したオーケストレーションを導入する準備ができているロイヤルティリーダーのために、次の四半期に取り組むべきアクションを紹介します。

- **データ準備状況の評価：**\
  顧客データの完全性と品質を監査します[[39]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 購入、行動、エンゲージメントのデータを統合していますか？ ギャップを特定し（例：プロファイルにリンクされていない実店舗内トランザクション）、IT部門と協力してギャップの解消に取り組む あらゆるAI施策の第一歩は、クリーンな統合データの活用です。

- **予測分析を使用したクイックの勝者の取得：**\
  実装する1つまたは2つの予測モデル（解約リスク、商品レコメンデーションなど）を選択します。 ロイヤルティプラットフォームに組み込まれたツールや、データサイエンスに精通していないシンプルなAI サービスを使用しましょう。 A/B テストを実施し、パフォーマンスの向上を実証。 基本的な解約モデルを用いた試験的な施策でも、具体的なROIを示して賛同を得ることができます。

- **AIを活用したロイヤルティプラットフォームへの投資：**\
  現在のシステムがリアルタイムの意思決定に対応していない場合は、アップグレードを検討しましょう。 Einstein AI、Adobe Experience Cloud（Journey Optimizer）、Oracle CrowdTwist、Epsilon PeopleCloud Loyalty[[62]](https://www.epsilon.com/us/insights/blog/boost-loyalty-efficiency-with-ai) [[63]](https://www.epsilon.com/us/insights/blog/boost-loyalty-efficiency-with-ai)を使用したSalesforce Loyalty Managementなどのエンタープライズソリューション、またはジャーニーオーケストレーション用のBrazeやmParticleなどのモジュラーツールを検討します。 新しいベンダーが強力なAIと自動化機能を備えていることを確認し、トリガー、セグメンテーション、パーソナライズをすぐに処理できるようにします。

- **早期にAI ガバナンスを確立：**\
  部門横断的なチーム（マーケティング、分析、法務、運用）を編成して、AI ガイドラインを設定します[[64]](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)。 連絡先の頻度、パーソナライゼーションの境界に関するポリシーの決定（例：顧客を惹きつける可能性のある機密性の高いパーソナライゼーションの回避）、バイスチェック（AIによるオファーが公平で包括的なものであることを確認する）を行います。 ガバナンスを確立することで、後で拡張がスムーズになります。

- **チームのスキルアップ：**\
  今四半期は、ロイヤルティ/CRM チームがAIの基本を学ぶための時間を確保します。 マシンラーニングモデルの仕組みに関するトレーニングを主催したり、分析チームの同僚に最近のテストでAIの出力をデモしてもらったりします。 目標は、マーケターをデータサイエンティストに変えることではなく、AI ツールをチームが信頼し、理解できるようにすることです。 オートメーションが向上するにつれて、これは重要になるでしょう。 AIを利用して、テストと学習のマインドセットを促進しましょう。

- **オーケストレーションの使用例を1つ特定：**\
  AIを利用して、改善すべきカスタマージャーニーをすばやく特定。 例えば、「新規会員のオンボーディング」や「休眠会員のウィンバック」などです。 現在のジャーニーをマップ化し、データ主導のバージョンを設計します（おそらく次善のアクションロジックやマルチチャネルトリガーを使用して）。 小さなセグメントに実装します。 これにより、クロスチャネルの調整や、意思決定におけるAI インサイトの活用に関する能力を強化できます。

- **財務パートナーとエンゲージ：**\
  財務チームやCFO チームでロイヤルティモデリングを積極的に行う。 AIが引き換えを促進する可能性があるため、ポイント（繰延責任）を考慮する方法を調整する必要がある可能性について説明します（良い点ですが、会計に影響します）。 AIの強化に関するROIの予測を共有します（例：「X%のリテンション向上が予想され、Y ドルの増分収益につながる）」 CFOの言葉（財務成果）を話すことは、AI予算のサポートを得て、責任管理の驚きを避けるのに役立ちます。

- **AIを活用した「今月のテスト」を計画：**\
  体系的なテスト： 月または四半期ごとに、少なくとも1つの新しいAI主導のキャンペーンや機能を実行し、比較して管理します。 たとえば、第1四半期ではAIがパーソナライズしたメールコンテンツと標準コンテンツの比較を検証し、第2四半期ではAIが決定したオファータイミングと固定スケジュールの比較を検証します。 結果の文書化： これにより、プログラムが改善されるだけでなく、社内のケーススタディライブラリを構築して、関係者にAIの価値を証明することができます。

ロイヤルティマーケターは、これらのステップを実行することで、AI主導のオーケストレーションを成功に導くための基盤を築きます。 成功の鍵は、小規模でも戦略的にも始めることです。データ基盤を構築し、迅速に成果を上げ、チームと経営陣の両方に教育することが重要です。 ロイヤルティプログラムは、常に&#x200B;**より強固な顧客関係の構築について**&#x200B;してきました。AIを活用することで、マーケターは、これまで不可能だった深度と規模でこれを実現できるようになりました。 AI主導のロイヤルティの未来に向けて、一歩先を行く時が来ました。

## 参照

- [対応型から予測型へ：AIがロイヤルティプログラムの成熟度とROIをどのように促進しているか](https://www.linkedin.com/pulse/from-reactive-predictive-how-ai-accelerating-loyalty-guinand-ph-d--jbhhe)
- [予測分析がRFM モデリングをサポートする仕組み – Pecan AI](https://www.pecan.ai/blog/how-predictive-analytics-supports-rfm-modeling/)
- [AIを活用した戦略でロイヤルティマーケティングの効率を向上 – Epsilon](https://www.epsilon.com/us/insights/blog/boost-loyalty-efficiency-with-ai)
- [ オムニチャネルロイヤルティプログラム：顧客維持率の向上 – Bloomreach](https://www.bloomreach.com/en/blog/omnichannel-loyalty-programs-a-comprehensive-guide-for-businesses)
- [顧客維持のためのAIを活用した次善のエクスペリエンス - McKinsey](https://www.mckinsey.com/capabilities/growth-marketing-and-sales/our-insights/next-best-experience-how-ai-can-power-every-customer-interaction)
- [Salesforceがエンタープライズ向けエージェンティック成熟度モデルをリリース - Salesforce](https://www.salesforce.com/news/stories/agentic-maturity-model/)
- [ID解決が顧客中心主義の邪魔になる – 合計小売業](https://www.mytotalretail.com/article/identity-resolution-gets-in-the-way-of-customer-centricity/)
