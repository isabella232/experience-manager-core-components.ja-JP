---
title: コアコンポーネントのバージョン
seo-title: コアコンポーネントのバージョン
description: コアコンポーネントはリリースとして公開されます。これらのリリースには、同じコアコンポーネントの複数のバージョンが含まれている場合があります。このドキュメントでは、リリースとバージョンの概要、およびコアコンポーネントと AEM の互換性を理解する方法について説明します。
seo-description: コアコンポーネントはリリースとして公開されます。これらのリリースには、同じコアコンポーネントの複数のバージョンが含まれている場合があります。このドキュメントでは、リリースとバージョンの概要、およびコアコンポーネントと AEM の互換性を理解する方法について説明します。
uuid: a916a923-8c5e-456a-84b5-b52228e21434
contentOwner: ユーザー
content-type: reference
topic-tags: introduction
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: a3a98b2f-65bf-4493-82ad-01717938fdbc
translation-type: tm+mt
source-git-commit: 63e75079e41d3091ca57bfc3129e700675bf4939

---


# コアコンポーネントのバージョン{#core-components-versions}

コアコンポーネントの現在のリリースは2.6.0で、AEM6.5と互換性があります。2019年9月にリリース2.0.0の重要なアップデートとしてリリースされました。リリース2.0.0では、既存コンポーネントのv2アップデートとともに新しいコンポーネントが導入されました。

