---
title: AJOのコードベースのエクスペリエンスでの編集可能なフォームフィールドの使用
description: Adobe Journey Optimizer のコードベースのエクスペリエンステンプレートのインラインフォームフィールドを使用して編集可能なコンテンツブロックを作成し、マーケターが動的で再利用可能なキャンペーンコンテンツを使用できるようにする方法について説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18416
exl-id: 0ba695d6-becb-440d-b0d0-de5b51b42562
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
source-wordcount: '221'
ht-degree: 22%
---
# AJOのコードベースのエクスペリエンスでの編集可能なフォームフィールドの使用

多くのマーケティングジャーニーにおいて、特に規制が厳しい業界では、キャンペーン、地域、製品に応じて異なる免責条項を含めることが不可欠です。 マーケターや法務部門は、AJO Personalizationエディターで[編集可能なフィールド &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences)を直接使用することで、開発者の関与や意思決定ロジックの変更なしに、免責事項のテキストを完全に制御することができます。

これにより、オファーなどの決定済みのコンテンツを活用しながら、迅速な更新が可能になり、キャンペーン全体のコンプライアンスを確保できます。

## パーソナライゼーションエディターへの編集可能フィールドの挿入

- 前の手順で作成したキャンペーンを開きます。
- 「_&#x200B;**キャンペーンを変更**&#x200B;_」をクリックします
- 「_&#x200B;**コンテンツ**&#x200B;_」タブに移動します
- 「_&#x200B;**コードを編集**&#x200B;_」をクリックし、パーソナライゼーションエディターで次の構文を使用して、legalDisclaimerという編集可能フィールドをデフォルト値で挿入します

- `{{#inline "legalDisclaimer" name="Legal Disclaimer"}} Legal Disclaimer will go here {{/inline}}`

- 以下に示すように、テンプレートで`{{{legalDisclaimer}}}`変数を使用します

- ![編集可能フィールド &#x200B;](assets/editable-fields.png)

- マーケターは、パーソナライゼーションエディターを開くことなく、「免責事項」フィールドを簡単に編集できます。
- ![editable-field-marketer](assets/editable-field-marketer-view.png)



## キャンペーンの公開

キャンペーンをアクティベートして、パーソナライズされたオファーのリアルタイムの提供を開始する。
