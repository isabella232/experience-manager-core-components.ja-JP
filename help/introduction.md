---
title: コアコンポーネントの概要
description: 'コアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築され、堅牢で拡張可能な基本コンポーネントを提供します。 '
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: 5271174f5c325a9793dc155c763054752c7308b8
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 100%

---

# コアコンポーネントの概要{#core-components-introduction}

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。コンポーネントは常に AEM エクスペリエンスの基本要素となってきました。作成者はコンポーネントを使用することで単純かつ強力にページを作成し、開発者は柔軟かつ拡張可能なコンポーネントを開発できます。

コアコンポーネントは、AEM で Web サイトの開発時間を短縮しメンテナンスコストを削減するための、標準化された Web コンテンツ管理（WCM）コンポーネントのセットです。

## リソース {#resources}

* **[コンポーネントライブラリ：](https://www.adobe.com/go/aem_cmp_library_jp)**&#x200B;コンポーネントを様々な設定で表示する例を集めたものです。
* **コンポーネントのドキュメント（本ドキュメント）：**&#x200B;開発者および作成者向けに、各コンポーネントの詳細を説明しています。
* **[コアコンポーネント GitHub リポジトリー：](https://github.com/adobe/aem-core-wcm-components)**&#x200B;開発者向けに、各コンポーネントおよびプロジェクトのダウンロードの詳細を説明しています。
* 入門ガイド：
   * **[コアコンポーネントを利用したプロジェクトの成功への道筋：](/help/developing/success.md)**&#x200B;コアコンポーネントを使用するプロジェクトを開始する前に十分考慮すべきガイドラインです。
   * **[WKND チュートリアル：](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**&#x200B;新しいサイトの構築に関する 2 日間のチュートリアルです。
   * **[Adobe Summit のチュートリアル：](https://expleague.azureedge.net/labs/L767/index.html)**&#x200B;新しいサイトの構築に関する 2 時間のチュートリアルです（US Summit 2019 のラボの内容）。
   * **[Gems Web セミナー：](https://helpx.adobe.com/jp/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**&#x200B;コアコンポーネントのガイドツアー（2018 年 12 月に録画）

## 機能 {#features}

|  |  |
|---|---|
| 本番で使用可能 | コアコンポーネントは 28 個の堅牢なコンポーネントで、十分にテストされ、広く使用されており、パフォーマンスが優れています。 |
| クラウド対応 | [AEM as a Cloud Service](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html)、[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)、オンプレミスのどれでも動作します。 |
| 用途が広い | コンポーネントは、ほぼあらゆるレイアウトの作成に作成者が使用できる汎用的な概念を表します。 |
| 設定可能 | ページ作成者が使用できる機能と使用できない機能をテンプレートレベルの[コンテンツポリシー](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies)で定義します。 |
| 追跡可能 | [Adobe Client Data Layer との統合](/help/developing/data-layer/overview.md)により、訪問者エクスペリエンスのあらゆる側面を追跡できます。 |
| 高いアクセシビリティ | [WCAG 2.1 標準](https://www.w3.org/TR/WCAG21/)に準拠し、ARIA ラベルを提供し、キーボードナビゲーションをサポートします（[既知の問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)を参照）。 |
| SEO 対応 | HTML 出力はセマンティックであり、[schema.org](https://schema.org) マイクロデータ注釈を提供します。 |
| Web アプリ対応 | [効率化された JSON 出力](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/foundation/development/develop-sling-model-exporter.html)によりクライアント側でのレンダリングが可能になる一方、[コンテキスト内編集](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)も依然として可能です。 |
| AMP のサポート | コンポーネントには、[AMP 標準に対する組み込みのサポート](/help/developing/amp.md)があり、モバイルエクスペリエンスの高速化に役立ちます。 |
| デザインキット | [Adobe XD 用 UI キット](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)を使用すると、デザイナーはワイヤフレームを作成したあと、[必要に応じてスタイルを設定](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)できます。 |
| テーマ適用可能 | コンポーネントは[スタイルシステム](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/implementing/components-templates/style-system.html)を実装し、マークアップは [BEM CSS の命名規則](http://getbem.com/)に従っています。 |
| カスタマイズ可能 | いくつかのパターンが用意されているので、HTML の調整から高度な機能の再利用まで、[カスタマイズが容易](developing/customizing.md)になっています。 |
| バージョン管理 | [バージョン管理ポリシー](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)が設定されているので、影響を受ける可能性のある改善の際にも、コアコンポーネントが原因でサイトが機能しなくなることはありません。 |
| ローカライズ可能 | スマートリファレンス解決機能により、特定のコンポーネントが対応する[ローカライズされたコンテンツを自動的に検索してレンダリング](get-started/localization.md)できます。 |
| オープンソース | 何か問題がある場合は、[改善案を寄稿できます。](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## コンポーネント {#the-components}

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
* [進行状況バー](components/progress-bar.md)
* [PDF ビューア](components/pdf-viewer.md)

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
>個別コアコンポーネントの一部のバージョンは、特定のバージョンの AEM とのみ互換性があります。
>
>互換性の情報については、特定のコンポーネントに対する個々のヘルプページ（前の一覧にリンクされています）を参照するか、[コアコンポーネントバージョン](versions.md)ドキュメントで詳細を確認してください。

## システム要件 {#system-requirements}

| コアコンポーネント | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | Maven |
|---------|---------|---------|---------|---------|---------|
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | 継続的 | 6.5.6.0+ * | 6.4.8.4+ * | 8、11 | 3.3.9 以上 |

>[!NOTE]
>
>（*）バージョン 2.11.0 以降、`org.apache.sling.models.impl` バージョン 1.4.12 以降が必要です（[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781) のため）。これは、将来のサービスパックで AEM 6.4 および 6.5 に対して提供される予定です。それまでは、Sling Models バンドルが `core.wcm.components.all` パッケージに含まれます。

以前のコアコンポーネントリリースの要件については、[コアコンポーネントのバージョン](versions.md)を参照してください。

コアコンポーネントでは、[編集可能なテンプレート](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)を使用する必要があり、クラシック UI や静的テンプレートはサポートされていません。必要に応じて、[AEM 最新化ツール](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html)を使用して、これらの最新の AEM 機能をプロジェクトに反映します。

ローカルの開発環境をセットアップするには、[AEM as a Cloud Service SDK の場合はこの概要](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)を、[旧バージョンの AEM](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html) の場合は本ドキュメントを、それぞれを参照してください。

>[!TIP]
>
>コアコンポーネントは自動的に AEM as a Cloud Service に含まれ、常にコアコンポーネントの最新リリースが使用可能になっています。
>
>AEM as a Cloud Service と AEM オンプレミスの両方でコアコンポーネントの使用を開始する方法について詳しくは、[コアコンポーネントの使用](/help/get-started/using.md)を参照してください。
