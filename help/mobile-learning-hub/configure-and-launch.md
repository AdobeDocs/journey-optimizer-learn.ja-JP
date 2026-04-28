---
title: 設定と起動
description: Adobe Journey Optimizer（AJO）およびAdobe Experience Platform（AEP）でモバイルチャネルを設定し、モバイルアプリと統合して、マーケティングキャンペーンを実行する準備を整えます。
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: false
index: true
jira: KT-19869
last-substantial-update: 2025-12-18T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: 3917e11cdf8c0450c19ce653a0964f6dc9da6a3c
workflow-type: tm+mt
source-wordcount: '2976'
ht-degree: 24%

---


# 設定と起動

**administrators**&#x200B;および&#x200B;**モバイルアプリ開発者**&#x200B;の場合、この節では、Adobe Journey Optimizerでモバイルチャネルとweb チャネルを設定および起動する方法について説明します。 前提条件、権限、プラットフォームサポートについて説明し、アプリ固有の設定の作成を順を追って説明します。

>[!IMPORTANT]
>
> Journey OptimizerおよびExperience Platformを初めて使用する場合は、Journey Optimizerのコアコンセプトであるデータ管理について、次のコースを受講してください。[Adobe Journey Optimizerのインテリジェントジャーニーアクティベーションのためのデータの設計](https://experienceleague.adobe.com/en/courses/ajo-engineer-data-for-intelligent-journey-activation){target="_blank"}
>

## Adobe Journey Optimizerのモバイル機能

プッシュメッセージ、アプリ内メッセージ、コンテンツパーソナライゼーションなど、Adobe Journey Optimizerが開発者、マーケター、製品部門向けに提供するモバイル機能をご確認ください。

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## チャネル設定

### モバイルプッシュとアプリ内

Journey Optimizerでのモバイル実装は、アプリでの&#x200B;**Adobe Experience Platform Mobile SDK**&#x200B;統合から始まります。 SDKは、Adobe Experience Platform（AEP）およびそのアプリケーション（Adobe Journey Optimizer（AJO）など）とのデータ収集とインタラクションに不可欠です。

#### モバイルSDKとは：

モバイル SDK:

* アプリイベント（画面表示、タップ、購入、ライフサイクルイベントなど）を収集します。 **Adobe Experience Platform Edge Network**&#x200B;に送信します。
* **ID**&#x200B;と&#x200B;**同意**&#x200B;を管理するので、Journey Optimizerでは顧客プロファイルを安全に構築して使用できます。
* **プッシュトークン**&#x200B;を登録および更新し、**プッシュおよびアプリ内トラッキングイベント**&#x200B;をAdobe Experience Platformに送信します。
* Integrates with the **[Journey Optimizer mobile extension](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer)** so messages can be delivered, rendered, and measured end‑to‑end.

Mobile SDKをアプリに統合しないと、Journey Optimizerは次の信頼性を維持できません。

* モバイルプッシュ通知とアプリ内メッセージを配信して追跡できます。
* コンテンツカードのレンダリングと追跡：
* アプリ内でリアルタイムの行動を利用して、カスタマージャーニーをトリガーし、エクスペリエンスをパーソナライズできます。

#### 新規実装のためのガイド付きチャネル設定

新しいモバイルアプリ内およびプッシュ通知の実装では、ガイド付きチャネル設定が推奨されます。 設定が正しくないデータストリームや拡張機能が欠落するリスクを軽減し、AssuranceによるSDKの検証を順を追って進めることができます。

>[!PREREQUISITES]
>
>次を持っていることを確認します。
>
> * 組織にプロビジョニングされた&#x200B;**Adobe Journey Optimizer** （AJO）。
> * [&#x200B; データ収集とJourney Optimizer権限](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config#:~:text=Required%20permissions)を持つAdobe Experience Platform アクセス。
> * チャネルと設定の設定に関するAJOの管理者権限。
> * モバイルアプリのソースコード（iOS、Android、クロスプラットフォームフレームワーク）へのアクセス。
> * アプリで必要なOS レベルの機能（プッシュ権限、通知サービス拡張機能、バックグラウンドモードなど）が有効になっています。
> * 既存の設定オプションを使用している場合は、[現在のAdobe Experience Platform Mobile SDK バージョン &#x200B;](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"}を使用していることを確認してください


>[!VIDEO](https://video.tv.adobe.com/v/3433053/?learn=on)

詳しくは、[&#x200B; ガイド付きチャネル設定の基本を学ぶ](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config.html?lang=ja){target="_blank"}を参照してください


#### プッシュチャネルの手動設定

次のガイドでは、データフローの把握、FirebaseやApple Push Notification Service （APN）などのサービスとの統合、モバイルアプリの設定、通知のテストなど、プッシュ通知を効果的に手動で設定および使用するために必要なすべての手順を説明します。

<!--
CARDS
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
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" title="プッシュ通知のデータフローとコンポーネント"> プッシュ通知データフローとコンポーネント </a>
                    </p>
                    <p class="is-size-6">Journey Optimizerでプッシュ通知に関する主要なサービスとワークフローを設定し、理解する方法を説明します。</p>
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
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" title="プッシュ通知の設定"> プッシュ通知設定</a>
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
                    <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" title="モバイルアプリでのAdobe Experience Cloudの実装チュートリアル" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="モバイルアプリでのAdobe Experience Cloudの実装チュートリアル"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="モバイルアプリでのAdobe Experience Cloudの実装チュートリアル">モバイルアプリでの Adobe Experience Cloud の実装のチュートリアル</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Cloud モバイルアプリケーションの実装方法について説明します。 このチュートリアルでは、サンプル SwiftまたはAndroid アプリでのExperience Cloud アプリケーションの実装について説明します。</p>
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


<!--
CARDS
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
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" title="Adobe Experience Platform Mobile SDKを入手する" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Mobile SDKを入手する"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDKを入手する">Adobe Experience Platform Mobile SDKを入手</a>
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
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" title="Adobe Experience Platform Assuranceの概要">Adobe Experience Platform Assuranceの概要</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Platform Assuranceモバイル拡張機能の概要。</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Mobile SDKの準備状況チェックリスト

アプリをマーケターに渡す前に、**[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/){target="_blank"}**&#x200B;で次のことを確認してください。

>[!SUCCESS]
> 
> [ ] Core SDK + Journey Optimizer拡張機能が読み込まれました，\
> [ ] イベントが正しいデータストリームとデータセットに流れています。\
> [ ]IDと同意は、すべての主要なイベントに存在します。\
> [ ]件のプッシュトークンとインタラクションが追跡され、\
> [ ]少なくとも1つのテスト アプリ内メッセージまたはコンテンツカードが表示され、インプレッションとして記録されています。


### コンテンツカード

<!--
CARDS
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
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" title="Mobile SDK でのコンテンツカードのサポートの設定">Mobile SDKでのコンテンツカードのサポートの設定</a>
                    </p>
                    <p class="is-size-6">Messaging SDKを使用して、モバイルアプリケーションにコンテンツカードを統合する方法について説明します。</p>
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

**WhatsApp チャネル**&#x200B;の設定方法について説明します。

<!--
CARDS
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

標準プロバイダー（Twilio、SynchまたはInfobip）を使用するか、カスタム SMS プロバイダーを使用して&#x200B;**SMS/MMS/RCS チャネル**&#x200B;を設定します。

<!--
CARDS
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
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="SMS API 資格情報とチャネルサーフェスの設定">SMS API資格情報とチャネルサーフェスの設定</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer を SMS サービスプロバイダーに接続する方法と SMS チャネルサーフェスを作成する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
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
                    <p class="is-size-6">Journey Optimizerでカスタム SMS プロバイダーを設定する方法、API資格情報とwebhookを設定する方法、オプトイン/オプトアウトキーワードを管理する方法、パーソナライズされたキャンペーンを開始する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
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
                    <p class="is-size-6">カスタム SMS プロバイダーを使用して、ブランド化されたインタラクティブな RCS メッセージを Adobe Journey Optimizer で設定および送信する方法について説明します。 このチュートリアルでは、ネイティブメッセージアプリ内で、API 資格情報、Webhook、チャネル設定を指定し、リッチでパーソナライズされたメッセージエクスペリエンスを提供するジャーニーを作成するすべての手順について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## プライバシー法とプラットフォームガイドラインを遵守しましょう。

<!--
CARDS
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
                    <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" title="Platform Mobile SDKの実装に対する同意の実装" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent./media_12356d2400b5ad641e8356a6883441b38a129c968.png?width=400&format=png&optimize=medium" alt="Platform Mobile SDKの実装に対する同意の実装"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" target="_blank" rel="referrer" title="Platform Mobile SDKの実装に対する同意の実装">Platform Mobile SDKの実装に対する同意の実装</a>
                    </p>
                    <p class="is-size-6">モバイルアプリに同意を実装する方法について説明します。</p>
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
                        Adobe Journey Optimizerの<a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Adobe Journey Optimizer のプライバシー機能"> プライバシー機能</a>
                    </p>
                    <p class="is-size-6">プライバシー要求の処理、ユーザーのアクションの監査、同意の管理、ガバナンスルールの適用、Customer Managed Keysなどの高度なセキュリティオプションの活用方法について説明します。</p>
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">監視</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->


## 一般的な実装の落とし穴とその回避方法

ほとんどのモバイルの問題は、**SDKまたはデータ収集設定**&#x200B;に起因するもので、Journey Optimizer ジャーニーやキャンペーン自体には発生しません。 Use the table below to identify what&#39;s going wrong, then expand the corresponding section for details.

### Pitfalls at a glance

| # | Issue / symptom | Common pitfall | Fix at a glance |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | Guided Channel Setup fails; no or low traffic | [SDK versions or extensions not aligned](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Update SDK/extension versions; validate in Assurance |
| 2 | Tracking batches fail; errors in AEP | [Datastreams or datasets misconfigured](#2-misconfigured-datastreams-or-datasets) | Map events to event dataset &amp; profiles to profile dataset |
| 3 | Journeys don&#39;t fire; odd personalization | [Identity or consent missing / inconsistent](#3-missing-or-inconsistent-identity-and-consent) | Implement Edge Identity &amp; Consent; verify in Assurance |
| 4 | No push delivery or opens in reports | [Push token registration or tracking broken](#4-push-token-registration-and-tracking-not-wired-correctly) | Fix token registration &amp; interaction tracking via SDK |
| 5 | No in‑app impressions despite active campaigns | [In‑app messages or content cards not displaying](#5-in-app-messages-or-content-cards-not-displaying) | Check messaging extensions, triggers, and Assurance decision responses |

### Detailed guidance per pitfall

Open the pitfall that matches your symptoms to see what to check and how to fix it.

+++ 1. SDK versions and extensions not aligned with channel requirements
**What you&#39;ll notice**

* Push or in‑app activities do not reach the device.
* Guided Channel Setup or channel validation fails.
* Assurance shows missing Journey Optimizer, Edge, or Identity extensions.

**What to check**

* Are you using the minimum **Mobile Core** and **Journey Optimizer** extension versions required by Guided Channel Setup?
* In **Assurance**, under extensions and events:
   * Do you see the expected extensions loaded?
   * Are events being sent to the Edge Network and acknowledged?

**How to fix**

* Upgrade to the supported Mobile SDK and Journey Optimizer extension versions.
* Rebuild the app, reconnect to Assurance, and re‑run Guided Channel Setup.

See: [Set up mobile and web](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config){target="_blank"}

+++

+++ 2. Misconfigured datastreams or datasets
**What you&#39;ll notice**

* Events or push tracking batches fail in Platform datasets.
* Data ingestion errors (for example, &quot;Updates are not supported for events&quot;).
* Push or in‑app reports show little or no tracking.

**What to check**

* Did anyone change **system schemas or datasets** created for Journey Optimizer tracking?
* In your **datastream**:
   * Are experience events mapped to an **event dataset**?
   * Are profile attributes mapped to a **profile dataset**?

**How to fix**

* Do not edit system datasets/schemas created by AJO.
* Correct the datastream mapping (events → event dataset, profiles → profile dataset).
* Prefer Guided Channel Setup or the documented datastream steps instead of ad‑hoc changes.

Adobe Journey Optimizerの[&#x200B; プッシュ通知フロー](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}を参照してください。

+++

+++ &#x200B;3. IDと同意が欠落している、または一貫性がない
**お知らせします**

* ジャーニーが、アプリユーザーに対して期待どおりにトリガーされない。
* Personalizationが、ほかのチャネルでの利用者の行動と一致していない。
* Experience Platformにはイベントが表示されますが、プロファイルは断片的に見えます。

**チェック対象**

* Edge Network **の** IDは実装され、安定したプライマリ ID （ログイン IDなど）を送信しますか？
* 環境設定が変更されたときに&#x200B;**Edge Networkの同意が実装され、更新されますか？**
* **Assurance**&#x200B;で：
   * アウトバウンドイベントには同意値が含まれますか？
   * ECIDとプライマリ IDは一貫して含まれていますか？

**解決方法**

* アプリにEdge Network **の** IDを実装または修正します。
* Edge Network **の**&#x200B;同意管理を実装し、アプリの同意管理UIに接続します。
* IDと同意がすべての関連イベントに表示されるまで、Assuranceでリストアします。

参照：[Platform Mobile SDKの実装に対する同意の実装](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent){target="_blank"}

+++

+++ &#x200B;4. プッシュトークンの登録とトラッキングが正しく接続されていない
**お知らせします**

* キャンペーンやジャーニーが実行されていても、ユーザーはプッシュ通知を受け取ることはありません。
* プッシュレポートでは、開封数、解約数、インタラクション数は表示されません。

**チェック対象**

* アプリは、Journey Optimizer拡張機能にプッシュトークンを登録します。
   * 最初のインストール時に？
   * アプリをアップデートするたびに？
   * Whenever the OS refreshes the token?
* When a user opens or dismisses a notification, do you see tracking events in Assurance?

**解決方法**

* Add or correct the code that:
   * Registers the token via the Journey Optimizer mobile extension whenever it is created or refreshed.
   * Sends push interaction events (open, dismiss, custom actions) via the Mobile SDK.
* Use Assurance to confirm registration and tracking events are firing as expected.

Adobe Journey Optimizerの[&#x200B; プッシュ通知フロー](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}を参照してください。

+++

+++ 5. In‑app messages or content cards not displaying
**お知らせします**

* In‑app messages or content cards never appear, despite active campaigns or journeys.
* Reporting shows 0 impressions.

**チェック対象**

* Are the **Journey Optimizer mobile messaging / in‑app extension** and **Messaging SDK** installed and registered in the app?
* In your **tags** configuration:
   * Do you have rules that trigger requests on the correct events (for example, screen views or custom events)?
* **Assurance**&#x200B;で：
   * When those events fire, do you see in‑app or content‑card decision requests going out?
   * Do you see responses coming back from the Edge Network?

**解決方法**

* Install and register the required messaging extensions.
* Add or correct rules that trigger decisions on your target events (screens, custom events).
* For content cards, ensure you:
   * Fetch cards via the Messaging SDK APIs.
   * Render them in your UI.
   * Track interactions back via the SDK.

参照：
* [Create and send in‑app messages](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp){target="_blank"}
* [Mobile SDK でのコンテンツカードのサポートの設定](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp){target="_blank"}

+++

## その他のリソース

* [Using CDN based client side personalization (ODD) on mobile for faster personalizations (Blog)](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626){target="_blank"}
* [The Secret to Next-Level Mobile App Engagement and Growth (Summit Session)](https://business.adobe.com/summit/2025/sessions/the-secret-to-nextlevel-mobile-app-engagement-s603.html)
