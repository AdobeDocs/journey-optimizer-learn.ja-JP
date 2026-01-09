---
title: の設定と起動
description: Adobe Journey Optimizer（AJO）およびAdobe Experience Platform（AEP）でモバイルチャネルを設定し、モバイルアプリと統合し、マーケティングキャンペーンを確実に実行できるようにします。
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: false
index: true
jira: KT-19869
last-substantial-update: 2025-12-18T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: 317f270c49754b00ba41eac6c22476e4c63b21e4
workflow-type: tm+mt
source-wordcount: '2148'
ht-degree: 20%

---


# の設定と起動

**管理者** および **モバイルアプリ開発者** を対象に、Adobe Journey Optimizerでモバイルと web チャネルを設定して起動する方法を説明します。 前提条件、権限、プラットフォームのサポートを説明したあと、アプリ固有の設定を作成する手順を説明します。

>[!IMPORTANT]
>
> Journey OptimizerとExperience Platformを初めて使用する場合は、次のコースを受講して、Journey Optimizerのデータマネジメントの中心概念を理解してください。[Adobe Journey Optimizerでのインテリジェントなジャーニーアクティベーションのためのデータのエンジニアリング ](https://experienceleague.adobe.com/en/courses/ajo-engineer-data-for-intelligent-journey-activation){target="_blank"}
>


## Adobe Journey Optimizerのモバイル機能

プッシュメッセージ、アプリ内メッセージ、コンテンツのパーソナライゼーションなど、Adobe Journey Optimizerが開発者、マーケターおよび製品チームに提供するモバイル機能について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## チャネル設定

### モバイルプッシュとアプリ内

Journey Optimizerでのモバイル実装は、アプリ内の **Adobe Experience Platform Mobile SDK** 統合から始まります。 SDK は、データ収集や、Adobe Experience Platform（AEP）およびAdobe Journey Optimizer（AJO）などのアプリケーションとのインタラクションに不可欠です。

#### モバイルSDKとは

モバイルSDK:

- アプリイベント（画面ビュー、タップ、購入、ライフサイクルイベントなど）を収集し、**Adobe Experience Platform Edge Network** に送信します。
- **ID** および **同意** を管理して、Journey Optimizerが顧客プロファイルを安全に作成して使用できるようにします。
- **プッシュトークン** を登録および更新し、**プッシュイベントおよびアプリ内トラッキングイベント** をAdobe Experience Platformに返します。
- **[Journey Optimizer モバイル拡張機能と統合するので ](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer)** メッセージをエンドツーエンドで配信、レンダリング、測定できます。

モバイル SDKがアプリに統合されていない場合、Journey Optimizerでは次の点で信頼性に優れています。

- モバイルプッシュおよびアプリ内メッセージの配信とトラッキング。
- コンテンツカードのレンダリングとトラック
- リアルタイムのアプリ内動作を使用して、ジャーニーをトリガーに設定し、エクスペリエンスをパーソナライズします。

#### 新規実装に向けたガイド付きチャネル設定

新しいモバイルのアプリ内実装およびプッシュ実装の場合、出発点としてガイド付きチャネルのセットアップをお勧めします。 これにより、データストリームの設定ミスや拡張機能の欠落のリスクが軽減され、Assuranceを使用したSDKの検証について順を追って説明します。

>[!PREREQUISITES]
>
>次の点を確認します。
>
> - 組織用にプロビジョニングされた **Adobe Journey Optimizer** （AJO）。
> - [ データ収集およびJourney Optimizer権限 ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config#:~:text=Required%20permissions) を持つAdobe Experience Platform アクセス。
> - チャネルおよび設定セットアップの管理者権限がAJOにある。
> - モバイルアプリのソースコード（iOS、Androidまたはクロスプラットフォームフレームワーク）にアクセスします。
> - アプリでは、必要な OS レベルの機能（プッシュ権限、通知サービス拡張機能、バックグラウンドモードなど）が有効になっています。
> - 既存の設定オプションを使用している場合は、[ 現在のバージョンのAdobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"} を使用していることを確認してください


>[!VIDEO](https://video.tv.adobe.com/v/3433053/?learn=on)

詳しくは、[ ガイド付きチャネルセットアップの概要 ](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config.html?lang=ja){target="_blank"} を参照してください。


#### プッシュチャネルの手動設定

このガイドでは、データフローの把握や Firebase やApple Push Notification Service （APN）などのサービスとの統合から、モバイルアプリの設定や通知のテストまで、プッシュ通知を手動で設定して効果的に使用するために必要なすべての手順を説明します。

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs
{title = Push notification data flow and components}
{description = Learn how to setup and understand key services and workflows involved with push notifications in Journey Optimizer.}
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=2000&format=webply&optimize=medium}
{target = _blank}

* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=2000&format=webply&optimize=small}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview 
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification data flow and components">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" title="プッシュ通知のデータフローとコンポーネント" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=400&format=webply&optimize=medium" alt="プッシュ通知のデータフローとコンポーネント"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" title="プッシュ通知のデータフローとコンポーネント"> プッシュ通知のデータフローとコンポーネント </a>
                    </p>
                    <p class="is-size-6">Journey Optimizerでプッシュ通知に関連する主要なサービスとワークフローを設定し、理解する方法を説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification configuration">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" title="プッシュ通知の設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=400&format=webply&optimize=small" alt="プッシュ通知の設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" title="プッシュ通知の設定"> プッシュ通知の設定 </a>
                    </p>
                    <p class="is-size-6">Journey Optimizer でプッシュ通知を送信するように環境を設定する方法を説明します</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" title="モバイルアプリでのAdobe Experience Cloudの実装のチュートリアル" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="モバイルアプリでのAdobe Experience Cloudの実装のチュートリアル"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="モバイルアプリでのAdobe Experience Cloudの実装のチュートリアル">モバイルアプリでの Adobe Experience Cloud の実装のチュートリアル</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Cloud モバイルアプリケーションの実装方法を説明します。 このチュートリアルでは、サンプルの Swift またはAndroid アプリでのExperience Cloud アプリケーションの実装について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### その他のリソース


<!-- CARDS
* https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk
{target = _blank}
* https://developer.adobe.com/client-sdks/home/base/assurance
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Get the Adobe Experience Platform Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" title="Adobe Experience Platform Mobile SDKを入手" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Mobile SDKを入手"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDKを入手">Adobe Experience Platform Mobile SDKを入手 </a>
                    </p>
                    <p class="is-size-6">アプリケーションにAdobe Experience Platform Mobile SDKをインストールする方法を説明するガイドです。</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Assurance overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/base/assurance" title="Adobe Experience Platform Assuranceの概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Assuranceの概要"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" title="Adobe Experience Platform Assuranceの概要">Adobe Experience Platform Assuranceの概要 </a>
                    </p>
                    <p class="is-size-6">Adobe Experience Platform Assurance モバイル拡張機能の概要です。</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Mobile SDK対応チェックリスト

アプリをマーケターに渡す前に、**[Assuranceで次のことを確認し ](https://developer.adobe.com/client-sdks/home/base/assurance/){target="_blank"}** ください。

>[!SUCCESS]
> 
> [ Core SDKとJourney Optimizerの拡張機能の ] が読み込まれると、\
> [ 正 ] いデータストリームとデータセットでイベントのフローが発生している。\
> [ ]ID と同意は、すべての主要なイベントに存在する、\
> [ ] プッシュトークンとインタラクションが追跡される。\
> [ ] テストのアプリ内メッセージまたはコンテンツカードが少なくとも 1 つ表示され、インプレッションとして記録されている。


### コンテンツカード

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp
{title = Configure content cards support in Mobile SDK}
{description = Learn how to integrate content cards in your mobile application using Messaging SDK.}
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=2000&format=webply&optimize=medium}
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure content cards support in Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" title="Mobile SDK でのコンテンツカードのサポートの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=400&format=webply&optimize=medium" alt="Mobile SDK でのコンテンツカードのサポートの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" title="Mobile SDK でのコンテンツカードのサポートの設定">Mobile SDKでのコンテンツカードのサポートの設定 </a>
                    </p>
                    <p class="is-size-6">Messaging SDKを使用して、モバイルアプリケーションにコンテンツカードを統合する方法を説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### WhatsApp

**WhatsApp チャネル** を設定する方法を理解します。

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="WhatsApp チャネルの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1765310599408" alt="WhatsApp チャネルの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="WhatsApp チャネルの設定">WhatsApp チャネルの設定</a>
                    </p>
                    <p class="is-size-6">このチュートリアルでは、Adobe Journey Optimizer で WhatsApp チャネルを設定して、リアルタイムのビジネスメッセージを有効にする方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

標準のプロバイダー（Twilio、Synch または Infobip）を使用するか **カスタム SMS プロバイダーを使用して、** SMS/MMS/RCS チャネル）を設定します。

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="SMS API 資格情報とチャネルサーフェスの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1765310599850" alt="SMS API 資格情報とチャネルサーフェスの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="SMS API 資格情報とチャネルサーフェスの設定">SMS API 資格情報とチャネルサーフェスの設定 </a>
                    </p>
                    <p class="is-size-6">Journey Optimizer を SMS サービスプロバイダーに接続する方法と SMS チャネルサーフェスを作成する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="カスタム SMS プロバイダーの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1765310599834" alt="カスタム SMS プロバイダーの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="カスタム SMS プロバイダーの設定">カスタム SMS プロバイダーの設定</a>
                    </p>
                    <p class="is-size-6">Journey Optimizerでのカスタム SMS プロバイダーの設定、API 資格情報と Webhook の設定、オプトイン/オプトアウトキーワードの管理、パーソナライズされたキャンペーンの開始の方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="MMS API 資格情報とチャネルサーフェスの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1765310599863" alt="MMS API 資格情報とチャネルサーフェスの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="MMS API 資格情報とチャネルサーフェスの設定">MMS API 資格情報とチャネルサーフェスの設定</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer を MMS サービスプロバイダーに接続する方法と、MMS チャネルサーフェスを作成する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1765310600192" alt="Journey Optimizer での RCS の設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Journey Optimizer での RCS の設定">Journey Optimizer での RCS の設定</a>
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

## プライバシー法およびプラットフォームガイドラインへのコンプライアンスを確保します。

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables
{cta = Watch}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement consent for Platform Mobile SDK implementations">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" title="Platform Mobile SDK実装に対する同意の実装" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent./media_12356d2400b5ad641e8356a6883441b38a129c968.png?width=400&format=png&optimize=medium" alt="Platform Mobile SDK実装に対する同意の実装"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" target="_blank" rel="referrer" title="Platform Mobile SDK実装に対する同意の実装">Platform Mobile SDK実装に対する同意の実装 </a>
                    </p>
                    <p class="is-size-6">モバイルアプリで同意を実装する方法を説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Adobe Journey Optimizer のプライバシー機能" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Adobe Journey Optimizer のプライバシー機能"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Adobe Journey Optimizer のプライバシー機能">Adobe Journey Optimizerのプライバシー機能 </a>
                    </p>
                    <p class="is-size-6">プライバシーリクエストの処理、ユーザー操作の監査、同意の管理、ガバナンスルールの適用、顧客管理キーなどの高度なセキュリティオプションの活用の方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="データガバナンスフレームワークの概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1765310600883" alt="データガバナンスフレームワークの概要"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="データガバナンスフレームワークの概要">データガバナンスフレームワークの概要</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Platform のガバナンス機能について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="ラベルを使用したデータの分類" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1765310600887" alt="ラベルを使用したデータの分類"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="ラベルを使用したデータの分類">ラベルを使用したデータの分類</a>
                    </p>
                    <p class="is-size-6">スキーマとデータセットにラベルを適用する方法を説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="データ使用ポリシーの作成" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1765310600676" alt="データ使用ポリシーの作成"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="データ使用ポリシーの作成">データ使用ポリシーの作成</a>
                    </p>
                    <p class="is-size-6">データ使用ポリシーを作成および管理する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->


## 実装の一般的な落とし穴と回避方法

モバイルに関する問題のほとんどは、Journey Optimizerのジャーニーやキャンペーン自体ではなく **0}SDKまたはデータ収集の設定 } に起因します。**&#x200B;次の表を使用して問題の原因を特定し、該当するセクションを展開して詳細を確認してください。

