---
title: コアコンポーネントの概要
description: '堅牢で拡張可能な基本コンポーネントとして導入されたコアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築されています。 '
translation-type: tm+mt
source-git-commit: 1c6e27c163f72fd66336e8db883144dc4dd60510

---


# コアコンポーネントの概要{#core-components-introduction}

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。コンポーネントは常に AEM エクスペリエンスの基本要素となってきました。作成者はコンポーネントを使用することで単純かつ強力にページを作成し、開発者は柔軟かつ拡張可能なコンポーネントを開発できます。

コアコンポーネントは、AEM で Web サイトの開発時間を短縮しメンテナンスコストを削減するための、標準化された Web コンテンツ管理（WCM）コンポーネントのセットです。

## リソース {#resources}

* **[コンポーネントライブラリ：](https://www.adobe.com/go/aem_cmp_library_jp)**コンポーネントを様々な設定で表示する例を集めたものです。
* **コンポーネントのドキュメント（本ドキュメント）：**&#x200B;開発者および作成者向けに、各コンポーネントの詳細を説明しています。
* 入門ガイド：
   * **[コアコンポーネントを利用したプロジェクトの成功への道筋：](/help/developing/success.md)**コアコンポーネントを使用するプロジェクトを開始する前に十分考慮すべきガイドラインです。
   * **[WKND チュートリアル：](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**新しいサイトの構築に関する 2 日間のチュートリアルです。
   * **[Adobe Summit のチュートリアル：](https://expleague.azureedge.net/labs/L767/index.html)**新しいサイトの構築に関する 2 時間のチュートリアルです（US Summit 2019 のラボの内容）。
   * **[Gems Web セミナー：](https://helpx.adobe.com/jp/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**コアコンポーネントのガイドツアー（2018 年 12 月に録画）

## 特長 {#features}

|  |  |
|---|---|
| 本番で使用可能 | コアコンポーネントは27の堅牢なコンポーネントで、よくテストされ、広く使用され、パフォーマンスが優れています。 |
| クラウド対応 | Whether on [AEM as a Cloud Service](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html), on [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams), or on-premise, they just work. |
| 用途が広い | コンポーネントは、作成者がほとんどすべてのレイアウトを組み立てることができる一般的な概念を表します。 |
| 設定可能 | Template-level [content policies](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/developing/platform/templates/page-templates-editable.html#content-policies) define which features the page authors are allowed to use or not use. |
| 高いアクセシビリティ | They comply [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), provide ARIA labels, and support keyboard navigation ([known issues](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO対応 | The HTML output is semantic and provides [schema.org](https://schema.org) microdata annotations. |
| WebApp-Ready | The [streamlined JSON output](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) allows client-side rendering, still with a possibility of [in-context editing](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| デザインキット | A [UI kit for Adobe XD](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) allows designers to create wireframes that they can then [style as needed](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_WKND.xd). |
| Themeable | The components implement the [Style System](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/developing/components/style-system.html), and the markup follows [BEM CSS conventions](http://getbem.com/). |
| カスタマイズ可能 | Several patterns allow [easy customization](developing/customizing.md), from adjusting the HTML to advanced functionality reuse. |
| バージョン管理 | The [versioning policy](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) ensures that the Core Components won&#39;t break your site when improving things that might impact you. |
| ローカライズ可能 | Smart reference resolution allows certain components to find and [render corresponding localized content automatically](get-started/localization.md). |
| オープンソース | If something is not as it should, [contribute your improvements!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## コンポーネント{#the-components}

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

### テンプレートコンポーネント {#template-components}

* [ページ](components/page.md)
* [ナビゲーション](components/navigation.md)
* [言語ナビゲーション](components/language-navigation.md)
* [パンくず](components/breadcrumb.md)
* [クイック検索](components/quick-search.md)

### ページオーサリングコンポーネント {#page-authoring-components}

* [タイトル](components/title.md)
* [テキスト](components/text.md)
* [画像](components/image.md)
* [ボタン](components/button.md)
* [ティーザー](components/teaser.md)
* [ダウンロード](components/download.md)
* [リスト](components/list.md)
* [エクスペリエンスフラグメント](components/experience-fragment.md)
* [コンテンツフラグメント](components/content-fragment-component.md)
* [コンテンツフラグメントリスト](components/content-fragment-list.md)
* [埋め込み](components/embed.md)
* [ソーシャルメディア共有](components/sharing.md)
* [区切り文字](components/separator.md)

### コンテナコンポーネント {#container-components}

* [コンテナ](components/container.md)
* [カルーセル](components/carousel.md)
* [タブ](components/tabs.md)
* [アコーディオン](components/accordion.md)

### フォームコンポーネント {#form-components}

* [フォームコンテナ](components/forms/form-container.md)
* [フォームテキスト](components/forms/form-text.md)
* [フォームオプション](components/forms/form-options.md)
* [フォーム非表示](components/forms/form-hidden.md)
* [フォームボタン](components/forms/form-button.md)

>[!NOTE]
>
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](get-started/using.md)。統合されると、[テンプレートエディター](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/templates.html)で使用できるようになり、事前設定されます。

>[!NOTE]
>
>個々のコアコンポーネントの一部のバージョンは、特定のバージョンの AEM とのみ互換性があります。
>
>互換性の情報については、特定のコンポーネントに対する個々のヘルプページ（前の一覧にリンクされています）を参照するか、[コアコンポーネントバージョン](versions.md)ドキュメントで詳細を確認してください。

## システム要件 {#system-requirements}

| コアコンポーネント | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | AEM 6.3 | Java SE | Maven |
---------|---------|---------|---------|---------|---------|---------
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 継続的 | 6.5.0.0 以上 | 6.4.4.0 以上 | 6.3.3.4 以上 | 8、11 | 3.3.9 以上 |

以前のコアコンポーネントリリースの要件については、[コアコンポーネントのバージョン](versions.md)を参照してください。

コアコンポーネントでは、[編集可能なテンプレート](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)を使用する必要があり、クラシック UI や静的テンプレートはサポートされていません。必要に応じて、[AEM Modernization Tools](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) を使用して、これらの最新の AEM 機能をプロジェクトに反映します。

ローカルの開発環境をセットアップするには、[AEM as a Cloud Service SDK の場合はこの概要](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)を、[旧バージョンの AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html) の場合は本ドキュメントを、それぞれを参照してください。
