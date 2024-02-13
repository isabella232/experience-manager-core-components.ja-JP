---
title: コアコンポーネントの概要
description: コアコンポーネントの問題の解決策を入手し、他の人が AEM 内の要素を作成できるようにします。
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: ht
source-wordcount: '808'
ht-degree: 100%

---


# コアコンポーネントの概要{#core-components-introduction}

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。コンポーネントは常に AEM エクスペリエンスの基本要素となってきました。作成者はコンポーネントを使用することで単純かつ強力にページを作成し、開発者は柔軟かつ拡張可能なコンポーネントを開発できます。

コアコンポーネントは、AEM で Web サイトの開発時間を短縮しメンテナンスコストを削減するための、標準化された Web コンテンツ管理（WCM）コンポーネントのセットです。

## リソース {#resources}

* **[コンポーネントライブラリ：](https://www.adobe.com/go/aem_cmp_library_jp)**&#x200B;コンポーネントを様々な設定で表示する例を集めたものです。
* **コンポーネントのドキュメント（本ドキュメント）：&#x200B;**&#x200B;開発者および作成者向けに、各コンポーネントの詳細を説明しています。
* **[コアコンポーネント GitHub リポジトリ：](https://github.com/adobe/aem-core-wcm-components)**&#x200B;開発者向けに、各コンポーネントおよびプロジェクトのダウンロードの詳細を説明しています。
* 入門ガイド：
   * **[コアコンポーネントを利用したプロジェクトの成功への道筋：](/help/developing/success.md)**&#x200B;コアコンポーネントを使用するプロジェクトを開始する前に十分考慮すべきガイドラインです。
   * **[WKND チュートリアル：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=ja)**&#x200B;新しいサイトの構築に関する 2 日間のチュートリアルです。
   * **[Adobe Summit のチュートリアル：](https://expleague.azureedge.net/labs/L767/index.html)**&#x200B;新しいサイトの構築に関する 2 時間のチュートリアルです（US Summit 2019 のラボの内容）。
   * **[Gems Web セミナー：](https://helpx.adobe.com/jp/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**&#x200B;コアコンポーネントのガイドツアー（2018年12月に録画）。

## 機能 {#features}

|  |  |
|---|---|
| 本番で使用可能 | コアコンポーネントは 30 個の堅牢な WCM コンポーネントで、十分にテストされ、広く使用されており、パフォーマンスが優れています。 |
| クラウド対応 | [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja)、[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)、オンプレミスのどれでも動作します。 |
| 用途が広い | コンポーネントは、ほぼあらゆるレイアウトの作成に作成者が使用できる汎用的な概念を表します。 |
| 設定可能 | ページ作成者が使用できる機能と使用できない機能をテンプレートレベルの[コンテンツポリシー](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html?lang=ja#content-policies)で定義します。 |
| [レスポンシブ](responsive.md) | すべてのコアコンポーネントは完全にレスポンシブに動作するように設計されており、デバイス間でのシームレスなエクスペリエンスを実現します。 |
| 追跡可能 | [Adobe Client Data Layer との統合](/help/developing/data-layer/overview.md)により、訪問者エクスペリエンスのあらゆる側面を追跡できます。 |
| 高いアクセシビリティ | [WCAG 2.1 標準](https://www.w3.org/TR/WCAG21/)に準拠し、ARIA ラベルを提供し、キーボードナビゲーションをサポートします（[既知の問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)を参照）。 |
| SEO 対応 | HTML 出力はセマンティックであり、[schema.org](https://schema.org) マイクロデータ注釈を提供します。 |
| Web アプリ対応 | [効率化された JSON 出力](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html?lang=ja)によりクライアント側でのレンダリングが可能になる一方、[コンテキスト内編集](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=ja)も依然として可能です。 |
| AMP のサポート | コンポーネントには、[AMP 標準に対する組み込みのサポート](/help/developing/amp.md)があり、モバイルエクスペリエンスの高速化に役立ちます。 |
| デザインキット | [Adobe XD 用 UI キット](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)を使用すると、デザイナーはワイヤフレームを作成したあと、[必要に応じてスタイルを設定](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)できます。 |
| テーマ適用可能 | コンポーネントは[スタイルシステム](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=ja)を実装し、マークアップは [BEM CSS の命名規則](https://getbem.com/)に従っています。 |
| カスタマイズ可能 | いくつかのパターンが用意されているので、HTML の調整から高度な機能の再利用まで、[カスタマイズが容易](developing/customizing.md)になっています。 |
| バージョン管理 | [バージョン管理ポリシー](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)が設定されているので、影響を受ける可能性のある改善の際にも、コアコンポーネントが原因でサイトが機能しなくなることはありません。 |
| ローカライズ可能 | スマートリファレンス解決機能により、特定のコンポーネントが対応する[ローカライズされたコンテンツを自動的に検索してレンダリング](get-started/localization.md)できます。 |
| オープンソース | 何か問題がある場合は、[改善案を寄稿できます。](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |


## WCM コンポーネント {#the-wcm-components}

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

### テンプレートコンポーネント {#template-components}

* [ページ](components/page.md)
* [ナビゲーション](components/navigation.md)
* [言語ナビゲーション](components/language-navigation.md)
* [パンくず](components/breadcrumb.md)
* [クイック検索](components/quick-search.md)
* [目次](components/tableofcontents.md)

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
* [ソーシャルメディア共有](components/sharing.md)（非推奨）
* [区切り文字](components/separator.md)
* [プログレスバー](components/progress-bar.md)
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
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](get-started/using.md)。統合されると、[テンプレートエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)で使用できるようになり、事前設定されます。

>[!NOTE]
>
>個別コアコンポーネントの一部のバージョンは、特定のバージョンの AEM とのみ互換性があります。
>
>互換性の情報については、特定のコンポーネントに対する個々のヘルプページ（前の一覧にリンクされています）を参照するか、[コアコンポーネントバージョン](versions.md)ドキュメントで詳細を確認してください。

## システム要件 {#system-requirements}

| コアコンポーネントリリース | AEM as a Cloud Service | AEM 6.5 パッチレベル | Java SE バージョン | Maven バージョン |
|---------|---------|---------|---------|---------|
| [2.23.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.4) | 継続的 | 6.5.17.0+ | 8、11 | 3.3.9 以上 |

以前のコアコンポーネントリリースの要件については、[コアコンポーネントのバージョン](versions.md)を参照してください。

コアコンポーネントでは、[編集可能なテンプレート](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html?lang=ja)を使用する必要があり、クラシック UI や静的テンプレートはサポートされていません。必要に応じて、[AEM 最新化ツール](https://opensource.adobe.com/aem-modernize-tools/)を使用して、これらの最新の AEM 機能をプロジェクトに反映します。

ローカルの開発環境を設定するには、[AEM as a Cloud Service SDK の場合はこの概要](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html?lang=ja)を、[旧バージョンの AEM の場合](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=ja)は本ドキュメントを、それぞれ参照してください。

>[!TIP]
>
>コアコンポーネントは自動的に AEM as a Cloud Service に含まれ、常にコアコンポーネントの最新リリースが使用可能になっています。
>
>AEM as a Cloud Service と AEM オンプレミスの両方でコアコンポーネントの使用を開始する方法について詳しくは、[コアコンポーネントの使用](/help/get-started/using.md)を参照してください。

## その他のコンポーネント {#other-components}

AEM 作成者が使用できる追加のコンポーネントがあり、コアコンポーネント上に構築されています。

* [メールコアコンポーネント](/help/email/introduction.md) - コアコンポーネントの上に構築され、特に Adobe Campaign で使用するためのコンポーネントを検出します。
