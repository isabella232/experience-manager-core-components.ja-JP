---
title: コアコンポーネントのバージョン
seo-title: コアコンポーネントのバージョン
description: コアコンポーネントは、同じコアコンポーネントの複数のバージョンを含むことができるリリースとして発行されます。このドキュメントでは、リリースとバージョンと、コアコンポーネントおよびAEMとの互換性を理解する方法について説明します。
seo-description: コアコンポーネントは、同じコアコンポーネントの複数のバージョンを含むことができるリリースとして発行されます。このドキュメントでは、リリースとバージョンと、コアコンポーネントおよびAEMとの互換性を理解する方法について説明します。
uuid: a916a923-8c5e-456a-84b5- b52228e21434
contentOwner: ユーザーは、
content-type: リファレンス
topic-tags: 概要
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: a3a98b2f-65bf-4493-82ad-01717938fdsc
translation-type: tm+mt
source-git-commit: 51842e5b6a9d4491bd4088d30c0d8c3a502e9644

---


# コアコンポーネントのバージョン{#core-components-versions}

コアコンポーネントの現在のリリースは2.4.0で、AEM6.5と互換性があります。2019年5月にリリース2.0.0のマイナーアップデートとしてリリースされました。リリース2.0.0では、既存コンポーネントのv2アップデートとともに新しいコンポーネントが導入されました。

