---
title: コアコンポーネントの開発
seo-title: コアコンポーネントの開発
description: コアコンポーネントは、機能豊富な機能、継続的な配信、コンポーネントのバージョン管理、最新の実装、冗長なマークアップおよびJSONの書き出しを提供する拡張可能なベースコンポーネントを提供します。
seo-description: コアコンポーネントは、機能豊富な機能、継続的な配信、コンポーネントのバージョン管理、最新の実装、冗長なマークアップおよびJSONの書き出しを提供する拡張可能なベースコンポーネントを提供します。
uuid: 68569da2-9bc8-4e20-9a71- e5816ace51ce
contentOwner: User
content-type: reference
topic-tags: 開発中
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: 157a2ec3-9fca-4fad-977a- d93013eeb218
translation-type: tm+mt
source-git-commit: bea783936100abe899f9b60e4a09522514755db2

---


# Developing Core Components{#developing-core-components}

## 概要 {#overview}

コアコンポーネントは、堅牢で拡張性のあるベースコンポーネントを提供し、ハイライトは次のとおりです。

* 豊富な機能
   * [多数の使用事例に対応](authoring.md) する柔軟な設定オプション
   * [ページ作成者が使用できる機能を定義](authoring.md#pre-configuring-core-components) するための事前設定機能
* 連続配信
   * 頻繁な増分機能の強化
   * Availability of the [source code on GitHub](https://github.com/adobe/aem-core-wcm-components) to allow the developer community to give feedback and contribute
   * Installation through a [separately released content package](https://github.com/adobe/aem-core-wcm-components/releases) for component upgrades to be done independently from AEM upgrades
* [コンポーネントのバージョン管理](guidelines.md#component-versioning)
   * [バージョン内の互換性を確認](#upgrade-of-core-components)して、コンポーネントを
   * 1つのコンポーネントの複数バージョンが同じ環境で共存できるようにする
* 最新の実装
   * [HTMLテンプレート言語](https://helpx.adobe.com/experience-manager/htl/using/overview.html) （HTL）で定義されているマークアップ
   * Content model logic implemented with [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* 効率的なマークアップ
   * Following [Block Element Modifier](https://getbem.com/) (BEM) notation as of Release 2.0.0
      * Prior release follow [Bootstrap](https://getbootstrap.com/css/) naming conventions
   * [アクセシビリティガイドラインに基づいて構築](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * レスポンシブサイトおよびモバイルサイトに使用可能
* ヘッドレスCMS使用事例のコンテンツモデルでJSONとしてシリアライズする機能
* アクセシビリティ
   * [WCAG2.0AA標準に準拠](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>Core Components require AEM 6.3 or later and Java 8 and and require the use of [editable templates](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>コアコンポーネントは、クラシックUIと静的テンプレートでは機能しません。

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) は、アドビのエキスパートによる技術的な詳細な解説シリーズです。このシリーズは、製品ドキュメントとその他の技術的なチャネルを補完し、開発者が特定のトピックを詳細に調べ、詳細に調べます。

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step-by-step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Delivered over GitHub {#delivered-over-github}

コアコンポーネントはGitHubによって開発され、配信されます。

GitHub のコード

このページのコードは GitHub にあります

* [gitHub上でaem- core- wcm- componentsプロジェクトを開く](https://github.com/adobe/aem-core-wcm-components)
* Download the project as [a ZIP file](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

See the [Using Core Components](using.md) documentation page to learn how to get started using them in your project.

GitHubにコアコンポーネントを配置すると、頻繁な更新を行えるようになり、AEM開発者コミュニティからのフィードバックを聞くことができます。また、これは、カスタムコンポーネントを作成する際に、顧客およびパートナーが類似のパターンを従うのに役立ちます。

>[!NOTE]
>
>To keep up-to-date on the latest changes to the core components, you can watch the [Core Components repository](https://github.com/adobe/aem-core-wcm-components) on GitHub.

## コンポーネントライブラリ

[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html)を確認して、コアコンポーネントの現在のリリースを表示し、使用例を提供します。

### Sample Content Run-Mode {#sample-content-run-mode}

The Core Components are visible in the Quickstart when the sample content is present, because the [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) uses them. However, when running in production (in `nosamplecontent` runmode, without sample content enabled), the core components won&#39;t be present anymore and must be installed on the AEM instances by the development and/or operations team.

>[!NOTE]
>
>In production environments, always run the Quickstart in `nosamplecontent` runmode. To use the Core Components in `nosamplecontent` runmode, follow the instructions of the [Using Core Components](using.md) documentation page.

## Technical Capabilities {#technical-capabilities}

次の表に、コアコンポーネントと基盤コンポーネントの違いを示します。

For details about their authoring capabilities and options to pre-configurable them, [refer to the authoring page about them](authoring.md).

| **機能** | **コアコンポーネント** | **Foundation Component** |
|-----|---|---|
| ロジックの実装 | [Slingモデル](https://sling.apache.org/documentation/bundles/models.html) 注釈を持つJava POJOS | JSPコード |
| マークアップの定義 | [HTMLテンプレート言語](https://helpx.adobe.com/experience-manager/htl/user-guide.html) （HTL）構文 | JSPコード |
| XSSサブリゼーション | HTLで自動化 | ほとんど手動 |
| CSSクラスの命名 | [ブロック要素修飾子](https://getbem.com/) （BEM）表記に基づく標準化命名規則（リリース2.0.0以降） | カスタムスキーム |
| ダイアログ定義 | [Coral3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral2+ Classic UI |
| JSON出力 | [SlingモデルエクスポーターとJacksonシリアル化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | デフォルトSlingサーブレット |
| バージョン管理 | [モデルとHTLの場合](guidelines.md) | なし |
| テスト | ユニットテストと統合テスト | 統合テスト |
| 配信 | [パブリックGitHub経由](https://github.com/adobe/aem-core-wcm-components) | クイックスタート |
| License | [Apacheライセンス](https://www.apache.org/licenses/LICENSE-2.0) | アドビ独自の |
| 貢献度 | プルリクエスト経由 | 不可能 |
| アクセシビリティ | [WCAG2.0AA標準に完全準拠](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | [WCAG2.0AA標準に部分的に準拠している](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## コンポーネントリスト {#component-list}

次の表に、使用可能なコアコンポーネントの一覧、APIへのリンク、および置き換える基盤コンポーネントを示します。

| コアコンポーネント | 説明 | Foundationコンポーネントに置き換えました |
|---|---|---|
| [ページ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | テンプレートエディターで使用するレスポンシブページ | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [パンくず](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | ページ階層のナビゲーション | `/libs/foundation/components/breadcrumb` |
| [タイトル](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | H1~ H6タイトル | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [テキスト](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | リッチテキスト | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [画像](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | 最適なレンディションサイズのスマート読み込みと遅延読み込み | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [リスト](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | ページのリスト | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [ソーシャルメディア共有](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | FacebookおよびPinterest共有ウィジェット | `-` |
| [フォームコンテナ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | レスポンシブフォームの段落システム | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [フォームテキスト](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | テキスト入力フィールド | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [フォームオプション](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | 複数のオプション入力フィールド | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [フォーム非表示](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | 非表示の入力フィールド | `/libs/foundation/components/form/hidden` |
| [フォームボタン](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | 送信ボタンまたはカスタムボタン | `/libs/foundation/components/form/submit` |
| [ナビゲーション](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | ネストされたページ階層を表示するサイトナビゲーションコンポーネント | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [言語ナビゲーション](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | グローバル言語構造を一覧表示する言語および国の切り替え | `-` |
| [クイック検索](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | ドロップダウンメニューで結果をインプレースサーチクエリとして表示する検索コンポーネント | `/libs/foundation/components/search` |
| [ティーザー](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | コンテンツ、タイトル、リッチテキストを使用してコンテンツ、タイトル、またはその他のアクションにリンクすることで、コンテンツ作成者がより簡単にコンテンツにティーザーを作成できます | `-` |
| [タブ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | コンテンツ作成者が複数のタブ内でページコンテンツを整理できるようにします | `-` |
| [カルーセル](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | コンテンツ作成者がスライドの回転カルーセル内のコンテンツを整理できるようにします | `/libs/foundation/components/carousel` |
| [コンテンツフラグメント](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | コンテンツフラグメントの表示を許可 | `-` |
| [コンテンツフラグメントリスト](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | コンテンツフラグメントのリストを表示できます | `-` |
| [区切り文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | ページ上のコンテンツの分離 | `-` |
| [アコーディオン](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | 折りたたみ可能なアコーディオンのコンテンツパネルを整理する | `-` |
| [コンテナ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | コンテナ内のコンポーネントの整理 | `-` |
| [ボタン](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | ページ上のボタンの作成 | `-` |
| [ダウンロード](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | ページへのダウンロード可能なアセットの追加 | `-` |

### Upcoming components {#upcoming-components}

以下のコアコンポーネントは、積極的に機能しています。They haven&#39;t been released yet, but can be previewed in the [development branch](https://github.com/adobe/aem-core-wcm-components/tree/development):

* 埋め込み
* モーダル

## Upgrade of Core Components {#upgrade-of-core-components}

バージョン管理されたコンポーネントの利点の1つは、新しいコンポーネントバージョンへの移行から新しいAEMバージョンへの移行を分離できることです。また、新しいコンポーネントバージョンが使用可能な場合は、各コンポーネントの個別の移行が可能になります。

バージョンのバージョンが移行先の新しいAEMバージョンをサポートしている場合、新しいAEMバージョンへの移行は、コアコンポーネントの動作に影響しません。Customizations made to the Core Components should not be affected either, as long as they don&#39;t use APIs that have been [deprecated or removed](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

新しいバージョンのコアコンポーネントへの移行は、コンポーネントがどのように機能するかに影響しませんが、新しい機能がページ作成者に導入されることはありません。これは、デフォルトの動作が望ましくない場合に備えて、テンプレートエディターによって一部の設定が必要になる可能性があります。Customizations however might need to be adapted, for more details see the [Customizing Core Components](customizing.md#upgrade-compatibility-of-customizations) page.

## When to Use the Core Components? {#when-to-use-the-core-components}

コアコンポーネントはまったく新規であり、複数のメリットがあるので、新しいAEMプロジェクトで使用することをお勧めします。既存のプロジェクトでは、リブランディングや全体的なリファクタリングなど、より大きなプロジェクト作業の一環として移行を行う必要があります。

したがって、アドビでは次の推奨事項を提供しています。

* **新しいプロジェクト** 新しいプロジェクトでは、常にコアコンポーネントを使用しようとします。If Core Components cannot be used directly or [extended](customizing.md) to satisfy project requirements, then create a custom component following the component architecture set forth in core components. Except where not otherwise possible, avoid using the [foundation components](developing.md).
* **既存のプロジェクト** のレコメンデーションは [、サイトまたはコンポーネントのリファクタリングが計画されていない限り、基盤コンポーネント](developing.md)を使用し続けることができます。\
   As they are very widely used by most existing projects, the foundation components [will continue to be supported.](developing.md)
* **新しいカスタムコンポーネント**[の評価](customizing.md)を参照してください。\
   If not, recommendation is to build a new custom component following the [Component Guidelines](guidelines.md).
* **既存のカスタムコンポーネント** コンポーネントが期待どおりに動作する場合は、それらのコンポーネントをそのまま維持します。\
   そうでない場合は、上記の「新しいカスタムコンポーネント」を参照してください。

## コアコンポーネントへの移行

新しいプロジェクトは、コアコンポーネントで実装する必要があります。ただし、既存のプロジェクトは通常、Foundationコンポーネントを広範に導入します。

既存プロジェクトの大きな作業（リブランディングや全体的なリファクタリングなど）は、多くの場合、コアコンポーネントへの移行のチャンスとなります。この移行を容易にするために、アドビでは、コアコンポーネントと最新のAEMテクノロジーの採用を奨励するために、多数の移行ツールを提供しています。

[AEM Enhancedツール](http://opensource.adobe.com/aem-modernize-tools/) を使用すると、次のような簡単な変換が可能になります。

* 編集可能なテンプレートへの静的テンプレート
* ポリシーへのデザイン設定
* Foundationコンポーネントからコアコンポーネント
* クラシックUIからタッチ対応UIへのUI

For further information about the usage of these tools, [see their documentation](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>AEMの最新化ツールはコミュニティの作業であり、アドビによってサポートまたは課金されません。

## Core Component Support {#core-component-support}

コアコンポーネントは、AEMの不可欠な構成要素であり、同じ条件と条件の中で、クイックスタートの一部として配信されたかのように条件を満たしています。

その他のAEM製品機能と同様に、一般的なルールは次のようになります。コンポーネントは最初に廃止され、次のAEMリリースでは最も古いものが削除されます。そのため、少なくとも1つのリリースサイクルで、サポートをドロップする前に、少なくとも1つのリリースサイクルに移動することができます。

各コンポーネントのバージョンは、サポートされているAEMバージョンを明確に状態させます。サポートがAEMのバージョンで停止すると、そのバージョンのAEMのコアコンポーネントのサポートが実行されます。

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page.

## Foundation Component Support {#foundation-component-support}

基盤コンポーネントは多数のAEMバージョンにわたるプロジェクト開発の基盤として提供されているため、今後も今後も引き続きサポートされます。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.

**関連項目：**

* [コアコンポーネント](using.md) の使用-独自のプロジェクトのコアコンポーネントの使用を習得できます。
* [コンポーネントガイドライン](guidelines.md) -コアコンポーネントの実装パターンを学習します。
