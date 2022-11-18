---
title: Journey Optimizerの課題 — 概要と前提条件
description: ジャーニーキャンバスでジャーニーを構築する基本を理解します。
feature: Journeys
role: Admin
level: Beginner
hide: true
source-git-commit: 3cd8b1a5b98adbe822cd82db8c27137b534c16e3
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 7%

---


# Journey Optimizerの課題 — 概要と前提条件

![AJO チャレンジバナー](./assets/ajo-banner-challenges.png)

課題は、学習した内容を実行するために必要なシナリオと要件を提供します。 課題は、スキルレベルを評価し、知識のギャップを特定するのに役立ちます。

この節で説明する各課題では、実装する固有の使用例について説明します。 各チャレンジの最初に、ターゲットオーディエンス（ペルソナ）と必要なスキルを記載します。

## 前提条件

### 必要システム構成

* Journey Optimizer Sandbox へのアクセス
* 専用のトレーニングサンドボックスでチャレンジを完了することをお勧めします。 詳しくは、 [トレーニングサンドボックスの設定チュートリアル](https://experienceleague.adobe.com//docs/journey-optimizer-learn/configure-a-training-sandbox/introduction-and-prerequisites.html) 」を参照してください。
* 次のアクセス権が必要です。
   * *ジャーニー管理* または *ジャーニー管理者* 権限
   * テストプロファイルとその属性の表示
* AEM Assets Essentials をインスタンス用にプロビジョニングする必要があります
* E メールチャネルは、トランザクションメッセージとマーケティングメッセージに対して設定する必要があります

>[!NOTE]
> 演習は Luma サンプルデータに基づいて開発されました。 サンプルデータを使用して設定されたトレーニングサンドボックスを設定することをお勧めします。 チュートリアルを参照してください [サンプルデータをAdobe Experience Platformに読み込む](https://experienceleague.adobe.com/docs/platform-learn/tutorials/import-sample-data.html?lang=en) を参照してください。

### 必要なアクション

* Adobe Journey Optimizerを初めて使用する場合は、コースを修了してください [Journey Optimizerを使い始める (ジャーニーマネージャーと管理者向け )](https://experienceleague.adobe.com/?recommended=JourneyOptimizer-U-1-2021.1&amp;lang=ja).
* 開始する前に、 [luma-assets.zip](/help/challenges/assets/email-assets/luma-assets.zip) ファイル。 課題の解決に必要なすべてのアセットが含まれます。
* ダウンロードフォルダーから、 `luma-assets.zip` ファイルをコンピューター上の目的の場所に展開し、解凍します。

## ザストーリー

Luma は架空のスポーツアパレル会社で、複数の国に店舗があり、Web サイトでのオンラインプレゼンス、モバイルアプリがあります。 Luma はAdobe Journey Optimizerを使用して、接続された、コンテキストに沿った、パーソナライズされたエクスペリエンスを顧客に提供します。

Luma は、最新のアパレルとギアコレクションを宣伝し、既存のお客様への販売促進を目指しています。 Journey Optimizerで Luma のマーケティングキャンペーンとリテンションキャンペーンを実装するために雇われています。

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
   <a href="summer-collection-announcement-challenge.md">
    <strong>夏物コレクションのお知らせの作成 </strong>
    </a>
      <p>
      <em>新しい Luma 夏コレクションを昇格します。 </em>
      <p>
      <b>必要なスキル：</b>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html"> セグメントの作成</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html">HTML 電子メールコンテンツの読み込みと作成</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html">ユースケース - セグメントの読み取り</li>
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
      <a href="order-confirmation-challenge.md">
    <strong>注文の確認を作成</strong>
    </a>
    <div>
    <p>
    <em>オンライン購入が完了したら、注文確認メールを送信する
    </em>
    <p>
  </td>
  </tr>
  <tr>
    <td>
    <div>
    <a href="product-replenishment-challenge.md">
      <img alt="Luma Web サイト" src="./assets/email-assets/luma-ProductReplenishment.png"/>
    </a>
    </div>
    <td>
    <div >
      <a href="product-replenishment-challenge.md">
    <strong>製品補充通知の作成 </strong>
    </a>
    </div>
    <p>
    <em>以前に在庫切れの品目が在庫に戻った際に顧客に通知します</em>
    <p>
  </td>
  </tr>
  <tr>
    <td>
    <div>
    <a href="loyalty-status-welcome-email-challenge.md">
      <img alt="ようこそ" src="./assets/email-assets/luma-transactional-onboarding-1.png"/>
    </a>
    </div>
    <td>
    <div >
      <a href="loyalty-status-welcome-email-challenge.md">
    <strong>ロイヤルティステータスのお知らせメールの作成 </strong>
    </a>
    </div>
    <p>
    <em>ロイヤルティ顧客が新しい層に移り、新しいメリットを祝福し、通知を受け取ったら、E メールを送信します</em>
    <p>
  </td>
  </tr>
</table>