詳しくは、この [ドキュメントの「リリース履歴」と「互換性](#versions-and-releases) 」を参照してください。

[また、コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html)をチェックアウトして、コアコンポーネントの現在のリリースを表示し、使用例を提示することもできます。

## バージョンとリリース {#versions-and-releases}

コアコンポーネントはGitHubを使用して配布されます。これにより、アドビはより迅速にコンポーネントに機能を追加し、AEMリリースサイクル外でコミュニティ入力を可能にすることができます。

コアコンポーネントは、互換性のある定義済みのAEMバージョンで使用できます。つまり、1つのAEMバージョンは、コアコンポーネントの複数のバージョンまたはリリースをサポートすることがあります。これは、特定のバージョンのAEMに結び付けられていた以前のFoundationコンポーネントよりも柔軟性が高くなります。

### バージョン {#versions}

コアコンポーネントの主要な反復は **バージョン**です。各コンポーネントにはバージョンがあります。バージョンは **v** 1やv2などの正の正の整数を持つvで示されます。バージョンは、後方互換性のない変更にのみ増加します。これは、通常、新機能と機能の導入のために使用されます。

開発者および管理者は、コアコンポーネントのバージョンを、リソースタイプパスの数字、およびその実装の完全修飾Javaクラス名によって認識できます。このバージョン番号は、セマンティックのバージョン設定ガイドラインによって [定義されたメジャーバージョンを表し](https://semver.org/)ます。

コアコンポーネントバージョンについて詳しくは、コアコンポーネントの [開発者向けドキュメント](guidelines.md)を参照してください。

### リリース {#releases}

コアコンポーネントは **リリース** から利用できるようになり、GitHubで使用可能な実際の公開アーティファクト [を表し](https://github.com/adobe/aem-core-wcm-components/releases)ます。リリースは、X.Y.Z形式の10進数で示され、すべてのコアコンポーネントを配信先パッケージとして収集します。

* **メジャーリリース** では、既存のコンポーネントの新しいバージョンとまったく新しいコンポーネントと、標準的なバグ修正を導入できます。これは、リリース番号のXコンポーネントのインクリメントで表されます。

* **重要なリリース** では、既存のコンポーネントに関する新機能をバグ修正と共に導入できます。これは、リリース番号のYコンポーネントのインクリメントで表されます。

* **マイナーリリース** にはバグ修正のみが含まれています。これは、リリース番号のZコンポーネントのインクリメントで表されます。

>[!NOTE]
>
>リリースには、同じコンポーネントの複数のバージョンを含めることができます。
>
>同じバージョンのコンポーネントを複数のリリースに表示できます。

## リリース履歴と互換性 {#release-history-and-compatibility}

コアコンポーネントはAEM6.3で最初にリリースされ、サポートされているすべてのAEMバージョンと柔軟で互換性があるように設計されています。このため、コンポーネントのリリースには同じコンポーネントの複数のバージョンを含めることができます。

次の表に、コアコンポーネントのリリースと、そのリリースに含まれるコンポーネントバージョンの互換性を示します。

### リリース履歴とサポートされているAEMバージョン {#release-history-supported-aem-versions}

次の表は、全リリース詳細を含むGitHub上で [利用可能なコンテンツであり、コア](https://github.com/adobe/aem-core-wcm-components/releases)コンポーネントのリリースとAEMリリースおよびJavaバージョンとの互換性について説明しています。

| リリース | 説明 | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java |
|---|---|---|---|---|---|
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | このリリースは、コンテンツフラグメントリストコンポーネントを導入しました | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | このリリースはコンポーネントライブラリの調整に重点を置いていますが、セパレータコンポーネントの機能強化も含まれています | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | このリリースはコンポーネントライブラリに加え、新しいセパレータコンポーネントを導入していますが、画像コンポーネントの機能強化も含まれています | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | このリリースは主にバグ修正に重点を置いていますが、カルーセルコンポーネントの機能強化も含まれています | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 追加されたタブおよびカルーセルコンポーネント、画像、ページ、タイトルコンポーネント、拡張トラッキングの機能強化 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | Teaserコンポーネントの導入、画像コンポーネントの改善、多数のバグ修正 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | バグ修正リリース | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | その他のサポートされている機能強化、バグ修正、および画像のフリップのサポートなどの小さな改善点です。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | ほとんどの機能強化、バグ修正、画像、ページ、コンテンツフラグメントコンポーネントの一部のマイナーな改善点があります | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | ナビゲーション、言語ナビゲーション、クイック検索のコンポーネントが導入されました。すべてのコンポーネントに対して実装されるスタイルシステム。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | すべてのコンポーネントに対するJSONエクスポートの実装、コンテンツフラグメントコンポーネントの導入 | 6.3.1.0 | 6.4.0.0+ | - | 8 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 画像コンポーネントに関するいくつかの修正点 | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | ページコンポーネント、画像コンポーネント、さまざまなグローバル修正および改善点 | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 画像コンポーネントのアニメーションGIF画像の修正点 | 6.3.0.0+ | 6.4.0.0+ | - | 7 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | コアコンポーネントの初回リリース | 6.3.0.0+ | 6.4.0.0+ | - | 7 |

>[!NOTE]
>
>AEMと同様、最新の修正および機能を活用 [するために、実行中のバージョンの](https://github.com/adobe/aem-core-wcm-components/releases/latest) コアコンポーネントと互換性がある最新のリリースおよびバージョンを使用することをお勧めします。

### コンポーネントバージョンとリリース{component- versions- and- release}

次の表に、コアコンポーネントのリリースに含まれるコンポーネントのバージョンを示します。

|  | リリース1.0.0-1.0.6 | リリース1.1.0 | リリース2.0.0-2.0.8 | リリース2.1.0 | リリース2.2.-2.2.0 | 2.3.0 |
|---|---|---|---|---|---|---|
| **[ページ](page.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[タイトル](title.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[画像](image.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[リスト](list.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[パンくず](breadcrumb.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[ソーシャルメディア共有](sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 |
| **[フォームコンテナ](form-container.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームテキスト](form-text.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームオプション](form-options.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォーム非表示](form-hidden.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームボタン](form-button.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[コンテンツフラグメント](content-fragment-component.md)** | サンドボックス | v1 | v1 | v1 | v1 |
| **[ナビゲーション](navigation.md)** | v1 | v1 | v1 | v1 |
| **[言語ナビゲーション](language-navigation.md)** | v1 | v1 | v1 | v1 |
| **[クイック検索](quick-search.md)** | v1 | v1 | v1 | v1 |
| **[ティーザー](teaser.md)** | v1 | v1 | v1 |
| **[タブ](tabs.md)** | v1 | v1 |
| **[カルーセル](carousel.md)** | v1 | v1 |
| **[区切り文字](separator.md)** | v1 |

## ドキュメント {#documentation}

[コアコンポーネント](authoring.md) を使用したオーサリングでは、コアコンポーネントと、コンテンツ作成者やテンプレート作成者に公開される機能について説明します。各コンポーネントについて詳しく説明しています。

[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html) は、ほとんどのコアコンポーネントの現在のバージョンのショーケースであり、どのように使用できるかを示しています。

[コアコンポーネント](developing.md) の開発では、コアコンポーネントの技術的機能、プロジェクト内での使用方法、カスタマイズ方法およびベストプラクティスについて説明します。

[コアコンポーネントの概要](introduction.md) では、バージョン、使用事例およびサポートにおけるコアコンポーネントの互換性の概要が提供されています。
