---
title: 電子メールコアコンポーネントの概要
description: E メールコアコンポーネントの柔軟性を利用して、説得力のある E メールコンテンツを作成し、Adobe Campaignの機能を活用して提供します。
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 10%

---


# 電子メールコアコンポーネントの概要 {#email-core-components-introduction}

E メールコアコンポーネントの柔軟性を利用して、説得力のある E メールコンテンツを作成し、Adobe Campaignの機能を活用して提供します。

## 概要 {#overview}

電子メールコアコンポーネントは、コアコンポーネントと同じ強力な基盤上に構築されています。 E メールコンテンツをシンプルで柔軟なドラッグ&amp;ドロップでオーサリングでき、Adobe Campaignの機能を使用してオーディエンスに配信できます。

## メリット {#benefits}

E メールは、ブランドエクスペリエンスとカスタマージャーニーの一部です。 電子メールコアコンポーネントを使用すると、作成者はAEM内から電子メールコンテンツを作成でき、一貫したブランドのエクスペリエンスを提供し、コンテンツの速度を向上できます。

* コアコンポーネントを使用したページのオーサリングと同様に、電子メールコアコンポーネントを使用すると、作成者は、ブランディングガイドラインに従いながら、技術的な知識を持たずに電子メールを組み立てることができます。
* アセットやコンテンツを再利用する機能は、作成者がブランディングガイドラインに従ってコンテンツ作成プロセスを最適化することを推奨します。

## 機能 {#features}

* コア電子メールコンポーネントは、 [コアコンポーネント、](/help/introduction.md) そのため、 [編集可能なテンプレート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja) そして [スタイルシステム。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=ja)
* 次のものがあります。 [電子メールに最適化された 10 個の実稼動用コンポーネント](#components) 電子メールコンテンツを作成する場合。
* コア電子メールコンポーネントは、 [Adobe Campaign変数](campaign-variables.md) ほとんどのダイアログフィールドで使用できます。
* 柔軟性 [セグメント化コンポーネント](/help/email/components/segmentation.md) では、コンテンツを高度なセグメント化することができます。
* コア電子メールコンポーネントは、 [CSS スタイルインライナー、](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Technical-documentation) [HTML属性 inliner](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) および [HTMLを殺す人。](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)
* E メールコンテンツは以下の任意の場所で作成できます。 `/content`.
* 電子メールコアコンポーネントは、 [オープンソース。](https://github.com/adobe/aem-core-email-components)

## 要件 {#requirements}

電子メールコアコンポーネントには、次の要件があります。

| AEM | Adobe Campaign | コアコンポーネント |
|---|---|---|
| AEM 6.5.14.0以降<br>オンプレミスまたは AMS | Adobe Campaign Classic<br>Adobe Campaign Standard | [リリース2.21.2](/help/versions.md)+ |

>[!NOTE]
>
>Adobe Campaignの統合はAEM as a Cloud Serviceではサポートされていないので、電子メールコアコンポーネントも同様にAEM as a Cloud Serviceではサポートされません。

## 電子メールコンポーネント {#components}

電子メールコアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

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

## インストールと使用方法 {#installation-usage}

詳しくは、 [電子メールコアコンポーネントの使用](using.md) 電子メールコアコンポーネントのインストールについて詳しくは、こちらのドキュメントを参照してください。