### 落とし穴の概要

| # | 問題/症状 | よくある落とし穴 | 一目で修正 |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | ガイド付きチャネルのセットアップに失敗。トラフィックがない、または少ない | [SDKのバージョンまたは拡張機能が揃っていない ](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | SDK/拡張機能のバージョンを更新し、Assuranceで検証する |
| 2 | バッチのトラッキングが失敗し、AEPでエラーが発生する | [ データストリームまたはデータセットの設定の誤り ](#2-misconfigured-datastreams-or-datasets) | イベントデータセットへのイベントのマッピングとプロファイルデータセットへのプロファイル |
| 3 | ジャーニーが起動せず、パーソナライゼーションが奇妙になる | [ID または同意が見つからない/一貫性がない ](#3-missing-or-inconsistent-identity-and-consent) | Edgeの ID および同意の実装、Assuranceでの検証 |
| 4 | プッシュ配信がないか、レポートで開いている | [ プッシュトークンの登録またはトラッキングが破損している ](#4-push-token-registration-and-tracking-not-wired-correctly) | SDKによるトークン登録とインタラクショントラッキングの修正 |
| 5 | アクティブなキャンペーンにもかかわらず、アプリ内インプレッションがありません | [ アプリ内メッセージまたはコンテンツカードが表示されない ](#5-in-app-messages-or-content-cards-not-displaying) | メッセージの拡張機能、トリガーおよびAssuranceの決定応答を確認する |

### 落とし穴ごとの詳細なガイダンス

症状に合った落とし穴を開けて、チェック対象と修正方法を確認します。

+++ &#x200B;1. チャネル要件に合致していないSDKのバージョンおよび拡張機能
**何に気づくでしょう**

- プッシュまたはアプリ内アクティビティがデバイスに到達しません。
- ガイド付きチャネル設定またはチャネル検証が失敗する。
- Assuranceで、Journey Optimizer、Edgeまたは ID 拡張機能が見つからない問題を示します。

**確認対象**

- ガイド付きチャネルのセットアップに必要な **Mobile Core** および **Journey Optimizer** 拡張機能の最小バージョンを使用していますか？
- **Assurance** の拡張機能とイベントで、次の操作を行います。
   - 必要な拡張機能が読み込まれていますか？
   - イベントはEdge Networkに送信され、確認されていますか？

**修正方法**

- サポートされている Mobile SDKおよびJourney Optimizer拡張機能のバージョンにアップグレードします。
- アプリを再構築し、Assuranceに再接続して、Guided Channel Setup を再実行します。

関連項目：[ モバイルと Web の設定 ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config){target="_blank"}

+++

+++ 2.設定が正しくないデータストリームまたはデータセット
**何に気づくでしょう**

- Platform データセットでイベントまたはプッシュトラッキングバッチが失敗する。
- データ取り込みエラー（例：「アップデートはイベントではサポートされていません」）。
- プッシュまたはアプリ内レポートには、トラッキングがほとんど、またはまったく表示されません。

**確認対象**

- Journey Optimizerのトラッキング用に作成された **システムスキーマまたはデータセット** に変更はありましたか？
- **データストリーム** で、
   - エクスペリエンスイベントは **イベントデータセット** にマッピングされていますか。
   - プロファイル属性は **プロファイルデータセット** にマッピングされていますか。

**修正方法**

- AJOで作成されたシステムデータセット/スキーマは編集しないでください。
- データストリームマッピングを修正します（イベント→イベントデータセット、プロファイル→プロファイルデータセット）。
- アドホックな変更の代わりに、ガイド付きチャネル設定またはドキュメント化されたデータストリーム手順を優先します。

関連項目：[Adobe Journey Optimizerにおけるプッシュ通知フロー ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ &#x200B;3. ID と同意が欠落している、または一貫性がない
**何に気づくでしょう**

- ジャーニーが、アプリユーザーの想定どおりにトリガーされません。
- Personalizationが他のチャネルでのユーザーの行動と一致しません。
- イベントはExperience Platformに表示されますが、プロファイルが断片化されているように見えます。

**確認対象**

- **Edge Networkの ID** が実装されており、安定したプライマリ ID （例えば、ログイン ID）を送信しているかどうか。
- 環境設定が変更されると、**Edge Networkの同意** が実装および更新されますか？
- **Assurance** で：
   - アウトバウンドイベントには同意値が含まれていますか？
   - ECID とプライマリ ID は一貫して含まれていますか？

**修正方法**

- アプリに **Edge Networkの ID** を実装または修正します。
- **Edge Networkに対する同意** を実装し、アプリの同意 UI に接続します。
- 関連するすべてのイベントに ID と同意が表示されるまで、Assuranceで再テストします。

[Platform Mobile SDK実装の同意の実装 ](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent){target="_blank"} を参照してください。

+++

+++ &#x200B;4. プッシュトークンの登録とトラッキングが正しく接続されていない
**何に気づくでしょう**

- キャンペーンやジャーニーが実行されていても、ユーザーにプッシュ通知が届くことはありません。
- プッシュレポートには、開封数、解除数またはインタラクション数は表示されません。

**確認対象**

- アプリはプッシュトークンをJourney Optimizer拡張機能に登録しますか？
   - 初回インストール時
   - アプリを更新するたびに、
   - OS がトークンを更新するたびに、
- ユーザーが通知を開いたり閉じたりすると、Assuranceにトラッキングイベントが表示されますか。

**修正方法**

- 次のコードを追加または修正します。
   - 作成または更新されるたびに、Journey Optimizer モバイル拡張機能を介してトークンを登録します。
   - Mobile SDKを介してプッシュインタラクションイベント（オープン、解除、カスタムアクション）を送信します。
- Assuranceを使用して、登録イベントとトラッキングイベントが期待どおりに実行されていることを確認します。

関連項目：[Adobe Journey Optimizerにおけるプッシュ通知フロー ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ &#x200B;5. アプリ内メッセージまたはコンテンツカードが表示されない
**何に気づくでしょう**

- アクティブなキャンペーンやジャーニーにもかかわらず、アプリ内メッセージやコンテンツカードが表示されることはありません。
- レポートにインプレッション数が 0 と表示される。

**確認対象**

- **Journey Optimizer モバイルメッセージ/アプリ内拡張機能** および **Messaging SDK** は、アプリにインストールして登録していますか。
- **tags** 設定で以下を行います。
   - トリガーが正しいイベント（画面ビューやカスタムイベントなど）に対してリクエストするルールはありますか？
- **Assurance** で：
   - これらのイベントが発生した場合、アプリ内決定リクエストまたはコンテンツカード決定リクエストが送信されますか。
   - Edge Networkから応答が返ってくることが確認できますか。

**修正方法**

- 必要なメッセージング拡張機能をインストールして登録します。
- ターゲットイベント（画面、カスタムイベント）に関する決定をトリガーにするルールを追加または修正します。
- コンテンツカードの場合は、次を確認します。
   - Messaging SDK API を使用してカードを取得します。
   - UI でレンダリングします。
   - SDKを介してインタラクションをトラッキングします。

参照：
- [ アプリ内メッセージの作成と送信 ](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp){target="_blank"}
- [Mobile SDKでのコンテンツカードのサポートの設定 ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp){target="_blank"}

+++

## その他のリソース

- [ モバイルでの CDN ベースのクライアントサイドパーソナライゼーション（ODD）の使用によるパーソナライゼーションの高速化（ブログ） ](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626){target="_blank"}
- [ 次レベルのモバイルアプリのエンゲージメントと成長の秘訣（サミットセッション） ](https://business.adobe.com/summit/2025/sessions/the-secret-to-nextlevel-mobile-app-engagement-s603.html)
