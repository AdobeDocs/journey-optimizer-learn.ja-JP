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
source-git-commit: ca55acb4ca76ca948243eab10faa7c5c15adca91
workflow-type: tm+mt
source-wordcount: '2471'
ht-degree: 17%

---


# の設定と起動

Adobe Journey OptimizerとAdobe Experience Platformでモバイルチャネルを設定し、モバイルアプリと統合し、マーケティングキャンペーンを確実に実行できるようにします。

&#x200B;> [!NOTE]
> Journey OptimizerおよびExperience Platformを初めて使用する場合は、次のコースを受講して、中心概念を理解してください。
> - [Adobe Journey Optimizerの設定と管理 &#x200B;](https://experienceleague.adobe.com/ja/courses/ajo-configure-and-administrate-ajo-environment)
>*このコースでは、ユーザーの役割、権限、サンドボックス、メールチャネルなど、Journey Optimizer環境を設定および管理し、効率的で安全な操作を行う方法について説明します。*
> - [Adobe Journey Optimizerのインテリジェントジャーニーアクティベーションのエンジニアリングデータ &#x200B;](https://experienceleague.adobe.com/ja/courses/ajo-engineer-data-for-intelligent-journey-activation)
>*このコースでは、Experience Platformを使用して、Journey Optimizerのリアルタイム顧客プロファイルデータを設定および管理する方法について説明します。 パーソナライズされたカスタマージャーニー用に統合プロファイルを作成するためのデータモデリング、ID マッピングおよびデータ取り込みについて説明します。*


## Adobe Journey Optimizerのモバイル機能

プッシュメッセージ、アプリ内メッセージ、コンテンツのパーソナライゼーションなど、Adobe Journey Optimizerが開発者、マーケターおよび製品チームに提供するモバイル機能について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## Mobile SDKとアプリの設定

Journey Optimizerでのモバイル実装は、アプリ内の **Adobe Experience Platform Mobile SDK** 統合から始まります。 SDK は、データ収集や、Adobe Experience Platform（AEP）およびAdobe Journey Optimizer（AJO）などのアプリケーションとのインタラクションに不可欠です。

モバイルSDK:

- アプリイベント（画面ビュー、タップ、購入、ライフサイクルイベントなど）を収集し、**Adobe Experience Platform Edge Network** に送信します。
- **ID** および **同意** を管理して、Journey Optimizerが顧客プロファイルを安全に作成して使用できるようにします。
- **プッシュトークン** を登録および更新し、**プッシュイベントおよびアプリ内トラッキングイベント** をAdobe Experience Platformに返します。
- **Journey Optimizer モバイル拡張機能** （プッシュ、アプリ内、コンテンツカード、決定）と統合するので、メッセージをエンドツーエンドで配信、レンダリング、測定できます。

モバイル SDKがアプリに統合されていない場合、Journey Optimizerでは次の点で信頼性に優れています。

- モバイルプッシュおよびアプリ内メッセージの配信とトラッキング。
- コンテンツカードのレンダリングとトラック
- リアルタイムのアプリ内動作を使用して、ジャーニーをトリガーに設定し、エクスペリエンスをパーソナライズします。


>[!PREREQUISITES]
>
>次の点を確認します。
>
> - 組織用にプロビジョニングされたAdobe Journey Optimizer（AJO）。
> - データ収集およびJourney Optimizer権限を持つAdobe Experience Platform アクセス。
> - チャネルおよび設定セットアップの管理者権限がAJOにある。
> - モバイルアプリのソースコード（iOS、Androidまたはクロスプラットフォームフレームワーク）にアクセスします。
>- アプリでは、必要な OS レベルの機能（プッシュ権限、通知サービス拡張機能、バックグラウンドモードなど）が有効になっています。


### Journey Optimizerに必須の Mobile SDK コンポーネント

Journey Optimizer モバイルチャネル（プッシュ、アプリ内、コンテンツカード、コードベースのエクスペリエンス）を使用するには、モバイルアプリに一連の **コア** および **チャネル固有の** 拡張機能をインストールして設定する必要があります。

>[!BEGINTABS]

>[!TAB  コア ]

#### コア拡張機能（すべてのモバイルユースケースで必要）

| 目的 | 拡張機能の例（iOS/Android） | メモ |
|----------------------|-----------------------------------------------|-------|
| イベントハブとサービス | Mobile Core/AEP Core、AEP サービス | 他のすべての拡張機能の基盤。 イベント ハブ、ネットワーク、ストレージ、および共有状態を提供します。 |
| Edge Network | Adobe Experience Platform Edge Network | アプリイベントをAdobe Experience Platform Edge Networkに送信します。 |
| ID | Edge Networkの ID | プロファイルおよびセグメント化に使用する ECID およびその他の ID を管理します。 |
| 同意 | Edge Networkの同意 | ユーザー同意環境設定を収集して適用します。 |
| Assurance | Adobe Experience Platform Assurance | SDKとチャネル設定の検証とデバッグをエンドツーエンドで行うために使用します。 |

>[!TAB  チャネル固有 ]

#### Journey Optimizerのチャネル固有の拡張機能

| チャネル /機能 | その他のキー拡張機能（コアの上） | それらが有効にするもの |
|------------------------|---------------------------------------------------------------------|------------------|
| プッシュ通知 | Journey Optimizer モバイル拡張機能（プッシュ） | プッシュトークンの登録と更新、プッシュトラッキングイベントの送信、AJO プッシュ設定への接続を行います。 |
| アプリ内メッセージ | Journey Optimizer Mobile 拡張機能（アプリ内）、メッセージング UI コンポーネント | コンテキスト内のアプリ内メッセージを取得して表示し、インプレッションとインタラクションイベントを送信します。 |
| コンテンツカード | コンテンツカードをサポートするメッセージング SDK | コンテンツカードを取得、レンダリング、追跡して、Journey Optimizerの正確なレポートを生成します。 |
| コードベースのエクスペリエンス | Journey Optimizer/Decisioning Extensions またはEdge Server API | アプリ内の特定の「サーフェス」に関する決定を取得します。アプリがコンテンツのレンダリング方法を制御します。 |

>[!ENDTABS]

#### モバイルタグのプロパティと設定

これらの拡張機能は、AEP Data Collection （タグ）の **[モバイルタグプロパティ &#x200B;](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)** で設定します。 このプロパティは次の項目を制御します。

- インストールされている Mobile SDK拡張機能。
- Edge Networkに呼び出すアプリトリガー内のイベント。
- データを XDM にマッピングし、Adobe ソリューション（Journey Optimizer、Analytics など）に転送する方法。

このモバイルプロパティを作成して [&#x200B; 手動で設定 &#x200B;](https://experienceleague.adobe.com/ja/docs/platform-learn/data-collection/tags/create-a-property) することも、アプリ内モバイルおよびプッシュの場合は **[ガイド付きチャネル設定 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** を使用して、iOSおよびAndroidに必要なタグプロパティ、データストリーム、チャネル設定を自動作成できます。

> **ヒント**\
> 新規実装の場合、**[ガイド付きチャネル設定 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** は出発点として推奨されます。 これにより、データストリームの設定ミスや拡張機能の欠落のリスクが軽減され、Assuranceを使用したSDKの検証について順を追って説明します。

#### モバイルSDKの基本を学ぶ：

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/platform-learn/data-collection/mobile-sdk/overview
    {description = Learn how Adobe Experience Platform Mobile SDK powers end-to-end engagement in your mobile applications.}
* https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/overview
* https://experienceleague.adobe.com/ja/docs/mobile
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/platform-learn/data-collection/mobile-sdk/overview" title="Adobe Experience Platform Mobile SDKの概要" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/28948?format=jpeg&nocache=1763594622398" alt="Adobe Experience Platform Mobile SDKの概要"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDKの概要">Adobe Experience Platform Mobile SDKの概要 </a>
                    </p>
                    <p class="is-size-6">Adobe Experience Platform Mobile SDKが、モバイルアプリケーションでのエンドツーエンドのエンゲージメントを強化する方法を説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">所要時間</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/overview" title="モバイルアプリでのAdobe Experience Cloudの実装のチュートリアル" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="モバイルアプリでのAdobe Experience Cloudの実装のチュートリアル"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="モバイルアプリでのAdobe Experience Cloudの実装のチュートリアル">モバイルアプリでの Adobe Experience Cloud の実装のチュートリアル</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Cloud モバイルアプリケーションの実装方法を説明します。 このチュートリアルでは、サンプルの Swift またはAndroid アプリでのExperience Cloud アプリケーションの実装について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK Documentation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/mobile" title="Adobe Experience Platform Mobile SDK ドキュメント" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://cdn.experienceleague.adobe.com/thumb/exl-cards/documentation.png" alt="Adobe Experience Platform Mobile SDK ドキュメント"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/mobile" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDK ドキュメント">Adobe Experience Platform Mobile SDK ドキュメント </a>
                    </p>
                    <p class="is-size-6">Experience Platform Mobile SDK に関するセルフヘルプ記事やチュートリアルを検索します。 ライブおよびオンデマンドのビデオイベントで、エキスパートから戦略とベストプラクティスについて学びましょう。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/mobile" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">詳細情報</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

詳しくは、[Adobe Experience Platform Mobile SDKのドキュメントも参照してください &#x200B;](https://experienceleague.adobe.com/ja/docs/mobile)

#### 開発者向けリファレンス：

- [Mobile SDK開発者ポータル（ホーム） &#x200B;](https://developer.adobe.com/client-sdks/home/)
- [&#x200B; 現在のSDKのバージョン &#x200B;](https://developer.adobe.com/client-sdks/home/current-sdk-versions/)
- [&#x200B; モバイルプロパティ（タグ）の概要 &#x200B;](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)
- [SDKを入手（アプリにインストール） &#x200B;](https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/)
- [Mobile SDKを使用したイベントの追跡 &#x200B;](https://developer.adobe.com/client-sdks/home/getting-started/track-events/)
- [Assuranceでの検証 &#x200B;](https://developer.adobe.com/client-sdks/home/base/assurance/)

>[!SUCCESS]
>
>**Mobile SDK対応チェックリスト**
>
> [ コア SDK] インストールされます（コア、Edge、ID、同意、Assurance）。
> [ 使用 ] るチャネル（プッシュ、アプリ内、コンテンツカード、コードベース）用に追加されたJourney Optimizer モバイル拡張機能。
> [ ] イベントデータセットとプロファイルデータセットに対して正しく設定されたデータストリーム。
> [ ] Assuranceで実装および検証された ID と同意。
> [ ] プッシュトークンの登録とトラッキングは、エンドツーエンドで検証されました。
> [ アプリ内カードやコンテンツカード ]、デバイス上で検証済みとして表示されます。
> [ 新規実装 ] 使用するガイド付きチャネルの設定、またはドキュメントの手順に手動で合わせた設定。



## Adobe Journey Optimizer Channel Configuration

### アプリ内、プッシュ、WhatsApp

ガイド付きチャネル設定機能を使用して **モバイルチャネル** を設定します。 **WhatsApp チャネル** を設定する方法を理解します。

<!-- CARDS
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup
 {description = Learn how to quickly set up and validate web and mobile channels across Experience Platform, Journey Optimizer, and Data Collection, and configure a push notification for a sample iOS marketing app.}
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Guided channel setup">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" title="ガイド付きチャネル設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3433053/?format=jpeg&nocache=1763594622823" alt="ガイド付きチャネル設定"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="ガイド付きチャネル設定">ガイド付きチャネル設定</a>
                    </p>
                    <p class="is-size-6">Experience Platform、Journey Optimizer、データ収集をまたいで web およびモバイルチャネルをすばやく設定および検証する方法、およびサンプルのiOS マーケティングアプリ用にプッシュ通知を設定する方法について説明します。</p>
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1763594622814" alt="WhatsApp チャネルの設定"
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
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
* https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1763594624036" alt="SMS API 資格情報とチャネルサーフェスの設定"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763594624067" alt="カスタム SMS プロバイダーの設定"
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
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="MMS API 資格情報とチャネルサーフェスの設定" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1763594624083" alt="MMS API 資格情報とチャネルサーフェスの設定"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1763594624043" alt="Journey Optimizer での RCS の設定"
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

## ブログ投稿

- [&#x200B; モバイルでの CDN ベースのクライアントサイドパーソナライゼーション（ODD）の使用によるパーソナライゼーションの高速化。](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626?profile.language=ja)
- [Adobe Experience CloudのMobile Activation](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595?profile.language=ja)

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
                    <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Adobe Journey Optimizer のプライバシー機能" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Adobe Journey Optimizer のプライバシー機能"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Adobe Journey Optimizer のプライバシー機能">Adobe Journey Optimizerのプライバシー機能 </a>
                    </p>
                    <p class="is-size-6">プライバシーリクエストの処理、ユーザー操作の監査、同意の管理、ガバナンスルールの適用、顧客管理キーなどの高度なセキュリティオプションの活用の方法について説明します。</p>
                </div>
                <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1763594624934" alt="データガバナンスフレームワークの概要"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1763594624932" alt="ラベルを使用したデータの分類"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1763594624933" alt="データ使用ポリシーの作成"
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

モバイルに関する問題のほとんどは、Journey Optimizerのジャーニーやキャンペーン自体ではなく **0&rbrace;SDKまたはデータ収集の設定 &rbrace; に起因します。**&#x200B;次の表を使用して問題の原因を特定し、該当するセクションを展開して詳細を確認してください。

### 落とし穴の概要

| # | 問題/症状 | よくある落とし穴 | 一目で修正 |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | ガイド付きチャネルのセットアップに失敗。トラフィックがない、または少ない | [SDKのバージョンまたは拡張機能が揃っていない &#x200B;](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | SDK/拡張機能のバージョンを更新し、Assuranceで検証する |
| 2 | バッチのトラッキングが失敗し、AEPでエラーが発生する | [&#x200B; データストリームまたはデータセットの設定の誤り &#x200B;](#2-misconfigured-datastreams-or-datasets) | イベントデータセットへのイベントのマッピングとプロファイルデータセットへのプロファイル |
| 3 | ジャーニーが起動せず、パーソナライゼーションが奇妙になる | [ID または同意が見つからない/一貫性がない &#x200B;](#3-missing-or-inconsistent-identity-and-consent) | Edgeの ID および同意の実装、Assuranceでの検証 |
| 4 | プッシュ配信がないか、レポートで開いている | [&#x200B; プッシュトークンの登録またはトラッキングが破損している &#x200B;](#4-push-token-registration-and-tracking-not-wired-correctly) | SDKによるトークン登録とインタラクショントラッキングの修正 |
| 5 | アクティブなキャンペーンにもかかわらず、アプリ内インプレッションがありません | [&#x200B; アプリ内メッセージまたはコンテンツカードが表示されない &#x200B;](#5-in-app-messages-or-content-cards-not-displaying) | メッセージの拡張機能、トリガーおよびAssuranceの決定応答を確認する |

### 落とし穴ごとの詳細なガイダンス

症状に合った落とし穴を開けて、チェック対象と修正方法を確認します。

<details id="1-sdk-versions-and-extensions-not-aligned-with-channel-requirements">
<summary><strong>1.SDKのバージョンと拡張機能がチャネル要件と合致していない </strong></summary>

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

関連項目：[&#x200B; モバイルと Web の設定 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config)

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. 設定が正しくないデータストリームまたはデータセット </strong></summary>

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

関連項目：[Adobe Journey Optimizerにおけるプッシュ通知フロー &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="3-missing-or-inconsistent-identity-and-consent">
<summary><strong>3.ID と同意が見つからないか、一貫性がない </strong></summary>

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

[Platform Mobile SDK実装の同意の実装 &#x200B;](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/app-implementation/consent) を参照してください。

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4. プッシュトークンの登録とトラッキングが正しく接続されていません </strong></summary>

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

関連項目：[Adobe Journey Optimizerにおけるプッシュ通知フロー &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5. アプリ内メッセージまたはコンテンツカードが表示されない </strong></summary>

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
- [&#x200B; アプリ内メッセージの作成と送信 &#x200B;](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp)
- [Mobile SDKでのコンテンツカードのサポートの設定 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp)

</details>

>[!SUCCESS]
>
> **1 行準備チェックリスト**
>
> アプリをマーケターに渡す前に、**[Assuranceで次のことを確認し &#x200B;](https://developer.adobe.com/client-sdks/home/base/assurance/)** ください。
> 
> [ Core SDKとJourney Optimizerの拡張機能の ] が読み込まれると、\
> [ 正 ] いデータストリームとデータセットでイベントのフローが発生している。\
> [ ]ID と同意は、すべての主要なイベントに存在する、\
> [ ] プッシュトークンとインタラクションが追跡される。\
> [ ] テストのアプリ内メッセージまたはコンテンツカードが少なくとも 1 つ表示され、インプレッションとして記録されている。
