---
title: コアコンポーネントの開発
seo-title: コアコンポーネントの開発
description: コアコンポーネントは、豊富な機能、継続的配信、コンポーネントのバージョン管理、最新の実装、効率的なマークアップ、コンテンツの JSON エクスポートなどの特長を持つ堅牢で拡張可能なベースコンポーネントを提供します。
seo-description: コアコンポーネントは、豊富な機能、継続的配信、コンポーネントのバージョン管理、最新の実装、効率的なマークアップ、コンテンツの JSON エクスポートなどの特長を持つ堅牢で拡張可能なベースコンポーネントを提供します。
uuid: 68569da2-9bc8-4e20-9a71-e5816ace51ce
contentOwner: ユーザー
content-type: reference
topic-tags: developing
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 157a2ec3-9fca-4fad-977a-d93013eeb218
translation-type: tm+mt
source-git-commit: f30a6a9f4d41c672472beb60767f3766479d9c16

---


# コアコンポーネントの開発{#developing-core-components}

## 概要 {#overview}

コアコンポーネントは堅牢で拡張可能なベースコンポーネントを提供し、次のような特長があります。

* 豊富な機能
   * 多数の使用例に対応する[柔軟な設定オプション](authoring.md)
   * ページ作成者の使用可能な機能を[事前に定義可能](authoring.md#pre-configuring-core-components)
* 継続的配信
   * 増分的機能の頻繁な強化
   * [GitHub でソースコードを入手できる](https://github.com/adobe/aem-core-wcm-components)ので、開発者コミュニティがフィードバックや投稿を提供できる
   * Installation through a [separately released content package](https://github.com/adobe/aem-core-wcm-components/releases) for component upgrades to be done independently from AEM upgrades
* [コンポーネントのバージョン管理](guidelines.md#component-versioning)
   * [バージョン内の互換性を確保](#upgrade-of-core-components)しつつ、コンポーネントを発展させることができる
   * 1 つのコンポーネントの複数バージョンが同じ環境で共存できる
* 最新の実装
   * [HTMLテンプレート言語](https://helpx.adobe.com/experience-manager/htl/using/overview.html) （HTL）で定義されているマークアップ
   * Content model logic implemented with [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* 効率的なマークアップ
   * Following [Block Element Modifier](https://getbem.com/) (BEM) notation as of Release 2.0.0
      * Prior release follow [Bootstrap](https://getbootstrap.com/css/) naming conventions
   * [アクセシビリティガイドラインに基づいて構築](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * レスポンシブサイトおよびモバイルサイトに使用可能
* ヘッドレス CMS の使用例で JSON コンテンツモデルとしてシリアル化する機能
* 高いアクセシビリティ
   * [WCAG2.0AA標準に準拠](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>Core Components require AEM 6.3 or later and Java 8 and and require the use of [editable templates](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>コアコンポーネントは、クラシック UI でも静的テンプレートでも動作しません。

## Gems セッションの概要 {#gems-session-overview}

コアコンポーネントとその機能、AEM での活用方法の概要については、AEM Gems セッションの [AEM コアコンポーネント](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) は、アドビのエキスパートによる技術的な詳細な解説シリーズです。製品ドキュメントやその他のあらゆる技術的なチャネルを補完するこのシリーズを利用すれば、開発者は特定のトピックにふれ、深く理解することができます。

## WKND 開発者向けチュートリアル {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step-by-step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## GitHub 経由で配信 {#delivered-over-github}

コアコンポーネントは GitHub で開発され、GitHub を通じて配信されます。

GitHub のコード

このページのコードは GitHub にあります

* [gitHub上でaem- core- wcm- componentsプロジェクトを開く](https://github.com/adobe/aem-core-wcm-components)
* Download the project as [a ZIP file](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

プロジェクトでコアコンポーネントの使用を開始する方法については、[コアコンポーネントの使用](using.md)を参照してください。

コアコンポーネントが GitHub にあることで、頻繁な更新を行えるほか、AEM 開発者コミュニティからのフィードバックを参考にすることができます。また、顧客やパートナーがカスタムコンポーネントを作成する際に類似のパターンに従うことができるようになります。

>[!NOTE]
>
>コアコンポーネントに常に最新の変更を反映させるには、GitHub 上の[コアコンポーネントリポジトリ](https://github.com/adobe/aem-core-wcm-components)を監視してください。

## コンポーネントライブラリ

[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html)を参照してください。ここでは、コアコンポーネントの現在のリリースを紹介し、使用例を示しています。

### サンプルコンテンツ実行モード {#sample-content-run-mode}

The Core Components are visible in the Quickstart when the sample content is present, because the [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) uses them. ただし、実稼働環境で（サンプルコンテンツが有効でない `nosamplecontent` 実行モードで）実行する場合は、コアコンポーネントは存在しなくなり、開発チームや運用チームの手で AEM インスタンスにインストールする必要があります。

>[!NOTE]
>
>実稼働環境では、クイックスタートを必ず `nosamplecontent` 実行モードで実行してください。`nosamplecontent` 実行モードでコアコンポーネントを使用するには、[コアコンポーネントの使用](using.md)の説明に従ってください。

## 技術的機能 {#technical-capabilities}

コアコンポーネントと基盤コンポーネントの違いを次の表に大まかに示します。

オーサリング機能とそれらの機能を事前に設定するためのオプションについて詳しくは、[コアコンポーネントを使用したオーサリング](authoring.md)を参照してください。

| **機能** | **コアコンポーネント** | **基盤コンポーネント** |
|-----|---|---|
| ロジックの実装 | [Slingモデル](https://sling.apache.org/documentation/bundles/models.html) 注釈を持つJava POJOS | JSP コード |
| マークアップ定義 | [HTMLテンプレート言語](https://helpx.adobe.com/experience-manager/htl/user-guide.html) （HTL）構文 | JSP コード |
| XSS サニタイズ | HTL で自動化 | ほぼ手動 |
| CSS クラスの命名 | [ブロック要素修飾子](https://getbem.com/) （BEM）表記に基づく標準化命名規則（リリース2.0.0以降） | カスタムスキーム |
| ダイアログの定義 | [Coral3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + クラシック UI |
| JSON 出力 | [SlingモデルエクスポーターとJacksonシリアル化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | デフォルト Sling サーブレット |
| バージョン管理 | [モデルと HTL の場合](guidelines.md) | なし |
| テスト | 単体テスト + 統合テスト | 統合テスト |
| 配信 | [パブリックGitHub経由](https://github.com/adobe/aem-core-wcm-components) | クイックスタートを通じて |
| ライセンス | [Apacheライセンス](https://www.apache.org/licenses/LICENSE-2.0) | アドビ固有 |
| 貢献度 | プル要求を通じて | 不可能 |
| アクセシビリティ | [WCAG2.0AA標準に完全準拠](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | [WCAG2.0AA標準に部分的に準拠している](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## コンポーネントリスト {#component-list}

使用可能なコアコンポーネント（API へのリンク）と、コアコンポーネントに置き換わる基盤コンポーネントの一覧を次の表に示します。

| コアコンポーネント | 説明 | 置き換わる基盤コンポーネント |
|---|---|---|
| [ページ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | テンプレートエディターに対応するレスポンシブページ | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [パンくず](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | ページ階層のナビゲーション | `/libs/foundation/components/breadcrumb` |
| [タイトル](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | H1 ~ H6 タイトル | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [テキスト](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | リッチテキスト | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [画像](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | 最適なレンディションサイズのスマート遅延読み込み | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [リスト](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | ページのリスト | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [ソーシャルメディア共有](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | Facebook および Pinterest の共有ウィジェット | `-` |
| [フォームコンテナ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | レスポンシブフォームの段落システム | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [フォームテキスト](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | テキスト入力フィールド | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [フォームオプション](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | 複数オプション入力フィールド | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [フォーム非表示](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | 非表示の入力フィールド | `/libs/foundation/components/form/hidden` |
| [フォームボタン](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | 送信ボタンまたはカスタムボタン | `/libs/foundation/components/form/submit` |
| [ナビゲーション](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | ネストしたページ階層を一覧表示するサイトナビゲーションコンポーネント | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [言語ナビゲーション](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | グローバル言語構造を一覧表示する言語および国の切り替え機能 | `-` |
| [クイック検索](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | 結果をドロップダウンメニューでインプレース候補として表示する検索コンポーネント | `/libs/foundation/components/search` |
| [ティーザー](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | 画像、タイトル、リッチテキスト、追加コンテンツや他のアクションへのリンクを使用して、コンテンツ作成者が詳細なコンテンツへのティーザーを容易に作成できるようになります | `-` |
| [タブ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | コンテンツ作成者がページコンテンツを複数のタブに整理できるようになります | `-` |
| [カルーセル](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | コンテンツ作成者がコンテンツをスライドの回転カルーセルに整理できるようになります | `/libs/foundation/components/carousel` |
| [コンテンツフラグメント](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | コンテンツフラグメントを表示できるようになります | `-` |
| [コンテンツフラグメントリスト](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | コンテンツフラグメントのリストを表示できるようになります | `-` |
| [区切り文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | ページのコンテンツを区切ります | `-` |
| [アコーディオン](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | 折りたたみ可能なアコーディオンのコンテンツパネルを整理する | `-` |
| [コンテナ](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | コンテナ内のコンポーネントの整理 | `-` |
| [ボタン](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | ページ上のボタンの作成 | `-` |
| [ダウンロード](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | ページへのダウンロード可能なアセットの追加 | `-` |

### Upcoming Components {#upcoming-components}

For an overview of the upcoming Core Componente roadmap see the [project wiki on GitHub](https://github.com/adobe/aem-core-wcm-components/wiki/home).

## コアコンポーネントのアップグレード {#upgrade-of-core-components}

バージョン管理されたコンポーネントのメリットの 1 つは、新しい AEM バージョンへの移行と新しいコンポーネントバージョンへの移行を切り離すことができる点です。また、新しいコンポーネントバージョンが使用可能になった場合は、コンポーネントごとに新バージョンへ個別に移行できます。

コアコンポーネントのバージョンが移行先の新しい AEM バージョンもサポートしている場合、新しい AEM バージョンへの移行はコアコンポーネントの動作に影響を与えません。Customizations made to the Core Components should not be affected either, as long as they don&#39;t use APIs that have been [deprecated or removed](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

コアコンポーネントを新しいバージョンに移行しても、コンポーネントの動作には影響しませんが、ページ作成者向けの新しい機能が導入されることはあります。これらの機能については、デフォルトの動作が望ましくない場合、テンプレートエディターで何らかの設定が必要になる可能性があります。一方、カスタマイズ部分は適合が必要になる可能性があります。詳しくは、[コアコンポーネントのカスタマイズ](customizing.md#upgrade-compatibility-of-customizations)を参照してください。

## コアコンポーネントを使用すべき状況 {#when-to-use-the-core-components}

コアコンポーネントはまったく新しい技術であり、複数のメリットがあるので、新しい AEM プロジェクトではコアコンポーネントを使用することをお勧めします。既存のプロジェクトでは、リブランディングや全体的なリファクタリングなど、より大きなプロジェクト作業の一環として移行をおこなうようにしてください。

そこで、アドビでは次の事項を推奨しています。

* **新規プロジェクト**
新規プロジェクトでは、常に、コアコンポーネントを使用するよう努めます。コアコンポーネントを直接使用または[拡張](customizing.md)してプロジェクト要件を満たすことができない場合は、コアコンポーネントで規定されているコンポーネントアーキテクチャに従ってカスタムコンポーネントを作成します。他に方法がない場合を除き、[基盤コンポーネント](developing.md)を使用しないでください。
* **既存プロジェクト**
サイトまたはコンポーネントのリファクタリングが予定されていない限り、[基盤コンポーネント](developing.md)を使用し続けることをお勧めします。\
   ほとんどの既存プロジェクトで広く使用されているので、基盤コンポーネントは[引き続きサポートされます](developing.md)。
* **新規のカスタムコンポーネント**
既存の[コアコンポーネントをカスタマイズしてよいか](customizing.md)どうかを評価します。\
   カスタマイズできない場合は、[コンポーネントのガイドライン](guidelines.md)に従って新規のカスタムコンポーネントを作成することをお勧めします。
* **既存のカスタムコンポーネント**
コンポーネントが期待どおりに動作する場合は、それらのコンポーネントをそのままにしておきます。\
   そうでない場合は、上記の「新規のカスタムコンポーネント」を参照してください。

## コアコンポーネントへの移行

新規プロジェクトは、コアコンポーネントで実装する必要があります。ただし、既存プロジェクトでは通常、基盤コンポーネントが広範囲にわたって実装されています。

既存プロジェクトに関する大規模な作業（リブランディングや全体的なリファクタリングなど）は、多くの場合、コアコンポーネントへの移行のチャンスとなります。このような移行を容易にするために、アドビでは、コアコンポーネントと最新の AEM テクノロジーの導入を促進するための多数の移行ツールを提供しています。

[AEM Enhancedツール](http://opensource.adobe.com/aem-modernize-tools/) を使用すると、次のような簡単な変換が可能になります。

* 静的テンプレートから編集可能テンプレートへ
* デザイン設定からポリシーへ
* 基盤コンポーネントからコアコンポーネントへ
* クラシック UI からタッチ操作対応 UI へ

For further information about the usage of these tools, [see their documentation](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>AEMの最新化ツールはコミュニティの作業であり、アドビによってサポートまたは課金されません。

## コアコンポーネントのサポート {#core-component-support}

コアコンポーネントは AEM に不可欠な部分なので、クイックスタートの一部として提供される場合と同じ条件の下、現状のままでサポートされます。

他の AEM 製品機能と同様、原則的としてまず、コンポーネントの廃止が発表されてから、最短でその次のリリースで削除されます。これにより、サポートが終了する前に、コンポーネントの新バージョンに移行する猶予期間として少なくとも 1 回分のリリースサイクルを確保できます。

各コンポーネントのバージョンには、サポートされる AEM バージョンが明記されています。ある AEM バージョンのサポートが停止されると、その AEM バージョンでのコアコンポーネントのサポートも停止されます。

コンポーネントのカスタマイズのサポートについて詳しくは、[コアコンポーネントのカスタマイズ](customizing.md)を参照してください。

## Foundation コンポーネントのサポート {#foundation-component-support}

基盤コンポーネントは多数の AEM バージョンにわたって大規模プロジェクト開発の基礎の役割を果たしてきたので、今後も引き続きサポートされます。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.

**関連項目：**

* [コアコンポーネントの使用](using.md) - 独自のプロジェクトにコアコンポーネントを導入する方法について説明します。
* [コンポーネントのガイドライン](guidelines.md) - コアコンポーネントの実装パターンについて説明します。
