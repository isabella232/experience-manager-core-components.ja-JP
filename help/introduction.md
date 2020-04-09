---
title: コアコンポーネントの概要
description: '堅牢で拡張可能な基本コンポーネントとして導入されたコアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築されています。 '
translation-type: tm+mt
source-git-commit: 71c1cca664dde91968df16848650df9f0f0a5218

---


# コアコンポーネントの概要{#core-components-introduction}

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。コンポーネントは常に AEM エクスペリエンスの基本要素となってきました。作成者はコンポーネントを使用することで単純かつ強力にページを作成し、開発者は柔軟かつ拡張可能なコンポーネントを開発できます。

コアコンポーネントは、AEMの標準化されたWebコンテンツ管理(WCM)コンポーネントのセットで、開発時間を短縮し、Webサイトのメンテナンスコストを削減します。

## リソース {#resources}

* **[コンポーネントライブラリ：](https://www.adobe.com/go/aem_cmp_library)**コンポーネントを様々な設定で表示するための例のコレクションです。
* **コンポーネントのドキュメント(このドキュメント):** 開発者および作成者向け。各コンポーネントの詳細を含みます。
* はじめに:
   * **[コアコンポーネントの成功：](/help/developing/success.md)**コアコンポーネントを使用するプロジェクトの開始前に十分考慮すべきガイドラインです。
   * **[WKNDチュートリアル：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**新しいサイトを作成するための2日間のチュートリアルです。
   * **[Summit Tutorial:](https://expleague.azureedge.net/labs/L767/index.html)**新しいサイトを構築するための2時間のチュートリアル（US Summit 2019のラボから）。
   * **[Gemsウェビナー：](https://helpx.adobe.com/jp/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**コアコンポーネントのガイドツアー（2018年12月に記録）

## 機能 {#features}

||||—|—||実稼働環境に対応|コアコンポーネントは27の堅牢なコンポーネントで、テストが適しており、広く使用されており、パフォーマンスが優れています。||Cloud-Ready| [AEM上でクラウドサービスとして、](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html)[](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)Adobe Managed Services上、オンプレミスのどちらでも、動作します。||汎用|コンポーネントは、作成者がほとんどすべてのレイアウトを組み立てることができる一般的な概念を表します。||設定可能|テンプレートレベルのコ [ンテンツポリシー](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/page-templates-editable.html#content-policies) 。ページ作成者が使用できる機能と使用できない機能を定義します。|
|Accessible| They comply [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), provide ARIA labels, and support keyboard navigation ([known issues](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)).|
|SEO-Friendly| The HTML output is semantic and provides [schema.org](https://schema.org) microdata annotations.||WebApp-Ready|合理化されたJSON [出力により](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) 、クライアント側でのレンダリングが可能になり、コンテキスト [内編集も可能です](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。||デザインキット| Adobe XD用 [UIキットを使用すると](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) 、デザイナーはワイヤフレームを作成し、必要に応じてスタ [イル設定できます](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_WKND.xd)。|
|Themeable| The components implement the [Style System](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/style-system.html), and the markup follows [BEM CSS conventions](http://getbem.com/).||カスタマイズ可能| HTMLの調整から高度な機 [能の再利用まで](developing/customizing.md)、いくつかのパターンをカスタマイズしやすくなっています。||バージョン管理|バージ [ョン管理ポリシーは](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 、影響を及ぼす可能性のある改善の際に、コアコンポーネントがサイトを壊さないようにします。|
|Localizable|Smart reference resolution allows certain components to find and [render corresponding localized content automatically](get-started/localization.md).||オープンソース|必要に応じて何かがない場合は、改 [善点にご協力ください。](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md)|

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

### コンテナの構成要素 {#container-components}

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
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 継続的 | 6.5.0.0 以上 | 6.4.4.0 以上 | 6.3.3.4 以上 | 8、11 | 3.3.9+ |

以前のコアコンポーネントリリースの要件については、コアコンポーネントのバージ [ョンを参照してくださ](versions.md)い。

コアコンポーネントでは、編集可能なテンプレー [トの使用が必要で](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) 、クラシックUIや静的テンプレートはサポートされません。 必要に応じて、 [AEM Modernization Toolsを確認して](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) 、これらの最新のAEM機能でプロジェクトを更新します。

ローカルの開発環境を設定するには、AEMの概要を [クラウドサービスSDKとして、またはこのドキュメントを使用して](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) 、AEMの古いバー [ジョンを設定する必要があります](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。
