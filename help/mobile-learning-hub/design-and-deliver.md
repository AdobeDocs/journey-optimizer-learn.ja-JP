---
title: デザインと配信
description: Adobe Journey Optimizerを使用してパーソナライズされたモバイル通信を作成、デザイン、配信する方法について説明します。 この包括的なガイドでは、プッシュ通知、アプリ内メッセージ、コンテンツカード、SMS、MMS、RCS、WhatsApp マーケティングメッセージ、コードベースのエクスペリエンスについて説明します。 リアルタイムのクロスチャネルモバイルメッセージ戦略で、顧客エンゲージメントを強化し、キャンペーンワークフローを効率化し、結果を促進します。
role: User
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
source-git-commit: e3bc8e24f6a8a59a84341f9d31d0e372fa6e99ab
workflow-type: tm+mt
source-wordcount: '1410'
ht-degree: 55%

---


# デザインと配信

Adobe Journey Optimizerを使用して効果的なモバイル通信を構築し、配信する方法を説明します。 プッシュ通知、アプリ内メッセージ、コンテンツカード、SMS/MMS/RCS、WhatsApp マーケティングメッセージ、コードベースのエクスペリエンスなど、オーディエンスに合わせてカスタマイズされ、モバイルエンゲージメントに最適化された様々なメッセージタイプを作成、デザイン、送信する方法を説明します。

>[!NOTE]
>
>Journey Optimizerを初めて使用する場合は、まず、次のプレイリストを視聴して、Journey Optimizerに慣れてください。[ジャーニー管理者およびマネージャー向けJourney Optimizerの概要 ](https://experienceleague.adobe.com/ja/playlists/journey-optimizer-getting-started-for-journey-administrators-and-managers)

## &#x200B;1. モバイルメッセージの設定

チャネルごとにモバイルメッセージを設定する方法を説明します。

>[!BEGINTABS]

>[!TAB 概要]

Journey Optimizerがサポートするモバイルチャネルと、それらのチャネルを使用してメッセージを設定および送信する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3430376?quality=12&learn=on&captions=jpn){transcript=true}

>[!TAB プッシュ]

### 前提条件

1. アプリが Mobile SDKと統合され、モバイルチャネル用に設定されていることを確認します。
2. [ プッシュチャネル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup) が設定されていることを確認します。
3. 顧客プロファイルとオーディエンスセグメントがターゲティングの準備ができていることを確認します。

### チュートリアル

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/push-notifications-overview
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/create-a-push-campaign
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notifications- Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/push-notifications-overview" title="プッシュ通知 - 概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3432679/?format=jpeg&nocache=1755891402383" alt="プッシュ通知 - 概要"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/push-notifications-overview" target="_blank" rel="referrer" title="プッシュ通知 - 概要">プッシュ通知 - 概要</a>
                    </p>
                    <p class="is-size-6">プッシュ通知を作成して、パーソナライズされたターゲットメッセージでいつでもモバイルアプリユーザーを引き付ける方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/push-notifications-overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure and send a push campaign">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/create-a-push-campaign" title="プッシュキャンペーンの設定と送信" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3452702/?format=jpeg&nocache=1755891402391&captions=jpn" alt="プッシュキャンペーンの設定と送信"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/create-a-push-campaign" target="_blank" rel="referrer" title="プッシュキャンペーンの設定と送信"> プッシュキャンペーンの設定と送信 </a>
                    </p>
                    <p class="is-size-6">キャンペーンでプッシュ通知を設定して送信する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/push-channel/create-a-push-campaign" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### 製品ドキュメント

| ![ プッシュの作成 ](./assets/configuration.svg) [**プッシュ通知を作成**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/push/create-push){target="_blank"} | ![ プッシュのデザイン ](./assets/content-management.png){width="50"}[**プッシュ通知をデザイン**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/push/design-push){target="_blank"} | ![ プッシュを送信 ](./assets/communication-channel.svg) [**プッシュ通知を送信**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/push/send-push){target="_blank"} |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

>[!TAB アプリ内]

### 前提条件

