---
title: メールコアコンポーネントの概要
description: メールコアコンポーネントの柔軟性を利用して、説得力のあるメールコンテンツを作成し、Adobe Campaign の機能を活用して提供します。
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: ht
source-wordcount: '409'
ht-degree: 100%

---


# メールコアコンポーネントの概要 {#email-core-components-introduction}

メールコアコンポーネントの柔軟性を利用して、説得力のあるメールコンテンツを作成し、Adobe Campaign の機能を活用して提供します。

## 概要 {#overview}

メールコアコンポーネントは、コアコンポーネントと同一の強力な基盤上に構築されています。 メールコンテンツをシンプルで柔軟なドラッグ＆ドロップでオーサリングでき、Adobe Campaign の機能を使用してオーディエンスに配信できます。

## メリット {#benefits}

メールは、ブランドエクスペリエンスとカスタマージャーニーの一部です。 メールコアコンポーネントを使用すると、作成者は AEM 内からメールコンテンツを作成でき、一貫したブランドのエクスペリエンスを提供し、コンテンツベロシティが向上します。

* コアコンポーネントを使用したページのオーサリングと同様に、メールコアコンポーネントを使用すると、作成者は、技術的な知識がなくても、ブランディングガイドラインに従いながらメールを組み立てることができます。
* アセットやコンテンツを再利用する機能により、作成者はブランディングガイドラインに従い、コンテンツ作成プロセスを最適化することもできます。

## 機能 {#features}

* コアメールコンポーネントは、[コアコンポーネント](/help/introduction.md)に基づいているため、[編集可能なテンプレート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)および[スタイルシステム](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=ja)もサポートしています。
* メールコンテンツを作成するための、[メール用に最適化された、すぐに使用できる 10 個のコンポーネント](#components)があります。
* ほとんどのダイアログフィールドに [Adobe Campaign の変数](campaign-variables.md)が挿入されているので、コアメールコンポーネントは、高度なパーソナライズ機能を提供します。
* 柔軟な[セグメント化コンポーネント](/help/email/components/segmentation.md)を使用すると、コンテンツを詳細にセグメント化することができます。
* コアメールコンポーネントは、[CSS スタイルインライナー](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Technical-documentation)、[HTML フィールド名インライナー](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner)および[HTML サニタイザー](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)によって、メール作成に最適な HTML 出力を提供します。
* メールコンテンツは、`/content` 下の任意の場所で作成できます。
* メールコアコンポーネントは、[オープンソース](https://github.com/adobe/aem-core-email-components)です。

## 要件 {#requirements}

電子メールコアコンポーネントには、以下の要件があります。

| AEM | Adobe Campaign | コアコンポーネント |
|---|---|---|
| AEM 6.5.14.0+<br>オンプレミスまたは AMS | Adobe Campaign Classic<br>Adobe Campaign Standard | [リリース 2.21.2](/help/versions.md)+ |

>[!NOTE]
>
>Adobe Campaign の統合は AEM as a Cloud Service ではサポートされていないので、電子メールコアコンポーネントも同様に AEM as a Cloud Service ではサポートされません。

## メールコンポーネント {#components}

電子メールコアコンポーネントの現在のバージョンには、以下のコンポーネントが含まれています。

* [ページ](components/page.md)
* [コンテナ](components/container.md)
* [タイトル](components/title.md)
* [テキスト](components/text.md)
* [画像](components/image.md)
* [ボタン](components/button.md)
* [ティーザー](components/teaser.md)
* [エクスペリエンスフラグメント](components/experience-fragment.md)
* [コンテンツフラグメント](components/content-fragment.md)
* [セグメント化](components/segmentation.md)

## インストールと使用 {#installation-usage}

電子メールコアコンポーネントのインストールについて詳しくは、[電子メールコアコンポーネントの使用](using.md)ドキュメントを参照してください。
