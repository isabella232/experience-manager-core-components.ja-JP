---
title: コアコンポーネントのバージョン
description: コアコンポーネントはリリースとして公開されます。これらのリリースには、同じコアコンポーネントの複数のバージョンが含まれている場合があります。このドキュメントでは、リリースとバージョンの概要、およびコアコンポーネントと AEM の互換性を理解する方法について説明します。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: e62bb19a487e337c1ea5994d9fbfc845145ae19d
workflow-type: ht
source-wordcount: '2147'
ht-degree: 100%

---

# コアコンポーネントのバージョン {#core-components-versions}

コアコンポーネントの現在のリリースは 2.17.0 で、[AEM as a Cloud Service](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html) および[オンプレミスの AEM](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/user-guide/home.html) インストールと互換性があります。

## リリース履歴と互換性 {#release-history-and-compatibility}

コアコンポーネントは、柔軟性を備え、サポートされるすべての AEM バージョンと互換性があるように設計されています。このため、コンポーネントの 1 つのリリースに同じコンポーネントの複数のバージョンを含めることができます。

コアコンポーネントの各リリースの互換性、およびリリースとそこに含まれているコンポーネントバージョンの対応関係を以下の表に示します。

### リリース履歴と要件 {#release-history-requirements}

次の表は、コアコンポーネントの各リリースと AEM リリースおよび Java バージョンとの互換性の概要を示しています（[各リリースの詳細については GitHub を参照してください](https://github.com/adobe/aem-core-wcm-components/releases)）。

| リリース | 説明 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | リリース日 |
|---|---|---|---|---|---|---|
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | このリリースには、リンクハンドラー機能をサポートする多数の新しいコンポーネントバージョンのテクニカルプレビューと、[ページコンポーネント](/help/components/page.md)の画像機能のテクニカルプレビューが含まれています。いくつかのバグ修正も含まれています。 | 6.4.8.4+ * | 6.5.6.0+ * | 継続的 | 8、11 | 2021 年 6 月 16 日（PT） |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 新しいリンクハンドラーの問題を修正するためのパッチリリースです。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2021 年 5 月 19 日（PT） |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 主に新しいリンクハンドラーの問題を修正するパッチリリースです。[PWA](/help/components/page.md#pwa-support) 用の複数ページアプリケーションをサポートするための機能が追加されました。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2021 年 5 月 15 日（PT） |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | このリリースでは、アクセシビリティの向上と、既存のコンポーネントに対する新しいリンクハンドラーの導入に焦点を当てています。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2021 年 4 月 22 日（PT） |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | これは、主に[データレイヤー](/help/developing/data-layer/overview.md)の下位互換性の問題と、特定の状況で IT テストが失敗する問題を修正するパッチリリースでした。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2021 年 3 月 16 日（PT） |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | このリリースでは、[プログレッシブ ｗeb アプリ（PWA）がページコンポーネント](/help/components/page.md#pwa-support)でサポートされているほか、[Adobe データレイヤー](/help/developing/data-layer/overview.md)のバージョン 2.0.0 がサポートされています。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2021 年 2 月 23 日（PT） |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | このリリースには、[埋め込みコンポーネント](/help/components/embed.md)の新しいオプションが含まれています。また、[ページ](/help/components/page.md)レベルでブランドスラッグが導入されているほか、多くの問題にも対処しています。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2021 年 2 月 9 日（PT） |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | これは、AEMaaCS で RTE を使用した場合の問題に対処するためのパッチリリースでした。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2020 年 12 月 16 日（PT） |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | このリリースには、[画像コンポーネント](/help/components/image.md)の新しい Dynamic Media 機能が含まれています。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2020 年 12 月 4 日（PT） |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | これは、2.12.0 のパッチリリースで、マイナーな修正が含まれています。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2020 年 11 月 11 日（PT） |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | これは2.12.0のパッチリリースで、[画像コンポーネント](/help/components/image.md)の重大なバグを修正しました。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2020 年 11 月 5 日（PT） |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | このリリースでは、[新しい POST フォームハンドラ](/help/components/forms/form-container.md#post-data)、カスタム CSS、JavaScript、メタデータ[タグをコンテキストに応じた設定で組み込む](/help/developing/including-clientlibs.md#context-aware-loading)機能、[カスタムコンポーネントでデータレイヤーとの統合を簡単に行う](/help/developing/data-layer/integrations.md#enabling-custom-components)ための `DataLayerBuilder` ユーティリティが導入されました。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2020 年 10月 29 日（PT） |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | このリリースでは、[AMP のサポート](/help/developing/amp.md)が導入されました。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2020 年 7 月 20 日（PT） |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | このリリースでは、[PDF ビューアコンポーネント](/help/components/pdf-viewer.md)が導入されました。 | 6.4.8.1+ | 6.5.5.0+ | 継続的 | 8、11 | 2020 年 6 月 17 日（PT） |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | このリリースでは、[Adobe Client Data Layer](/help/developing/data-layer/overview.md) との統合が可能になり、[進行状況バーコンポーネント](/help/components/progress-bar.md)が導入されました。 | 6.4.8.0+ | 6.5.4.0+ | 継続的 | 8、11 | 2020 年 5 月 29 日（PT） |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | このリリースでは小規模の機能強化による修正に重点を置きました。 | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 12 月 5 日（PT） |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | このリリースでは、新しい[埋め込みコンポーネント](/help/components/embed.md)が導入されました。 | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 9 月 25 日（PT） |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | このリリースでは、新しい[エクスペリエンスフラグメントコンポーネント](/help/components/experience-fragment.md)が導入されました. | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 9 月 6 日（PT） |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | このリリースでは、[アコーディオン](/help/components/accordion.md)、[ボタン](/help/components/button.md)、[コンテナ](/help/components/container.md)、[ダウンロード](/help/components/download.md)の各コンポーネントが新しく導入されました。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 6 月 25 日（PT） |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | このリリースでは、[コンテンツフラグメントリストコンポーネント](/help/components/content-fragment-list.md)が導入されました。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019 年 5 月 7 日（PT） |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | このリリースでは[コンポーネントライブラリ](https://aemcomponents.dev)の改善に重点を置いていますが、[区切り文字コンポーネント](/help/components/separator.md)の機能強化も含まれています。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8 | 2019 年 3 月 14 日（PT） |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | このリリースでは[コンポーネントライブラリ](https://aemcomponents.dev)の改善に重点を置き、新しい[区切り文字コンポーネント](/help/components/separator.md)を導入したほか、[画像コンポーネント](/help/components/image.md)の機能強化も含まれています。 | 6.4.2.0 以上 | - | - | 8 | 2019 年 2 月 11 日（PT） |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | このリリースは主にバグ修正に重点を置いていますが、[カルーセルコンポーネント](/help/components/carousel.md)の機能強化も含まれています。 | 6.4.2.0 以上 | - | - | 8 | 2018 年 11 月 27 日（PT） |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | このリリースでは、[タブコンポーネント](/help/components/tabs.md)と[カルーセルコンポーネント](/help/components/carousel.md)が導入されたほか、[画像コンポーネント](/help/components/image.md)、[ページコンポーネント](/help/components/page.md)、[タイトルコンポーネント](/help/components/title.md)が改善され、トラッキング機能も強化されました。 | 6.4.2.0 以上 | - | - | 8 | 2018 年 10月 16 日（PT） |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | このリリースでは、[ティーザーコンポーネント](/help/components/teaser.md)が導入されたほか、[画像コンポーネント](/help/components/image.md)の改善と多数のバグ修正が行われました。 | 6.4.2.0 以上 | - | - | 8 | 2018 年 7 月 13 日（PT） |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | バグ修正リリース。 | 6.4.0.0 以上 | - | - | 8 | 2018 年 6 月 12 日（PT） |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | このリリースでは、内部的な改善、バグ修正、小規模な改善（[画像コンポーネント](/help/components/image.md)での画像反転のサポートなど）が追加されました。 | 6.4.0.0 以上 | - | - | 8 | 2018 年 4 月 11 日（PT） |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | このリリースでは主に、内部的な改善とバグの修正に加えて、[画像コンポーネント](/help/components/image.md)、[ページコンポーネント](/help/components/page.md)、[コンテンツフラグメントコンポーネント](/help/components/content-fragment-component.md)のマイナーな改善にも重点を置いています。 | 6.4.0.0 以上 | - | - | 8 | 2018 年 3 月 7 日（PT） |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | このリリースでは、[ナビゲーションコンポーネント](/help/components/navigation.md)、[言語ナビゲーションコンポーネント](/help/components/language-navigation.md)、[クイック検索コンポーネント](/help/components/quick-search.md)が導入されたほか、すべてのコンポーネントに[スタイルシステム](/help/get-started/authoring.md#component-styling)が実装されました。 | 6.4.0.0 以上 | - | - | 8 | 2018 年 1 月 16 日（PT） |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | このリリースでは、すべてのコンポーネントに JSON 形式での書き出しが実装されたほか、[コンテンツフラグメントコンポーネント](/help/components/content-fragment-component.md)が導入されました。 | 6.4.0.0 以上 | - | - | 8 | 2017 年 10月 10 日（PT） |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | このリリースでは、[画像コンポーネント](/help/components/image.md)の修正がいくつか追加されています。 | 6.4.0.0 以上 | - | - | 8 | 2017 年 8 月 4 日（PT） |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | このリリースでは、[ページコンポーネント](/help/components/page.md)と[画像コンポーネント](/help/components/image.md)の修正のほか、様々なグローバル修正および改善が行われました。 | 6.4.0.0 以上 | - | - | 8 | 2017 年 4 月 26 日（PT） |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | このリリースでは、[画像コンポーネント](/help/components/image.md)のアニメーション GIF 画像に関する修正が追加されました。 | 6.4.0.0 以上 | - | - | 7 | 2017 年 3 月 22 日（PT） |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | コアコンポーネントの初回リリースです。。 | 6.4.0.0 以上 | - | - | 7 | 2017 年 3 月 20 日（PT） |

>[!NOTE]
>
>（*）バージョン 2.11.0 以降、`org.apache.sling.models.impl` バージョン 1.4.12 以降が必要です（[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781) のため）。これは、将来のサービスパックで AEM 6.4 および 6.5 に対して提供される予定です。それまでは、Sling Models バンドルが `core.wcm.components.all` パッケージに含まれます。

>[!TIP]
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
| **[進行状況バー](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 |
| **[PDF ビューア](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## バージョンとリリース {#versions-and-releases}

コアコンポーネントは GitHub を通じて配布されます。これにより、アドビはより迅速にコンポーネントに機能を追加できるほか、AEM リリースサイクル以外でコミュニティからの入力を取り入れることもできます。

コアコンポーネントは、互換性のある定義済みの AEM バージョンで使用できます。つまり、1 つの AEM バージョンがコアコンポーネントの複数のバージョンまたはリリースをサポートしている場合があります。その結果、以前の基盤コンポーネントよりも柔軟性が高くなっています。基盤コンポーネントは AEM の特定のバージョンに結び付いていました。

### バージョン {#versions}

コアコンポーネントの主要な反復が&#x200B;**バージョン**&#x200B;です。各コンポーネントにはバージョンがあります。バージョンは、v1 や v2 のように、**v** の後に正の整数が付いた形式で示されます。バージョンは、下位互換性のない変更の場合にのみ増えます。これは、通常、新しい特長や機能が導入される場合です。

開発者や管理者は、リソースタイプパスや実装の完全修飾 Java クラス名に含まれている数字で、コアコンポーネントのバージョンを認識できます。このバージョン番号は、[セマンティックバージョニングガイドライン](https://semver.org/)で定義されたメジャーバージョンを表します。

コアコンポーネントバージョンについて詳しくは、[コアコンポーネントの開発者向けドキュメント](developing/guidelines.md)を参照してください。

### リリース {#releases}

コアコンポーネントは&#x200B;**リリース**&#x200B;を通じて使用できるようになり、[GitHub で実際に入手可能な公開済みアーティファクトを表します](https://github.com/adobe/aem-core-wcm-components/releases)。リリースは、すべてのコアコンポーネントを配信可能なパッケージとしてまとめたもので、X.Y.Z 形式の 10 進数で示されます。

* **メジャーリリース**&#x200B;では、既存コンポーネントの新しいバージョンのほか、まったく新しいコンポーネントおよび通常のバグ修正を取り入れることができます。これは、リリース番号の X 部分のインクリメントで表されます。
* **重要リリース**&#x200B;では、コンポーネントの既存バージョンに新しい機能を導入できるほか、バグ修正を行うことができます。これは、リリース番号の Y 部分のインクリメントで表されます。
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