1. アプリが Mobile SDKと統合され、モバイルチャネル用に設定されていることを確認します。
2. アプリ内チャネルが設定されていることを確認します。
3. 顧客プロファイルとオーディエンスセグメントがターゲティングの準備ができていることを確認します。

### チュートリアル

<!-- CARDS
*https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/in-app-channel/in-app-messages-overview
* https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/in-app-channel/author-in-app-messages.html?lang=ja
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/create-campaigns/action-campaigns/in-app
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Author an in-app message">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/in-app-channel/author-in-app-messages.html?lang=ja" title="アプリ内メッセージを作成" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3410471?format=jpeg&nocache=1755891403133" alt="アプリ内メッセージを作成"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/in-app-channel/author-in-app-messages.html?lang=ja" target="_blank" rel="referrer" title="アプリ内メッセージを作成">アプリ内メッセージの作成</a>
                    </p>
                    <p class="is-size-6">アプリ内メッセージを作成およびテストする方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/in-app-channel/author-in-app-messages.html?lang=ja" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold"> 詳細情報 </span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create an in-app campaign">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/create-campaigns/action-campaigns/in-app" title="アプリ内キャンペーンの作成" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3451883?format=jpeg&nocache=1755891402919&captions=jpn" alt="アプリ内キャンペーンの作成"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/create-campaigns/action-campaigns/in-app" target="_blank" rel="referrer" title="アプリ内キャンペーンの作成">アプリ内キャンペーンの作成</a>
                    </p>
                    <p class="is-size-6">アプリ内メッセージとは何かを理解します。キャンペーンでアプリ内メッセージを作成、設定および公開する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/create-campaigns/action-campaigns/in-app" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold"> 詳細情報 </span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### アプリ内ジャーニーの作成

<!--CARDS
* https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/in-app-channel/create-an-in-app-message-in-a-journey.html?lang=ja
* https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/in-app-channel/create-experiments-for-in-app-messages.html?lang=ja
-->

### ドキュメント

| ![ メッセージの作成 ](./assets/configuration.svg) [**モバイルのアプリ内メッセージの作成**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/in-app/create-in-app){target="_blank"} | ![ コンテンツのデザイン ](./assets/content-management.png){width="50"}[**アプリ内コンテンツのデザイン**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/in-app/design-in-app){target="_blank"} | ![ 通知を送信 ](./assets/communication-channel.svg) [**アプリ内通知を送信**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/in-app/send-in-app){target="_blank"} |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

>[!TAB  コンテンツカード ]

### 前提条件

1. アプリが Mobile SDKと統合され、モバイルチャネル用に設定されていることを確認します。
2. [ アプリ内チャネル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup) が設定されていることを確認します。
3. 顧客プロファイルとオーディエンスがターゲティングの準備ができていることを確認します。

### チュートリアル

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/content-cards/create-content-cards
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create content cards">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/content-cards/create-content-cards" title="コンテンツカードの作成" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3434784/?format=jpeg&nocache=1755891403581&captions=jpn" alt="コンテンツカードの作成"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/content-cards/create-content-cards" target="_blank" rel="referrer" title="コンテンツカードの作成">コンテンツカードの作成</a>
                    </p>
                    <p class="is-size-6">アプリケーションのコンテンツカードを作成する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/content-cards/create-content-cards" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### 製品ドキュメント

| ![ コンテンツカードの作成と設定 ](./assets/configuration.svg) [**コンテンツカードの作成と設定**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/content-card/create-content-card){target="_blank"} | ![ コンテンツカードの設計 ](./assets/content-management.png){width="50"}[**コンテンツカードの設計**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/content-card/design-content-card){target="_blank"} |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

>[!TAB SMS/MMS/RCS]

### 前提条件

1. [SMS 資格情報とチャネル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel) および/または [MMS 資格情報とチャネル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces) が設定されていることを確認します – > RCS 設定については、以下のチュートリアルで説明しています。
2. 顧客プロファイルとオーディエンスセグメントがターゲティングの準備ができていることを確認します。

