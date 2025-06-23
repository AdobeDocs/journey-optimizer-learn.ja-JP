---
title: AJO コードベースのエクスペリエンスでの編集可能なフォームフィールドの使用
description: Adobe Journey Optimizerのコードベースのエクスペリエンステンプレートのインラインフォームフィールドを使用して編集可能なコンテンツブロックを作成し、マーケターが動的で再利用可能なキャンペーンコンテンツを使用できるようにする方法について説明します。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18416
source-git-commit: b9feb65fb7af8fb495f81841ab9235e4ae80ecd7
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 1%

---

# AJO コードベースのエクスペリエンスでの編集可能なフォームフィールドの使用

多くのマーケティングジャーニー、特に規制対象の業界では、キャンペーン、地域、製品に応じて異なる可能性のある法的免責事項を含めることが不可欠です。 AJO Personalization Editor で直接 [ 編集可能フィールド ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences) を使用すると、マーケターや法務チームは、開発者を関与させたり、意思決定ロジックを変更したりすることなく、免責事項のテキストを完全に制御できます。

これにより、迅速な更新が可能になり、オファーなどの決定されたコンテンツを活用しながら、キャンペーン全体でコンプライアンスが確保されます。

## パーソナライゼーションエディターへの編集可能フィールドの挿入

- 前の手順で作成したキャンペーンを開きます。
- 「_&#x200B;**キャンペーンを変更**&#x200B;_」をクリックします
- _&#x200B;**コンテンツ**&#x200B;_ タブに移動します。
- 「_&#x200B;**コードを編集**&#x200B;_」をクリックし、パーソナライゼーションエディターで次の構文を使用して、legalDisclaimer という編集可能なフィールドをデフォルト値で挿入します

- &#x200B;
  <pre> {{#inline "legalDisclaimer" name="Legal Disclaimer"}} 法的免責事項はここに {{/inline}} に移動します  </pre>

- <code>{{{legalDisclaimer}}} の使用</code> 以下に示すように、テンプレート内の変数

- ![ 編集可能フィールド ](assets/editable-fields.png)

- マーケターは、パーソナライゼーションエディターを開かなくても、「法的免責事項」フィールドを簡単に編集できます。
- ![editable-field-marketer](assets/editable-field-marketer-view.png)



## キャンペーンの公開

キャンペーンをアクティブ化して、パーソナライズされたオファーのリアルタイムでの配信を開始します。

