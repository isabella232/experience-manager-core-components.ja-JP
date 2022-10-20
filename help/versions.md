---
title: コアコンポーネントのバージョン
description: コアコンポーネントはリリースとして公開されます。これらのリリースには、同じコアコンポーネントの複数のバージョンが含まれている場合があります。このドキュメントでは、リリースとバージョンの概要、およびコアコンポーネントと AEM の互換性を理解する方法について説明します。
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 1e449c2b3c8fb9a98093c6731455089e8a157015
workflow-type: tm+mt
source-wordcount: '2780'
ht-degree: 98%

---

# コアコンポーネントのバージョン {#core-components-versions}

コアコンポーネントの現在のリリースは 2.20.6 で、[AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja) および[オンプレミス AEM](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=ja) のインストールと互換性があります。

## リリース履歴と互換性 {#release-history-and-compatibility}

コアコンポーネントは、柔軟性を備え、サポートされるすべての AEM バージョンと互換性があるように設計されています。このため、コンポーネントの 1 つのリリースに同じコンポーネントの複数のバージョンを含めることができます。

コアコンポーネントの各リリースの互換性、およびリリースとそこに含まれているコンポーネントバージョンの対応関係を以下の表に示します。

### リリース履歴と要件 {#release-history-requirements}

次の表は、コアコンポーネントの各リリースと AEM リリースおよび Java バージョンとの互換性の概要を示しています（[各リリースの詳細については GitHub を参照してください](https://github.com/adobe/aem-core-wcm-components/releases)）。

| リリース | 説明 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | リリース日 |
|---|---|---|---|---|---|---|
| [2.21.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.2) | これは、v1 および v2 の問題を修正するパッチリリースです [ティーザーコンポーネント。](/help/components/teaser.md) | - | 6.5.13.0+ * | 継続的 | 8、11 | 2022年9月12日（PT） |
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | このリリースには、LinkHandler API の公開、 [画像コンポーネント](/help/components/image.md) および [データレイヤー](/help/developing/data-layer/overview.md) と、マルチパネルコンポーネントの改善を追加しました。 | - | 6.5.13.0以降* | 継続的 | 8、11 | 2022年9月12日（PT） |
| [2.20.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.8) | このリリースでは、AdaptiveImageServlet を使用した SVG 画像の配信に関する問題が修正されています。 | - | 6.5.13.0以降* | 継続的 | 8、11 | 2022年8月4日（PT） |
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | このパッチリリースでは、新しい[目次コンポーネント](/help/components/tableofcontents.md)の問題が修正されています。 | - | 6.5.13.0以降* | 継続的 | 8、11 | 2022年7月7日（PT） |
| --- | — | — | — | — | — | — |
| [2.20.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.4) | このパッチリリースでは、新しい[目次コンポーネント](/help/components/tableofcontents.md)の問題が修正されています。 | - | 6.5.13.0以降* | 継続的 | 8、11 | 2022年6月29日（PT） |
| — | — | — | — | — | — | — |
| [2.20.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.2) | これは、AEMaaCS の新しい [web に最適化されたアセット配信サービス](/help/developing/web-optimized-image-delivery.md)の問題を修正するパッチリリースです。 | - | 6.5.13.0以降* | 継続的 | 8、11 | 2022年6月20日（PT） |
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | このリリースでは、新しい[目次コンポーネント](/help/components/tableofcontents.md)が追加され、AEMaaCS の [web に最適化されたアセット配信サービス](/help/developing/web-optimized-image-delivery.md)がサポートされるようになり、バグ修正が含まれています。 | - | 6.5.13.0以降* | 継続的 | 8、11 | 2022年6月9日（PT） |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | このリリースでは、[検索コンポーネント](/help/components/quick-search.md) の新しいバージョンや[ボタンコンポーネント](/help/components/button.md)の機能を追加し、多くのアクセシビリティの改善とバグの修正も行いました。 | - | 6.5.10.0+ * | 継続的 | 8、11 | 2022年4月7日（PT） |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | このリリースでは AEMaaCS の問題が修正されました。 | - | 6.5.10.0以降* | 継続的 | 8、11 | 2022年3月17日（PT） |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | これはパッチリリースです。 | - | 6.5.10.0以降* | 継続的 | 8、11 | 2022年3月3日（PT） |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | コアコンポーネントのこのメジャーリリースでは、複数コンポーネントの新しいバージョンに新しいリンクハンドラーが導入されたほか、アクセシビリティに関する多くの改善とバグ修正が行われました。 | - | 6.5.10.0以降* | 継続的 | 8、11 | 2022年2月16日（PT） |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | これはパッチリリースです。 | 6.4.8.4+ * | 6.5.6.0+ * | 継続的 | 8、11 | 2021年12月13日（PT） |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | これは、以前のリリースに起因するリグレッションを修正するパッチリリースです。 | 6.4.8.4 以上* | 6.5.6.0 以上* | 継続的 | 8、11 | 2021年1月10日（PT） |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | このパッチは、[リスト](/help/components/list.md)および[ナビゲーション](/help/components/navigation.md)コンポーネントを強化し、リダイレクトターゲット用の外部 URL を表示し、今後の[ティーザー](/help/components/teaser.md)コンポーネント v2 のページ画像の継承を有効にし、追加のバグ修正を含みます。 | 6.4.8.4 以上* | 6.5.6.0 以上* | 継続的 | 8、11 | 2021年8月31日（PT） |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | このパッチリリース以前に導入された、後方互換性のない変更を修正するためのパッチリリースです。 | 6.4.8.4 以上* | 6.5.6.0 以上* | 継続的 | 8、11 | 2021年8月2日（PT） |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | このパッチリリースでは、ページのサイトマップのサポートが追加され、様々なアクセシビリティの改善が含まれています。 | 6.4.8.4 以上* | 6.5.6.0 以上* | 継続的 | 8、11 | 2021年7月29日（PT） |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | このパッチリリースには、AEMaaCS で動作しない[データレイヤー](/help/developing/data-layer/overview.md)の修正が含まれています。 | 6.4.8.4 以上* | 6.5.6.0 以上* | 継続的 | 8、11 | 2021年7月8日（PT） |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | このリリースには、リンクハンドラー機能をサポートする多数の新しいコンポーネントバージョンのテクニカルプレビューと、[ページコンポーネント](/help/components/page.md)の画像機能のテクニカルプレビューが含まれています。いくつかのバグ修正も含まれています。 | 6.4.8.4 以上* | 6.5.6.0 以上* | 継続的 | 8、11 | 2021年6月16日（PT） |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 新しいリンクハンドラーの問題を修正するためのパッチリリースです。 | 6.4.8.1+ * | 6.5.5.0+ * | 継続的 | 8、11 | 2021年5月19日（PT） |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 主に新しいリンクハンドラーの問題を修正するパッチリリースです。[PWA](/help/components/page.md#pwa-support) 用の複数ページアプリケーションをサポートするための機能が追加されました。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2021年5月15日（PT） |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | このリリースでは、アクセシビリティの向上と、既存のコンポーネントに対する新しいリンクハンドラーの導入に焦点を当てています。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2021年4月22日（PT） |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | これは、主に[データレイヤー](/help/developing/data-layer/overview.md)の下位互換性の問題と、特定の状況で IT テストが失敗する問題を修正するパッチリリースでした。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2021年3月16日（PT） |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | このリリースでは、[プログレッシブ ｗeb アプリ（PWA）がページコンポーネント](/help/components/page.md#pwa-support)でサポートされているほか、[Adobe データレイヤー](/help/developing/data-layer/overview.md)のバージョン 2.0.0 がサポートされています。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2021年2月23日（PT） |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | このリリースには、[埋め込みコンポーネント](/help/components/embed.md)の新しいオプションが含まれています。また、[ページ](/help/components/page.md)レベルでブランドスラッグが導入されているほか、多くの問題にも対処しています。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2021年2月9日（PT） |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | これは、AEMaaCS で RTE を使用した場合の問題に対処するためのパッチリリースでした。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2020年12月16日（PT） |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | このリリースには、[画像コンポーネント](/help/components/image.md)の新しい Dynamic Media 機能が含まれています。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2020年12月4日（PT） |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | これは、2.12.0 のパッチリリースで、マイナーな修正が含まれています。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2020年11月11日（PT） |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | これは2.12.0のパッチリリースで、[画像コンポーネント](/help/components/image.md)の重大なバグを修正しました。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2020年11月5日（PT） |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | このリリースでは、[新しい POST フォームハンドラ](/help/components/forms/form-container.md#post-data)、カスタム CSS、JavaScript、メタデータ[タグをコンテキストに応じた設定で組み込む](/help/developing/including-clientlibs.md#context-aware-loading)機能、[カスタムコンポーネントでデータレイヤーとの統合を簡単に行う](/help/developing/data-layer/integrations.md#enabling-custom-components)ための `DataLayerBuilder` ユーティリティが導入されました。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2020年10月29日（PT） |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | このリリースでは、[AMP のサポート](/help/developing/amp.md)が導入されました。 | 6.4.8.1 以上* | 6.5.5.0 以上* | 継続的 | 8、11 | 2020年7月20日（PT） |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | このリリースでは、[PDF ビューアコンポーネント](/help/components/pdf-viewer.md)が導入されました。 | 6.4.8.1+ | 6.5.5.0+ | 継続的 | 8、11 | 2020年6月17日（PT） |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | このリリースでは、[Adobe Client Data Layer](/help/developing/data-layer/overview.md) との統合が可能になり、[プログレスバーコンポーネント](/help/components/progress-bar.md)が導入されました。 | 6.4.8.0+ | 6.5.4.0+ | 継続的 | 8、11 | 2020年5月29日（PT） |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | このリリースでは小規模の機能強化による修正に重点を置きました。 | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019年12月5日（PT） |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | このリリースでは、新しい[埋め込みコンポーネント](/help/components/embed.md)が導入されました。 | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019年9月25日（PT） |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | このリリースでは、新しい[エクスペリエンスフラグメントコンポーネント](/help/components/experience-fragment.md)が導入されました. | 6.4.4.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019年9月6日（PT） |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | このリリースでは、[アコーディオン](/help/components/accordion.md)、[ボタン](/help/components/button.md)、[コンテナ](/help/components/container.md)、[ダウンロード](/help/components/download.md)の各コンポーネントが新しく導入されました。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019年6月25日（PT） |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | このリリースでは、[コンテンツフラグメントリストコンポーネント](/help/components/content-fragment-list.md)が導入されました。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8、11 | 2019年5月7日（PT） |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | このリリースでは[コンポーネントライブラリ](https://aemcomponents.dev)の改善に重点を置いていますが、[区切り文字コンポーネント](/help/components/separator.md)の機能強化も含まれています。 | 6.4.2.0 以上 | 6.5.0.0 以上 | 継続的 | 8 | 2019年3月14日（PT） |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | このリリースでは[コンポーネントライブラリ](https://aemcomponents.dev)の改善に重点を置き、新しい[区切り文字コンポーネント](/help/components/separator.md)を導入したほか、[画像コンポーネント](/help/components/image.md)の機能強化も含まれています。 | 6.4.2.0 以上 | - | - | 8 | 2019年2月11日（PT） |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | このリリースは主にバグ修正に重点を置いていますが、[カルーセルコンポーネント](/help/components/carousel.md)の機能強化も含まれています。 | 6.4.2.0 以上 | - | - | 8 | 2018年11月27日（PT） |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | このリリースでは、[タブコンポーネント](/help/components/tabs.md)と[カルーセルコンポーネント](/help/components/carousel.md)が導入されたほか、[画像コンポーネント](/help/components/image.md)、[ページコンポーネント](/help/components/page.md)、[タイトルコンポーネント](/help/components/title.md)が改善され、トラッキング機能も強化されました。 | 6.4.2.0 以上 | - | - | 8 | 2018年10月16日（PT） |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | このリリースでは、[ティーザーコンポーネント](/help/components/teaser.md)が導入されたほか、[画像コンポーネント](/help/components/image.md)の改善と多数のバグ修正が行われました。 | 6.4.2.0 以上 | - | - | 8 | 2018年7月13日（PT） |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | バグ修正リリース。 | 6.4.0.0 以上 | - | - | 8 | 2018年6月12日（PT） |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | このリリースでは、内部的な改善、バグ修正、小規模な改善（[画像コンポーネント](/help/components/image.md)での画像反転のサポートなど）が追加されました。 | 6.4.0.0 以上 | - | - | 8 | 2018年4月11日（PT） |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | このリリースでは主に、内部的な改善とバグの修正に加えて、[画像コンポーネント](/help/components/image.md)、[ページコンポーネント](/help/components/page.md)、[コンテンツフラグメントコンポーネント](/help/components/content-fragment-component.md)のマイナーな改善にも重点を置いています。 | 6.4.0.0 以上 | - | - | 8 | 2018年3月7日（PT） |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | このリリースでは、[ナビゲーションコンポーネント](/help/components/navigation.md)、[言語ナビゲーションコンポーネント](/help/components/language-navigation.md)、[クイック検索コンポーネント](/help/components/quick-search.md)が導入されたほか、すべてのコンポーネントに[スタイルシステム](/help/get-started/authoring.md#component-styling)が実装されました。 | 6.4.0.0 以上 | - | - | 8 | 2018年1月16日（PT） |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | このリリースでは、すべてのコンポーネントに JSON 形式での書き出しが実装されたほか、[コンテンツフラグメントコンポーネント](/help/components/content-fragment-component.md)が導入されました。 | 6.4.0.0 以上 | - | - | 8 | 2017年10月10日（PT） |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | このリリースでは、[画像コンポーネント](/help/components/image.md)の修正がいくつか追加されています。 | 6.4.0.0 以上 | - | - | 8 | 2017年8月4日（PT） |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | このリリースでは、[ページコンポーネント](/help/components/page.md)と[画像コンポーネント](/help/components/image.md)の修正のほか、様々なグローバル修正および改善が行われました。 | 6.4.0.0 以上 | - | - | 8 | 2017年4月26日（PT） |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | このリリースでは、[画像コンポーネント](/help/components/image.md)のアニメーション GIF 画像に関する修正が追加されました。 | 6.4.0.0 以上 | - | - | 7 | 2017年3月22日（PT） |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | コアコンポーネントの初回リリースです. | 6.4.0.0 以上 | - | - | 7 | 2017年3月20日（PT） |

>[!NOTE]
>
>（*）バージョン 2.11.0 以降、`org.apache.sling.models.impl` バージョン 1.4.12 以降が必要です（[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781) のため）。これは、将来のサービスパックで AEM 6.4 および 6.5 に対して提供される予定です。それまでは、Sling Models バンドルが `core.wcm.components.all` パッケージに含まれます。

>[!TIP]
>
>AEM の場合と同様に、最新の修正および機能を活用するために、実行している AEM バージョンと互換性のある入手可能な[最新のリリースおよびバージョンのコアコンポーネント](https://github.com/adobe/aem-core-wcm-components/releases/latest)を開発に使用することをお勧めします。

### コンポーネントのバージョンとリリース {#component-versions-and-releases}

コアコンポーネントの各リリースと、そこに含まれている各コンポーネントのバージョンを次の表に示します。

|  | リリース 1.0.0 ～ 1.0.6 | リリース 1.1.0 | リリース 2.0.0 ～ 2.0.8 | リリース 2.1.0 | リリース 2.2.0 ～ 2.2.0 | リリース 2.3.0 ～ 2.3.2 | リリース 2.4.0 | リリース 2.5.0 | リリース 2.6.0 | リリース 2.7.0 ～ 2.8.0 | リリース 2.9.0～2.17.14 | リリース 2.18.0 | リリース 2.19.0 | リリース 2.20.0 以上 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **[ページ](components/page.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[タイトル](components/title.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[画像](components/image.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[リスト](components/list.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[パンくず](components/breadcrumb.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[ソーシャルメディア共有](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、非推奨 | v1、非推奨 | v1、非推奨 |
| **[フォームコンテナ](components/forms/form-container.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームテキスト](components/forms/form-text.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームオプション](components/forms/form-options.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォーム非表示](components/forms/form-hidden.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[フォームボタン](components/forms/form-button.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[コンテンツフラグメント](components/content-fragment-component.md)** |  | サンドボックス | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[ナビゲーション](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[言語ナビゲーション](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[クイック検索](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 |
| **[ティーザー](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[タブ](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[カルーセル](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[区切り文字](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[コンテンツフラグメントリスト](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[アコーディオン](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[ボタン](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[コンテナ](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[ダウンロード](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[エクスペリエンスフラグメント](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[埋め込み](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[プログレスバー](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[PDF ビューア](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[目次](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 |

## バージョンとリリース {#versions-and-releases}

コアコンポーネントは GitHub を通じて配布されます。これにより、アドビはより迅速にコンポーネントに機能を追加できるほか、AEM リリースサイクル以外でコミュニティからの入力を取り入れることもできます。

コアコンポーネントは、互換性のある定義済みの AEM バージョンで使用できます。つまり、1 つの AEM バージョンがコアコンポーネントの複数のバージョンまたはリリースをサポートしている場合があります。

### バージョン {#versions}

コアコンポーネントの主要な反復が&#x200B;**バージョン**&#x200B;です。各コンポーネントにはバージョンがあります。バージョンは、v1 や v2 のように、**v** の後に正の整数が付いた形式で示されます。バージョンは、下位互換性のない変更の場合にのみ増えます。これは、通常、新しい特長や機能が導入される場合です。

開発者や管理者は、リソースタイプパスや実装の完全修飾 Java クラス名に含まれている数字で、コアコンポーネントのバージョンを認識できます。このバージョン番号は、[セマンティックバージョニングガイドライン](https://semver.org/)で定義されたメジャーバージョンを表します。

コアコンポーネントバージョンについて詳しくは、[コアコンポーネントの開発者向けドキュメント](developing/guidelines.md)を参照してください。

### リリース {#releases}

コアコンポーネントは&#x200B;**リリース**&#x200B;を通じて使用できるようになり、 [GitHub で実際に入手可能な公開済みアーティファクトを表します。](https://github.com/adobe/aem-core-wcm-components/releases)リリースは、すべてのコアコンポーネントを配信可能なパッケージとしてまとめたもので、`X.Y.Z` 形式の 10 進数で示されます。

* **メジャーリリース**&#x200B;では、まったく新しいコンポーネント、既存バージョンのコンポーネントの改善、標準のバグ修正が導入されています。これは、リリース番号の `X` 部分の増分で表されます。
* **マイナーリリース**&#x200B;では、新しいコンポーネント、既存バージョンのコンポーネントに対する新しい機能、バグ修正が導入されています。これは、リリース番号の `Y` 部分の増分で表されます。
* **パッチリリース**&#x200B;には、バグ修正のみ含まれています。これは、リリース番号の `Z` 部分の増分で表されます。

>[!NOTE]
>
>リリースには、同じコンポーネントの複数のバージョンを含めることができます。
>
>同じバージョンのコンポーネントが複数のリリースに現れることがあります。

## コアコンポーネントのサポート {#core-components-support}

コアコンポーネントは AEM に不可欠な部分なので、クイックスタートの一部として提供された場合と同じ利用条件でサポートされます。

他の製品機能と同じく、提供終了の一般的なルールは次のようになります。

* コンポーネントは、削除される前に、非推奨になったことが事前に通知されます
* 早ければその通知の後、AEM リリースからコンポーネントが削除されます。

したがって、新しいバージョンのコンポーネントへの移行を検討するユーザーに対し、サポートが終了するまでの期間として少なくとも 1 つのリリースサイクルが与えられることになります。

各コンポーネントのバージョンには、サポートされる AEM バージョンが明記されています。ある AEM バージョンのサポートが停止されると、その AEM バージョンでのコアコンポーネントのサポートも停止されます。

コンポーネントのカスタマイズのサポートについて詳しくは、関連するコアコンポーネントバージョンの[コアコンポーネントのカスタマイズ](developing/customizing.md)ページを参照してください。

## 基盤コンポーネントのサポート {#foundation-component-support}

Adobe の開発における重点は、コアコンポーネントに移行し、新機能の追加は今後も続けられます。

[ほとんどの基盤コンポーネントは AEM 6.5 では非推奨となり](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html?lang=ja)、今後は基盤コンポーネントに関する主なバグ修正のみが検討されます。