### SMS チュートリアル

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-mms-messages-overview
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-sms-messages
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-double-opt-in
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="SMS/MMS messages - Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-mms-messages-overview" title="SMS/MMS メッセージ - 概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3432680/?format=jpeg&nocache=1755891404155" alt="SMS/MMS メッセージ - 概要"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-mms-messages-overview" target="_blank" rel="referrer" title="SMS/MMS メッセージ - 概要">SMS/MMS メッセージ - 概要</a>
                    </p>
                    <p class="is-size-6">SMS および MMS メッセージを作成、スケジュール、配布して、外出先でも顧客に簡単にリーチする方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-mms-messages-overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure, author, and deliver SMS messages">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-sms-messages" title="SMS メッセージを設定、作成および配信" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3422696?format=jpeg&nocache=1755891404139&captions=jpn" alt="SMS メッセージを設定、作成および配信"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-sms-messages" target="_blank" rel="referrer" title="SMS メッセージを設定、作成および配信">SMS メッセージの設定、作成および配信</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer のキャンペーンとジャーニーで SMS メッセージを設定、作成および配信する方法を説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-sms-messages" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold"> 詳細情報 </span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Double opt-in for Sinch and Infobip">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-double-opt-in" title="Sinch および Infobip のダブルオプトイン" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3440273/?format=jpeg&nocache=1755891404148&captions=jpn" alt="Sinch および Infobip のダブルオプトイン"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-double-opt-in" target="_blank" rel="referrer" title="Sinch および Infobip のダブルオプトイン">Sinch と Infobip のダブルオプトイン</a>
                    </p>
                    <p class="is-size-6">SMS のダブルオプトインを設定する方法を説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-double-opt-in" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### MMS および RCS チュートリアル

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-mms
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Author an MMS message">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-mms" title="MMS メッセージの作成" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3437101/?format=jpeg&nocache=1755891404669&captions=jpn" alt="MMS メッセージの作成"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-mms" target="_blank" rel="referrer" title="MMS メッセージの作成">MMS メッセージの作成 </a>
                    </p>
                    <p class="is-size-6">Journey Optimizer を MMS サービスプロバイダーに接続する方法と、MMS チャネルサーフェスを作成する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/author-mms" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Journey Optimizer での RCS の設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464756/?format=jpeg&nocache=1755891404682&captions=jpn" alt="Journey Optimizer での RCS の設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Journey Optimizer での RCS の設定">Journey Optimizerでの RCS の設定 </a>
                    </p>
                    <p class="is-size-6">カスタム SMS プロバイダーを使用して、ブランド化されたインタラクティブな RCS メッセージを Adobe Journey Optimizer で設定および送信する方法について説明します。このチュートリアルでは、ネイティブメッセージアプリ内で、API 資格情報、Webhook、チャネル設定を指定し、リッチでパーソナライズされたメッセージエクスペリエンスを提供するジャーニーを作成するすべての手順について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### 製品ドキュメント

| ![ テキストメッセージの基本を学ぶ ](./assets/configuration.svg) [**テキストメッセージの基本を学ぶ**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/get-started-sms){target="_blank"} | ![ コンテンツの設計 ](./assets/content-management.png){width="50"}[**SMS、MMS、RCS メッセージの作成**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/create-sms){target="_blank"} | ![ 通知の送信 ](./assets/communication-channel.svg) [**テキストメッセージの確認と送信**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/send-sms){target="_blank"} |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

>[!TAB コードベースのエクスペリエンス]

### 前提条件

1. コードベースチャネルが設定されていることを確認します。
2. 顧客プロファイルとオーディエンスがターゲティングの準備ができていることを確認します。

