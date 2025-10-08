---
title: Journey Optimizer の課題 - 概要と前提条件
description: 課題は、学習した内容を実践するために必要なシナリオと要件を提供します。各課題では、実装する固有のユースケースに取り組みます。
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 87a79560-c098-4e72-abec-6b750ec730ee
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 99%

---

# Journey Optimizer の課題 - 概要と前提条件

課題は、学習した内容を実践するために必要なシナリオと要件を提供します。課題は、スキルレベルを評価し、知識のギャップを特定するのに役立ちます。

この節の各課題は、実装する固有のユースケースに対応しています。ターゲットオーディエンス（ペルソナ）と必要なスキルは、各課題の冒頭に記載されています。

## 前提条件

次の前提条件が満たされていることを確認します。

### 必要システム構成

* Journey Optimizer サンドボックスへのアクセス - 専用のトレーニングサンドボックスで課題を完了することをお勧めします。
* お使いのインスタンスに AEM Assets Essentials をプロビジョニングする必要があります。
* トランザクションメッセージとマーケティングメッセージ用に[メールチャネルを設定する必要があります](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja)。

### アクセス権限

次のアクセス権限が必要です。

* *ジャーニーマネージャー*&#x200B;または&#x200B;*ジャーニー管理者*
* テストプロファイルとその属性の表示

>[!NOTE]
> 演習は、Luma サンプルデータに基づいて作成されました。サンプルデータを使用してトレーニングサンドボックスを設定することをお勧めします。手順について詳しくは、[トレーニングサンドボックスの設定](/help/tutorial-configure-a-training-sandbox/introduction-and-prerequisites.md)のチュートリアルを参照してください。

### 必要なアクション

* Adobe Journey Optimizer を初めて使用する場合は、[Journey Optimizer の基本を学ぶ（ジャーニーマネージャーおよび管理者向け）](https://experienceleague.adobe.com/docs/courses/using/journeyoptimizer-u-1-2022-1-1-0.html?lang=ja)のコースを完了してください。

## ストーリー

Luma は架空のアスレチックアパレル会社で、複数の国に店舗があり、web サイトとモバイルアプリを備えたオンラインプレゼンスがあります。Luma は、Adobe Journey Optimizer を使用して、コネクテッドでコンテキストに応じた、パーソナライズされたエクスペリエンスを顧客に提供しています。

Luma は、最新のアパレルとギアのコレクションを宣伝し、既存の顧客の売り上げを伸ばしたいと考えています。Journey Optimizer で Luma のマーケティングおよびリテンションキャンペーンを実装するために雇われました。

## 課題

<table>
<tr>
<td>
 <div>
      <a href="summer-collection-announcement-challenge.md">
        <img alt="夏物コレクションのお知らせ用の画像" src="./assets/email-assets/luma-transactional-onboarding-3.png"/>
      </a>
      </div>
  </td>
  <td>
   <strong><a href="summer-collection-announcement-challenge.md">夏物コレクションのお知らせの作成 </strong>
    </a>
      <p>
      <em>既存の顧客のオーディエンスに夏物コレクションのお知らせメールを送信するジャーニーを作成します。</em>
      <p>
      <b>必要なスキル：</b>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ja"> セグメントの作成</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journeys/use-case-read-segment.html">セグメントの読み取り</li>
       <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=ja">HTML メールコンテンツのインポート</li>
  </td>
  </tr>
   <tr>
    <td>
    <div>
    <a>
      <img alt="ようこそ" src="./assets/email-assets/luma-transactional-onboarding-1.png"/>
    </a>
    </div>
    <td>
    <div >
      <a><strong><a href="loyalty-status-welcome-email-challenge.md">ロイヤルティステータスのようこそメールの作成</strong></a>
    </div>
    <p>
    <em>ロイヤルティ顧客が新しい層に移行したときにメールを送信して、お祝いの言葉と新しい特典について通知します。</em>
    <p>
    <b>必要なスキル：</b>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ja"> セグメントの作成</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journeys/use-case-read-segment-qualification.html">セグメントの選定</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=ja">HTML メールコンテンツの読み込みと作成</li>
  </td>
  </tr>
  <tr>
  <td>
  <div>
    <a href="order-confirmation-challenge.md">
      <img alt="Luma メール" src="./assets/email-assets/luma-transactional-order-confirmation.png"/>
    </a>
  </td>
  <td>
      <a href="order-confirmation-challenge.md"><strong><a href="order-confirmation-challenge.md">注文確認の作成</strong></a>
    <div>
    <p>
    <em>トランザクションメッセージの作成方法とパーソナライズ方法に関する知識をテストする</em>
    <p>
    <b>必要なスキル：</b>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/create-content-with-the-email-designer.html?lang=ja"> メッセージエディターでのメールコンテンツの作成</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=ja">パーソナライゼーションに関するコンテキストイベント情報の使用</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=ja">パーソナライゼーションへのヘルパー関数の使用</li>
  </td>
</table>
