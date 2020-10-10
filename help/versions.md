---
title: コアコンポーネントのバージョン
description: コアコンポーネントはリリースとして公開されます。これらのリリースには、同じコアコンポーネントの複数のバージョンが含まれている場合があります。このドキュメントでは、リリースとバージョンの概要、およびコアコンポーネントと AEM の互換性を理解する方法について説明します。
translation-type: ht
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: ht
source-wordcount: '1681'
ht-degree: 100%

---


# コアコンポーネントのバージョン {#core-components-versions}

コアコンポーネントの現在のリリースは 2.11.0 で、[AEM as a Cloud Service](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html) および [On-Premise の AEM](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/user-guide/home.html) インストールと互換性があります。このバージョンは、リリース 2.0.0 の重要な更新として 2020 年 7 月にリリースされました。リリース 2.0.0 では、既存のコンポーネントの v2 アップデートに加えて、新しいコンポーネントが導入されました。

## リリース履歴と互換性 {#release-history-and-compatibility}

コアコンポーネントは、柔軟性を備え、サポートされるすべての AEM バージョンと互換性があるように設計されています。このため、コンポーネントの 1 つのリリースに同じコンポーネントの複数のバージョンを含めることができます。

コアコンポーネントの各リリースの互換性、およびリリースとそこに含まれているコンポーネントバージョンの対応関係を以下の表に示します。

### リリース履歴と要件 {#release-history-requirements}