### チュートリアル

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/create-a-code-based-experience-campaign
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create a code-based experience campaign.">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/create-a-code-based-experience-campaign" title="コードベースのエクスペリエンスキャンペーンを作成します。" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3449454/?format=jpeg&nocache=1755891405190&captions=jpn" alt="コードベースのエクスペリエンスキャンペーンを作成します。"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/create-a-code-based-experience-campaign" target="_blank" rel="referrer" title="コードベースのエクスペリエンスキャンペーンを作成します。"> コードベースのエクスペリエンスキャンペーンを作成します。</a>
                    </p>
                    <p class="is-size-6">コードベースのエクスペリエンスキャンペーンを作成して、サーバーサイド、API ベースまたは SDK ベースの実装方法をサポートしてパーソナライゼーションを拡張し、開発環境とシームレスに統合する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/create-a-code-based-experience-campaign" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Add Form Fields to Code-Based Experience Channel Templates">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences" title="フォームフィールドをコードベースのエクスペリエンスチャネルテンプレートに追加する" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3463992/?format=jpeg&nocache=1755891405203&captions=jpn" alt="フォームフィールドをコードベースのエクスペリエンスチャネルテンプレートに追加する"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences" target="_blank" rel="referrer" title="フォームフィールドをコードベースのエクスペリエンスチャネルテンプレートに追加する"> コードベースの Experience Channel テンプレートへのフォームフィールドの追加 </a>
                    </p>
                    <p class="is-size-6">コードベースのエクスペリエンスチャネル内で編集可能なフィールドを有効にすることで、開発者がマーケティングチームとの共同作業をどのように効率化できるかを紹介します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### 製品ドキュメント

| ![ コードベースのエクスペリエンスを作成 ](./assets/content-management.png){width="50"}[**コードベースのエクスペリエンスを作成**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/code-based-experience/create-code-based-experiences/create-code-based-experiences-landing-page){target="_blank"} |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

>[!TAB WhatsApp]

### 前提条件

1. [WhatsApp チャネル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel) が設定されていることを確認します。
2. 顧客プロファイルとオーディエンスがターゲティングの準備ができていることを確認します。

### チュートリアル

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/whatsapp-introduction
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/create-a-whatsapp-journey
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Introduction to the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/whatsapp-introduction" title="WhatsApp チャネルの概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470297/?format=jpeg&nocache=1755891405738&captions=jpn" alt="WhatsApp チャネルの概要"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/whatsapp-introduction" target="_blank" rel="referrer" title="WhatsApp チャネルの概要">WhatsApp チャネルの概要 </a>
                    </p>
                    <p class="is-size-6">このビデオでは、WhatsApp と Adobe Journey Optimizer の統合の価値の概要を紹介します。WhatsApp のグローバルなリーチとエンゲージメントのメリットを強調し、WhatsApp ビジネスアカウントの設定、アクセストークンの生成、メッセージテンプレートの作成などの主な前提条件を概説します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/whatsapp-introduction" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create a WhatsApp journey">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/create-a-whatsapp-journey" title="WhatsApp ジャーニーの作成" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470283/?format=jpeg&nocache=1755891405726&captions=jpn" alt="WhatsApp ジャーニーの作成"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/create-a-whatsapp-journey" target="_blank" rel="referrer" title="WhatsApp ジャーニーの作成">WhatsApp ジャーニーの作成 </a>
                    </p>
                    <p class="is-size-6">このチュートリアルでは、Adobe Journey Optimizer を使用して、複数ステップの WhatsApp ジャーニーを作成する手順について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/create-a-whatsapp-journey" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### 製品ドキュメント

