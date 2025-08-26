---
title: の設定と起動
description: Adobe Journey Optimizer（AJO）およびAdobe Experience Platform（AEP）でモバイルチャネルを設定し、モバイルアプリと統合し、マーケティングキャンペーンを確実に実行できるようにします。
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: b7d014b3ac6373b957eb5fce11661ec39689446b
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 55%

---

# の設定と起動

Journey OptimizerとExperience Platformでモバイルチャネルを設定し、モバイルアプリと統合し、マーケティングキャンペーンを確実に実行できるようにします。

>[!NOTE]
>
>Journey OptimizerとExperience Platformを初めて使用する場合は、次のプレイリストを見て、中心概念を理解してください。
>
>* [ジャーニー管理者およびマネージャー向けJourney Optimizerの概要 ](https://experienceleague.adobe.com/ja/playlists/journey-optimizer-getting-started-for-journey-administrators-and-managers)
>* [Journey Optimizerをジャーニー管理者用に設定する ](https://experienceleague.adobe.com/ja/playlists/journey-optimizer-configure-journey-optimizer-for-administrators)
>* [ データエンジニア向けJourney Optimizerでのデータの設定と管理 ](https://experienceleague.adobe.com/ja/playlists/journey-optimizer-configure-and-manage-data-for-data-engineers)


## Adobe Journey Optimizerのモバイル機能

>[!VIDEO](https://video.tv.adobe.com/v/344617?quality=12&learn=on&captions=jpn){transcript=true}

## Mobile SDKとアプリの設定

チャネルごとに分類？

### 前提条件

次の点を確認します。

* 組織用にプロビジョニングされたAdobe Journey Optimizer（AJO）。
* Adobe Experience Platform（AEP）SDKの資格情報。
* AJOでの設定用の管理者権限。
* アプリのソースコードにアクセスします。
* アプリでは、必要な OS レベルの機能（プッシュ権限、通知サービス拡張機能など）が有効になっています

### モバイルプロパティの設定

チュートリアルへのリンク


## Adobe Journey Optimizer Channel Configuration

ガイド付きチャネル設定機能を使用してチャネルで **モバイルチャネル** を設定する方法を説明します。 **WhatsApp チャネル** を設定する方法を理解します。

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Guided channel setup">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" title="ガイド付きチャネル設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3433053/?format=jpeg&nocache=1755888511558" alt="ガイド付きチャネル設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="ガイド付きチャネル設定">ガイド付きチャネル設定</a>
                    </p>
                    <p class="is-size-6">ガイド付きチャネル設定により、Experience Platform、Journey Optimizer、データ収集全体にわたって必要なリソースを使用して web チャネルとモバイルチャネルを迅速に設定および検証できるので、マーケティングチームはキャンペーンとジャーニーの作成を開始できます。サンプルの iOS モバイルマーケティングアプリでプッシュチャネル通知を設定および検証する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="WhatsApp チャネルの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470269/?format=jpeg&nocache=1755888511569&captions=jpn" alt="WhatsApp チャネルの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="WhatsApp チャネルの設定">WhatsApp チャネルのセットアップ </a>
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


標準のプロバイダー（Twilio、Synch、Infobip）を使用して **SMS/MMS/RCS チャネル** を設定する方法、またはカスタム SMS プロバイダーを使用する方法を説明します。

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="SMS API 資格情報とチャネルサーフェスの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3418546?format=jpeg&nocache=1755888512031&captions=jpn" alt="SMS API 資格情報とチャネルサーフェスの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="SMS API 資格情報とチャネルサーフェスの設定">SMS API 資格情報とチャネルサーフェスの設定 </a>
                    </p>
                    <p class="is-size-6">Journey Optimizer を SMS サービスプロバイダーに接続する方法と SMS チャネルサーフェスを作成する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1755888512068" alt="カスタム SMS プロバイダーの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="カスタム SMS プロバイダーの設定">カスタム SMS プロバイダーの設定</a>
                    </p>
                    <p class="is-size-6">Adobe Journey Optimizer で Sinch、Twilio、Infobip 以外の SMS プロバイダーを設定する方法、インバウンドメッセージ用の API 資格情報と Webhook を設定する方法、オプトイン／オプトアウトキーワードを管理する方法、ネイティブツールとカスタムペイロードを使用してパーソナライズされた SMS キャンペーンを開始する方法について説明します。</p>
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
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="MMS API 資格情報とチャネルサーフェスの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3438047/?format=jpeg&nocache=1755888512061&captions=jpn" alt="MMS API 資格情報とチャネルサーフェスの設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="MMS API 資格情報とチャネルサーフェスの設定">MMS API 資格情報とチャネルサーフェスの設定</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer を MMS サービスプロバイダーに接続する方法と、MMS チャネルサーフェスを作成する方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464756/?format=jpeg&nocache=1755888512073&captions=jpn" alt="Journey Optimizer での RCS の設定"
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

## ブログ投稿

* [ モバイルでの CDN ベースのクライアントサイドパーソナライゼーション（ODD）の使用によるパーソナライゼーションの高速化。](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626?profile.language=ja)
* [Adobe Experience CloudのMobile Activation](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595?profile.language=ja)

## プライバシー法およびプラットフォームガイドラインへのコンプライアンスを確保します。

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables{cta = Watch}
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Adobe Journey Optimizerのプライバシー機能" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Adobe Journey Optimizerのプライバシー機能"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Adobe Journey Optimizerのプライバシー機能">Adobe Journey Optimizerのプライバシー機能 </a>
                    </p>
                    <p class="is-size-6">プライバシーリクエストの処理、ユーザー操作の監査、同意の管理、ガバナンスルールの適用、顧客管理キーなどの高度なセキュリティオプションの活用の方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold"> 詳細情報 </span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="データガバナンスフレームワークの概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/34106/?format=jpeg&nocache=1755888512557&captions=jpn" alt="データガバナンスフレームワークの概要"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3422791?format=jpeg&nocache=1755888512540&captions=jpn" alt="ラベルを使用したデータの分類"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/37133/?format=jpeg&nocache=1755888512550&captions=jpn" alt="データ使用ポリシーの作成"
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