詳しくは、このドキュメントの[リリース履歴と互換性](#versions-and-releases)を参照してください。

また、[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html)も参照してください。ここでは、コアコンポーネントの現在のリリースを紹介し、使用例を示しています。

## バージョンとリリース {#versions-and-releases}

コアコンポーネントは GitHub を通じて配布されます。これにより、アドビはより迅速にコンポーネントに機能を追加できるほか、AEM リリースサイクル以外でコミュニティからの入力を取り入れることもできます。

コアコンポーネントは、互換性のある規定された AEM バージョンで使用できます。つまり、1 つのAEM バージョンがコアコンポーネントの複数のバージョンまたはリリースをサポートしている場合があります。その結果、以前の基盤コンポーネントよりも柔軟性が高くなっています。基盤コンポーネントは AEM の特定のバージョンに結び付いていました。

### バージョン {#versions}

コアコンポーネントの主要な反復が&#x200B;**バージョン**&#x200B;です。各コンポーネントにはバージョンがあります。バージョンは、v1 や v2 のように、**v** の後に正の整数が付いた形式で示されます。バージョンは、下位互換性のない変更の場合にのみ増えます。これは、通常、新しい特長や機能が導入される場合です。

開発者や管理者は、リソースタイプパスや実装の完全修飾 Java クラス名に含まれている数字で、コアコンポーネントのバージョンを認識できます。このバージョン番号は、[セマンティックバージョニングガイドライン](https://semver.org/)/で定義されたメジャーバージョンを表します。

コアコンポーネントバージョンについて詳しくは、[コアコンポーネントの開発者向けドキュメント](guidelines.md)を参照してください。

### リリース {#releases}

The core components are made available through **releases** and [represent the actual published artifacts available on GitHub](https://github.com/adobe/aem-core-wcm-components/releases). リリースは、すべてのコアコンポーネントを配信可能なパッケージとしてまとめたもので、X.Y.Z 形式の 10 進数で示されます。

* **メジャーリリース**&#x200B;では、既存コンポーネントの新しいバージョンのほか、まったく新しいコンポーネントおよび通常のバグ修正を取り入れることができます。これは、リリース番号の X 部分のインクリメントで表されます。
* **重要リリース**&#x200B;では、コンポーネントの既存バージョンに新しい機能を導入できるほか、バグ修正をおこなうことができます。これは、リリース番号の Y 部分のインクリメントで表されます。
* **マイナーリリース**&#x200B;にはバグ修正のみ含まれています。これは、リリース番号の Z 部分のインクリメントで表されます。

>[!NOTE]
>
>リリースには、同じコンポーネントの複数のバージョンを含めることができます。
>
>同じバージョンのコンポーネントが複数のリリースに現れることがあります。

## リリース履歴と互換性 {#release-history-and-compatibility}

コアコンポーネントは AEM 6.3 で初めてリリースされました。柔軟性があり、サポートされているすべての AEM バージョンと互換性があるように設計されています。このため、コンポーネントの 1 つのリリースに同じコンポーネントの複数のバージョンを含めることができます。

コアコンポーネントの各リリースの互換性、およびリリースとそこに含まれているコンポーネントバージョンの対応関係を以下の表に示します。

### リリース履歴とサポートされている AEM バージョン {#release-history-supported-aem-versions}

次の表は、コアコンポーネントの各リリースと AEM リリースおよび Java バージョンとの互換性の概要を示しています（[各リリースの詳細については GitHub を参照してください](https://github.com/adobe/aem-core-wcm-components/releases)）。

| リリース | 説明 | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java | リリース日 |
|---|---|---|---|---|---|---|
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | このリリースは新しいエクスペリエンスフラグメントコンポーネントを導入しました | 6.3.3.0 以上 | 6.4.2.0 以上 | 6.5.0.0 以上 | 8、11 | 2019年9月 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | このリリースでは、新しいアコーディオン、ボタン、コンテナおよびダウンロードコンポーネントが導入されました。 | 6.3.3.0 以上 | 6.4.2.0 以上 | 6.5.0.0 以上 | 8、11 | 2019年6月26日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | このリリースでは、コンテンツフラグメントリストコンポーネントが導入されました。 | 6.3.3.0 以上 | 6.4.2.0 以上 | 6.5.0.0 以上 | 8、11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | このリリースではコンポーネントライブラリの改善に重点を置いていますが、区切り文字コンポーネントの機能強化も含まれています。 | 6.3.3.0 以上 | 6.4.2.0 以上 | 6.5.0.0 以上 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | このリリースではコンポーネントライブラリの改善に重点を置き、新しい区切り文字コンポーネントを導入したほか、画像コンポーネントの機能強化も含まれています。 | 6.3.3.0 以上 | 6.4.2.0 以上 | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | このリリースは主にバグ修正に重点を置いていますが、カルーセルコンポーネントの機能強化も含まれています。 | 6.3.3.0 以上 | 6.4.2.0 以上 | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | タブコンポーネントとカルーセルコンポーネントの導入、画像、ページ、タイトルの各コンポーネントの改善、トラッキングの機能強化がおこなわれました。 | 6.3.3.0 以上 | 6.4.2.0 以上 | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | ティーザーコンポーネントの導入、画像コンポーネントの改善、多数のバグ修正がおこなわれました。 | 6.3.3.0 以上 | 6.4.2.0 以上 | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | バグ修正リリース | 6.3.2.0 以上 | 6.4.0.0 以上 | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 追加の内部的改善、バグ修正、画像フリップのサポートなどの小規模な改善がおこなわれました。 | 6.3.2.0 以上 | 6.4.0.0 以上 | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 内部的な改善がほとんどで、その他にバグ修正や、画像、ページ、コンテンツフラグメントの各コンポーネントの小規模な改善がおこなわれました。 | 6.3.2.0 以上 | 6.4.0.0 以上 | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | ナビゲーション、言語ナビゲーション、クイック検索の各コンポーネントが導入されました。すべてのコンポーネントにスタイルシステムが実装されました。 | 6.3.2.0 以上 | 6.4.0.0 以上 | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | すべてのコンポーネントに JSON エクスポートが実装され、コンテンツフラグメントコンポーネントが導入されました。 | 6.3.1.0 | 6.4.0.0 以上 | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 画像コンポーネントの修正がいくつかおこなわれました。 | 6.3.0.0 以上 | 6.4.0.0 以上 | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | ページコンポーネントと画像コンポーネントが修正されたほか、広範囲にわたる様々な修正および改善がおこなわれました。 | 6.3.0.0 以上 | 6.4.0.0 以上 | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 画像コンポーネントのアニメーション GIF 画像が修正されました。 | 6.3.0.0 以上 | 6.4.0.0 以上 | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | コアコンポーネントの初回リリースです。 | 6.3.0.0 以上 | 6.4.0.0 以上 | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>AEM の場合と同様、最新の修正および機能を活用するために、実行している AEM バージョンと互換性のある入手可能な[最新のリリースおよびバージョンのコアコンポーネント](https://github.com/adobe/aem-core-wcm-components/releases/latest)を開発に使用することをお勧めします。

### コンポーネントのバージョンとリリース {#component-versions-and-releases}

コアコンポーネントの各リリースと、そこに含まれている各コンポーネントのバージョンを次の表に示します。

|  | リリース 1.0.0 ～ 1.0.6 | リリース 1.1.0 | リリース 2.0.0 ～ 2.0.8 | リリース 2.1.0 | リリース 2.2.～ 2.2.0 | リリース 2.3.0 |
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
| **[コンテンツフラグメント](content-fragment-component.md)** |  | サンドボックス | v1 | v1 | v1 | v1 |
| **[ナビゲーション](navigation.md)** |  |  | v1 | v1 | v1 | v1 |
| **[言語ナビゲーション](language-navigation.md)** |  |  | v1 | v1 | v1 | v1 |
| **[クイック検索](quick-search.md)** |  |  | v1 | v1 | v1 | v1 |
| **[ティーザー](teaser.md)** |  |  |  | v1 | v1 | v1 |
| **[タブ](tabs.md)** |  |  |  |  | v1 | v1 |
| **[カルーセル](carousel.md)** |  |  |  |  | v1 | v1 |
| **[区切り文字](separator.md)** |  |  |  |  |  | v1 |

## ドキュメント {#documentation}

[コアコンポーネントを使用したオーサリング](authoring.md)では、コアコンポーネントと、コンテンツ作成者やテンプレート作成者に公開されている機能の使用方法について説明します。各コンポーネントについて詳しく説明しています。

[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html)では、ほとんどのコアコンポーネントの現在のバージョンを紹介し、それらの使用方法を示しています。

[コアコンポーネントの開発](developing.md)では、コアコンポーネントの技術的機能、プロジェクト内での使用方法、カスタマイズ方法およびベストプラクティスについて説明しています。

[コアコンポーネントの概要](introduction.md)では、コアコンポーネントの各バージョンの機能、使用例およびサポートの概要を説明しています。