| ![WhatsApp メッセージの作成 ](./assets/configuration.svg) [**WhatsApp メッセージの作成*](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/whatsapp/create-whatsapp){target="_blank"} | ![WhatsApp メッセージのプレビュー、検証、送信 ](./assets/communication-channel.svg){width="50"}[**&#x200B;WhatsApp メッセージのプレビュー、検証、送信**](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/whatsapp/send-whatsapp){target="_blank"} |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

>[!ENDTABS]

## 適用のベストプラクティス

* ユーザーの価値のある瞬間までの時間メッセージ：

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/identify-potential-conflicts
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Identify potential conflicts">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/identify-potential-conflicts" title="潜在的な競合の特定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3435528/?format=jpeg&nocache=1755891406215" alt="潜在的な競合の特定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/identify-potential-conflicts" target="_blank" rel="referrer" title="潜在的な競合の特定">潜在的な競合の特定</a>
                    </p>
                    <p class="is-size-6">重複するオーディエンス、同時タイムライン、共有されたコミュニケーションチャネル、ジャーニーやキャンペーン間の頻度制約など、潜在的な競合を特定および管理し、シームレスで顧客に優しいコミュニケーションエクスペリエンスを実現する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/identify-potential-conflicts" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

* コンテンツをパーソナライズ：

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/personalization-editor-overview
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-and-manage-saved-expressions-in-personalization-library
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Personalization editor - Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/personalization-editor-overview" title="パーソナライゼーションエディター - 概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3434964/?format=jpeg&nocache=1755891406853" alt="パーソナライゼーションエディター - 概要"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/personalization-editor-overview" target="_blank" rel="referrer" title="パーソナライゼーションエディター - 概要">パーソナライゼーションエディター - 概要</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer でパーソナライズできるコンテンツについて説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/personalization-editor-overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Use helper functions for personalization">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization" title="パーソナライゼーションへのヘルパー関数の使用" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3416781?format=jpeg&nocache=1755891406861&captions=jpn" alt="パーソナライゼーションへのヘルパー関数の使用"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization" target="_blank" rel="referrer" title="パーソナライゼーションへのヘルパー関数の使用">パーソナライゼーションへのヘルパー関数の使用</a>
                    </p>
                    <p class="is-size-6">パーソナライズ機能のヘルパー関数を使用してパーソナライゼーション値を変換する方法と、ヘルパー関数の様々なユースケースを説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Use and manage saved expressions in the personalization library">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-and-manage-saved-expressions-in-personalization-library" title="パーソナライゼーションライブラリの保存済み式の使用と管理" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/344987?format=jpeg&nocache=1755891406844&captions=jpn" alt="パーソナライゼーションライブラリの保存済み式の使用と管理"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-and-manage-saved-expressions-in-personalization-library" target="_blank" rel="referrer" title="パーソナライゼーションライブラリの保存済み式の使用と管理">パーソナライゼーションライブラリで保存済みの式を使用および管理</a>
                    </p>
                    <p class="is-size-6">保存したパーソナライゼーションライブラリ項目をメッセージで使用する方法と、パーソナライゼーションライブラリ項目を作成および管理する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/use-and-manage-saved-expressions-in-personalization-library" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold"> 詳細情報 </span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

* ユーザーの疲労を避けるためにメッセージ頻度を制御する：

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/assign-priority-score
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/journey-frequency-capping-and-prioritization
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Assign Priority Scores to Inbound Actions">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/assign-priority-score" title="インバウンドアクションへの優先度スコアの割り当て" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3445002/?format=jpeg&nocache=1755891407584&captions=jpn" alt="インバウンドアクションへの優先度スコアの割り当て"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/assign-priority-score" target="_blank" rel="referrer" title="インバウンドアクションへの優先度スコアの割り当て"> インバウンドアクションへの優先度スコアの割り当て </a>
                    </p>
                    <p class="is-size-6">インバウンドアクションに優先順位を付け、同じチャネル設定を使用して複数のインバウンドアクションの対象となる顧客に、最も優先度の高いコンテンツを配信する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/assign-priority-score" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Journey Frequency Capping and Prioritization">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/journey-frequency-capping-and-prioritization" title="ジャーニーのフリークエンシーキャップと優先順位設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3447613/?format=jpeg&nocache=1755891407596&captions=jpn" alt="ジャーニーのフリークエンシーキャップと優先順位設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/journey-frequency-capping-and-prioritization" target="_blank" rel="referrer" title="ジャーニーのフリークエンシーキャップと優先順位設定">ジャーニーのフリークエンシーキャップと優先度 </a>
                    </p>
                    <p class="is-size-6">インバウンドアクションに優先順位を付け、同じチャネル設定を使用して複数のインバウンドアクションの対象となる顧客に、最も優先度の高いコンテンツを配信する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/journey-frequency-capping-and-prioritization" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->