次の表は、コアコンポーネントの各リリースと AEM リリースおよび Java バージョンとの互換性の概要を示しています（[各リリースの詳細については GitHub を参照してください](https://github.com/adobe/aem-core-wcm-components/releases)）。

| リリース | 説明 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | リリース日 |
|---|---|---|---|---|---|---|
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | このリリースでは、AMP のサポートが導入されました。 | 6.4.8.1+ | 6.5.5.0+ | 継続的 | 8、11 | 2020 年 7 月 20 日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | このリリースでは、PDF ビューアコンポーネントが導入されました。 | 6.4.8.1+ | 6.5.5.0+ | 継続的 | 8、11 | 2020 年 6 月 17 日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | このリリースでは、Adobe Client Data Layer との統合が可能になり、プログレスバーコンポーネントが導入されました。 | 6.4.8.0+ | 6.5.4.0+ | 継続的 | 8、11 | 2020 年 5 月 29 日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | このリリースでは小規模の機能強化による修正に重点を置きました。 | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 12 月 5 日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | このリリースでは新しい埋め込みコンポーネントを導入しました | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | このリリースでは新しいエクスペリエンスフラグメントコンポーネントを導入しました | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | このリリースでは、アコーディオン、ボタン、コンテナ、ダウンロードの各コンポーネントが新しく導入されました。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 6 月 25 日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | このリリースでは、コンテンツフラグメントリストコンポーネントが導入されました。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 5 月 7 日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | このリリースではコンポーネントライブラリの改善に重点を置いていますが、区切り文字コンポーネントの機能強化も含まれています。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8 | 2019 年 3 月 14 日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | このリリースではコンポーネントライブラリの改善に重点を置き、新しい区切り文字コンポーネントを導入したほか、画像コンポーネントの機能強化も含まれています。 | 6.4.2.0 以上 | - | - | 8 | 2019 年 2 月 11 日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | このリリースは主にバグ修正に重点を置いていますが、カルーセルコンポーネントの機能強化も含まれています。 | 6.4.2.0 以上 | - | - | 8 | 2018 年 11 月 27 日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | タブコンポーネントとカルーセルコンポーネントの導入、画像、ページ、タイトルの各コンポーネントの改善、トラッキングの機能強化がおこなわれました。 | 6.4.2.0 以上 | - | - | 8 | 2018 年 10 月 16 日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | ティーザーコンポーネントの導入、画像コンポーネントの改善、多数のバグ修正がおこなわれました。 | 6.4.2.0 以上 | - | - | 8 | 2018 年 7 月 13 日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | バグ修正リリース | 6.4.0.0 以上 | - | - | 8 | 2018 年 6 月 12 日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 追加の内部的改善、バグ修正、画像フリップのサポートなどの小規模な改善がおこなわれました。 | 6.4.0.0 以上 | - | - | 8 | 2018 年 4 月 11 日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 内部的な改善がほとんどで、その他にバグ修正や、画像、ページ、コンテンツフラグメントの各コンポーネントの小規模な改善がおこなわれました。 | 6.4.0.0 以上 | - | - | 8 | 2018 年 3 月 7 日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | ナビゲーション、言語ナビゲーション、クイック検索の各コンポーネントが導入されました。すべてのコンポーネントにスタイルシステムが実装されました。 | 6.4.0.0 以上 | - | - | 8 | 2018 年 1 月 16 日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | すべてのコンポーネントに JSON エクスポートが実装され、コンテンツフラグメントコンポーネントが導入されました。 | 6.4.0.0 以上 | - | - | 8 | 2017 年 10 月 10 日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 画像コンポーネントの修正がいくつかおこなわれました。 | 6.4.0.0 以上 | - | - | 8 | 2017 年 8 月 4 日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | ページコンポーネントと画像コンポーネントが修正されたほか、広範囲にわたる様々な修正および改善がおこなわれました。 | 6.4.0.0 以上 | - | - | 8 | 2017 年 4 月 26 日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 画像コンポーネントのアニメーション GIF 画像が修正されました。 | 6.4.0.0 以上 | - | - | 7 | 2017 年 3 月 22 日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | コアコンポーネントの初回リリースです。 | 6.4.0.0 以上 | - | - | 7 | 2017 年 3 月 20 日 |

>[!NOTE]
>
>AEM の場合と同様、最新の修正および機能を活用するために、実行している AEM バージョンと互換性のある入手可能な[最新のリリースおよびバージョンのコアコンポーネント](https://github.com/adobe/aem-core-wcm-components/releases/latest)を開発に使用することをお勧めします。

### コンポーネントのバージョンとリリース {#component-versions-and-releases}

コアコンポーネントの各リリースと、そこに含まれている各コンポーネントのバージョンを次の表に示します。

|  | リリース 1.0.0 ～ 1.0.6 | リリース 1.1.0 | リリース 2.0.0 ～ 2.0.8 | リリース 2.1.0 | リリース 2.2.0 ～ 2.2.0 | リリース 2.3.0 ～ 2.3.2 | リリース 2.4.0 | リリース 2.5.0 | リリース 2.6.0 | リリース 2.7.0 ～ 2.8.0 | リリース 2.9.0 以上 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **[ページ](components/page.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[タイトル](components/title.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[画像](components/image.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[リスト](components/list.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[パンくず](components/breadcrumb.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[ソーシャルメディア共有](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[フォームコンテナ](components/forms/form-container.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームテキスト](components/forms/form-text.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームオプション](components/forms/form-options.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォーム非表示](components/forms/form-hidden.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームボタン](components/forms/form-button.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[コンテンツフラグメント](components/content-fragment-component.md)** |  | サンドボックス | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 |
| **[ナビゲーション](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[言語ナビゲーション](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[クイック検索](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[ティーザー](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[タブ](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[カルーセル](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[区切り文字](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[コンテンツフラグメントリスト](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[アコーディオン](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[ボタン](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[コンテナ](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[ダウンロード](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[エクスペリエンスフラグメント](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[埋め込み](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 |
| **[プログレスバー](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 |
| **[PDF ビューア](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## バージョンとリリース {#versions-and-releases}

コアコンポーネントは GitHub を通じて配布されます。これにより、アドビはより迅速にコンポーネントに機能を追加できるほか、AEM リリースサイクル以外でコミュニティからの入力を取り入れることもできます。

コアコンポーネントは、互換性のある規定された AEM バージョンで使用できます。つまり、1 つの AEM バージョンがコアコンポーネントの複数のバージョンまたはリリースをサポートしている場合があります。その結果、以前の基盤コンポーネントよりも柔軟性が高くなっています。基盤コンポーネントは AEM の特定のバージョンに結び付いていました。

### バージョン {#versions}

コアコンポーネントの主要な反復が&#x200B;**バージョン**&#x200B;です。各コンポーネントにはバージョンがあります。バージョンは、v1 や v2 のように、**v** の後に正の整数が付いた形式で示されます。バージョンは、下位互換性のない変更の場合にのみ増えます。これは、通常、新しい特長や機能が導入される場合です。

開発者や管理者は、リソースタイプパスや実装の完全修飾 Java クラス名に含まれている数字で、コアコンポーネントのバージョンを認識できます。このバージョン番号は、[セマンティックバージョニングガイドライン](https://semver.org/)/で定義されたメジャーバージョンを表します。

コアコンポーネントバージョンについて詳しくは、[コアコンポーネントの開発者向けドキュメント](developing/guidelines.md)を参照してください。

### リリース {#releases}

コアコンポーネントは&#x200B;**リリース**&#x200B;を通じて使用できるようになり、[GitHub で実際に入手可能な公開済みアーティファクトを表します](https://github.com/adobe/aem-core-wcm-components/releases)。リリースは、すべてのコアコンポーネントを配信可能なパッケージとしてまとめたもので、X.Y.Z 形式の 10 進数で示されます。

* **メジャーリリース**&#x200B;では、既存コンポーネントの新しいバージョンのほか、まったく新しいコンポーネントおよび通常のバグ修正を取り入れることができます。これは、リリース番号の X 部分のインクリメントで表されます。
* **重要リリース**&#x200B;では、コンポーネントの既存バージョンに新しい機能を導入できるほか、バグ修正をおこなうことができます。これは、リリース番号の Y 部分のインクリメントで表されます。
* **マイナーリリース**&#x200B;にはバグ修正のみ含まれています。これは、リリース番号の Z 部分のインクリメントで表されます。

>[!NOTE]
>
>リリースには、同じコンポーネントの複数のバージョンを含めることができます。
>
>同じバージョンのコンポーネントが複数のリリースに現れることがあります。

## コアコンポーネントのサポート {#core-components-support}

コアコンポーネントは AEM に不可欠な部分なので、クイックスタートの一部として提供される場合と同じ条件の下、現状のままでサポートされます。

他の製品機能と同じく、提供終了の一般的なルールは次のようになります。

* コンポーネントは、削除される前に、非推奨になったことが事前に通知されます
* 早ければその通知の後、AEM リリースからコンポーネントが削除されます。

したがって、新しいバージョンのコンポーネントへの移行を検討するユーザーに対し、サポートが終了するまでの期間として少なくとも 1 つのリリースサイクルが与えられることになります。

各コンポーネントのバージョンには、サポートされる AEM バージョンが明記されています。ある AEM バージョンのサポートが停止されると、その AEM バージョンでのコアコンポーネントのサポートも停止されます。

コンポーネントのカスタマイズのサポートについて詳しくは、関連するコアコンポーネントバージョンの[コアコンポーネントのカスタマイズ](developing/customizing.md)ページを参照してください。

## 基盤コンポーネントのサポート {#foundation-component-support}

Adobe の開発における重点は、コアコンポーネントに移行し、新機能の追加は今後も続けられます。

[ほとんどの基盤コンポーネントは AEM 6.5 では非推奨となり](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/authoring/siteandpage/default-components-foundation.html)、今後は基盤コンポーネントに関する主なバグ修正のみが検討されます。
