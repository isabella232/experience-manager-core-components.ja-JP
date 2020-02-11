---
title: コアコンポーネントの開発
description: コアコンポーネントは、豊富な機能、継続的配信、コンポーネントのバージョン管理、最新の実装、効率的なマークアップ、コンテンツの JSON エクスポートなどの特長を持つ堅牢で拡張可能なベースコンポーネントを提供します。
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# コアコンポーネントの開発{#developing-core-components}

## 概要 {#overview}

コアコンポーネントは堅牢で拡張可能なベースコンポーネントを提供し、次のような特長があります。

* 豊富な機能
   * 多数の使用例に対応する[柔軟な設定オプション](authoring.md)
   * ページ作成者の使用可能な機能を[事前に定義可能](authoring.md#pre-configuring-core-components)
* 継続的配信
   * 増分的機能の頻繁な強化
   * GitHub で[ソースコード](https://github.com/adobe/aem-core-wcm-components)を入手できるので、開発者コミュニティがフィードバックや投稿を提供できる
   * [別個にリリースされるコンテンツパッケージ](https://github.com/adobe/aem-core-wcm-components/releases)を通じたインストールで、コンポーネントのアップグレードを AEM のアップグレードとは別におこなうことができる
* [コンポーネントのバージョン管理](guidelines.md#component-versioning)
   * [バージョン内の互換性を確保](#upgrade-of-core-components)しつつ、コンポーネントを発展させることができる
   * 1 つのコンポーネントの複数バージョンが同じ環境で共存できる
* 最新の実装
   * [HTML テンプレート言語](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html)（HTL）で定義されたマークアップ
   * [Sling モデル](https://sling.apache.org/documentation/bundles/models.html)で実装されたコンテンツモデルロジック
* 効率的なマークアップ
   * リリース 2.0.0 時点の[ブロック要素修飾子](https://getbem.com/)（BEM）表記に準拠
      * 以前のリリースでは、[Bootstrap](https://getbootstrap.com/css/) 命名規則に準拠していました。
   * [アクセシビリティガイドライン](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)に沿って構築されている
   * レスポンシブサイトおよびモバイルサイトに使用可能
* ヘッドレス CMS の使用例で JSON コンテンツモデルとしてシリアル化する機能
* 高いアクセシビリティ
   * [WCAG 2.0 AA 標準](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)に準拠

>[!CAUTION]
>
>コアコンポーネントでは AEM 6.3 以降と Java 8 が必要です。また、[編集可能テンプレート](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)を使用する必要があります。
>
>コアコンポーネントは、クラシック UI でも静的テンプレートでも動作しません。

## Gems セッションの概要 {#gems-session-overview}

コアコンポーネントとその機能、AEM での活用方法の概要については、AEM Gems セッションの [AEM コアコンポーネント](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) は、アドビのエキスパートによる技術的な詳細の解説シリーズです。製品ドキュメントやその他のあらゆる技術的なチャネルを補完するこのシリーズを利用すれば、開発者は特定のトピックにふれ、深く理解することができます。

## WKND 開発者向けチュートリアル {#wknd-developer-tutorial}

コアコンポーネントで AEM Sites の開発を始めるには、[この詳しいチュートリアル](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)に従います。

## AEM プロジェクトアーキタイプ {#aem-project-archetype}

[AEM Project Archetypeは、推奨のプロキシパターンを使用したコアコンポーネントのロジックと適切な実装のためのSlingModelを使用したカスタムHTMLコンポーネントの例を含め、独自のプロジェクトの起点として最小限のAdobe Experience Managerプロジェクトを作成します。](overview.md)

## GitHub 経由で配信 {#delivered-over-github}

コアコンポーネントは GitHub で開発され、GitHub を通じて配信されます。

GitHub のコード

このページのコードは GitHub にあります

* [GitHub の aem-core-wcm-components プロジェクトを開きます](https://github.com/adobe/aem-core-wcm-components)
* プロジェクトを [ZIP ファイル](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)としてダウンロードします

プロジェクトでコアコンポーネントの使用を開始する方法については、[コアコンポーネントの使用](using.md)を参照してください。

コアコンポーネントが GitHub にあることで、頻繁な更新を行えるほか、AEM 開発者コミュニティからのフィードバックを参考にすることができます。また、顧客やパートナーがカスタムコンポーネントを作成する際に類似のパターンに従うことができるようになります。

>[!NOTE]
>
>コアコンポーネントに常に最新の変更を反映させるには、GitHub 上の[コアコンポーネントリポジトリ](https://github.com/adobe/aem-core-wcm-components)を監視してください。

## コンポーネントライブラリ

[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library)を参照してください。ここでは、コアコンポーネントの現在のリリースを紹介し、使用例を示しています。

### コアコンポーネントをすぐに使用できる状態 {#out-of-the-box}

AEMの実行方法に応じて、コアコンポーネントが自動的にインストールされる場合とされない場合があります。

#### クラウドサービスとしてのAEM {#aem-cloud-service}

コアコンポーネントはクラウドサービスとしての [AEMとの完全な互換性がありますが](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)、コアコンポーネントは手動でインストールする必要があり、そのまま使用することはできません。

#### AEMオンプレミス {#on-premise}

In on-premise installations, the Core Components are visible in the Quickstart when the sample content is present, because the [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) uses them. However, when running in production (in `nosamplecontent` runmode, without sample content enabled), the core components won&#39;t be present anymore and must be installed on the AEM instance.

>[!NOTE]
>
>In on-premise production environments, always run the Quickstart in `nosamplecontent` runmode. `nosamplecontent` 実行モードでコアコンポーネントを使用するには、[コアコンポーネントの使用](using.md)の説明に従ってください。

## 技術的機能 {#technical-capabilities}

コアコンポーネントと基盤コンポーネントの違いを次の表に大まかに示します。

オーサリング機能とそれらの機能を事前に設定するためのオプションについて詳しくは、[コアコンポーネントを使用したオーサリング](authoring.md)を参照してください。

| **機能** | **コアコンポーネント** | **基盤コンポーネント** |
|-----|---|---|
| ロジックの実装 | [Sling モデル](https://sling.apache.org/documentation/bundles/models.html)注釈の付いた Java POJO | JSP コード |
| マークアップ定義 | [HTML テンプレート言語](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html)（HTL）構文 | JSP コード |
| XSS サニタイズ | HTL で自動化 | ほぼ手動 |
| CSS クラスの命名 | [ブロック要素修飾子](https://getbem.com/)（BEM）表記（リリース 2.0.0 時点）に基づく、標準化された命名規則 | カスタムスキーム |
| ダイアログの定義 | [Coral 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + クラシック UI |
| JSON 出力 | [Jackson シリアル化を使用している Sling モデルエクスポーター](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | デフォルト Sling サーブレット |
| バージョン管理 | [モデルと HTL の場合](guidelines.md) | なし |
| テスト | 単体テスト + 統合テスト | 統合テスト |
| 配信 | [公開 GitHub 経由](https://github.com/adobe/aem-core-wcm-components) | クイックスタートを通じて |
| ライセンス | [Apache ライセンス](https://www.apache.org/licenses/LICENSE-2.0) | アドビ固有 |
| 貢献度 | プル要求を通じて | 不可能 |
| アクセシビリティ | [WCAG 2.0 AA 標準]に完全に準拠(https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | [WCAG 2.0 AA 標準](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)に部分的に準拠 |

## コンポーネントリスト {#component-list}

使用可能なコアコンポーネント（API へのリンク）と、コアコンポーネントに置き換わる基盤コンポーネントの一覧を次の表に示します。

| コアコンポーネント | 説明 | 置き換わる基盤コンポーネント |
|---|---|---|
| [ページ](https://adobe.com/go/aem_cmp_tech_page_v2) | テンプレートエディターに対応するレスポンシブページ | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [パンくず](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | ページ階層のナビゲーション | `/libs/foundation/components/breadcrumb` |
| [タイトル](https://adobe.com/go/aem_cmp_tech_title_v2) | H1 ~ H6 タイトル | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [テキスト](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | リッチテキスト | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [画像](https://adobe.com/go/aem_cmp_tech_image_v2) | 最適なレンディションサイズのスマート遅延読み込み | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [リスト](https://adobe.com/go/aem_cmp_tech_list_v2) | ページのリスト | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [ソーシャルメディア共有](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Facebook および Pinterest の共有ウィジェット | `-` |
| [フォームコンテナ](https://adobe.com/go/aem_cmp_tech_form_container_v2) | レスポンシブフォームの段落システム | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [フォームテキスト](https://adobe.com/go/aem_cmp_tech_form_text_v2) | テキスト入力フィールド | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [フォームオプション](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 複数オプション入力フィールド | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [フォーム非表示](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 非表示の入力フィールド | `/libs/foundation/components/form/hidden` |
| [フォームボタン](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 送信ボタンまたはカスタムボタン | `/libs/foundation/components/form/submit` |
| [ナビゲーション](https://adobe.com/go/aem_cmp_tech_navigation_v1) | ネストしたページ階層を一覧表示するサイトナビゲーションコンポーネント | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [言語ナビゲーション](https://adobe.com/go/aem_cmp_tech_langnav_v1) | グローバル言語構造を一覧表示する言語および国の切り替え機能 | `-` |
| [クイック検索](https://adobe.com/go/aem_cmp_tech_search_v1) | 結果をドロップダウンメニューでインプレース候補として表示する検索コンポーネント | `/libs/foundation/components/search` |
| [ティーザー](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 画像、タイトル、リッチテキスト、追加コンテンツや他のアクションへのリンクを使用して、コンテンツ作成者が詳細なコンテンツへのティーザーを容易に作成できるようにする | `-` |
| [タブ](https://adobe.com/go/aem_cmp_tech_tabs_v1) | コンテンツ作成者がページコンテンツを複数のタブに整理できるようにする | `-` |
| [カルーセル](https://adobe.com/go/aem_cmp_tech_carousel_v1) | コンテンツ作成者がコンテンツをスライドの回転カルーセルに整理できるようにする | `/libs/foundation/components/carousel` |
| [コンテンツフラグメント](https://adobe.com/go/aem_cmp_tech_cf_v1) | コンテンツフラグメントを表示できるようにする | `-` |
| [コンテンツフラグメントリスト](https://adobe.com/go/aem_cmp_tech_cflist_v1) | コンテンツフラグメントのリストを表示できるようにする | `-` |
| [区切り文字](https://adobe.com/go/aem_cmp_tech_separator_v1) | ページのコンテンツを区切る | `-` |
| [アコーディオン](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 折りたたみ可能なアコーディオンの形式にコンテンツパネルを整理する | `-` |
| [コンテナ](https://adobe.com/go/aem_cmp_tech_container_v1) | コンテナ内のコンポーネントを整理する | `-` |
| [ボタン](https://adobe.com/go/aem_cmp_tech_button_v1) | ページ上にボタンを作成する | `-` |
| [ダウンロード](https://adobe.com/go/aem_cmp_tech_download_v1) | ダウンロード可能なアセットをページに追加する | `-` |
| [エクスペリエンスフラグメント](https://adobe.com/go/aem_cmp_tech_xf_v1) | エクスペリエンスフラグメントをページに追加する | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [埋め込み](https://adobe.com/go/aem_cmp_tech_embed_v1) | ページ内に外部リソースを埋め込む | - |

### 今後リリース予定のコンポーネント {#upcoming-components}

今後リリース予定のコアコンポーネントのロードマップ概要については、[GitHub のプロジェクト Wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home) を参照してください。

## コアコンポーネントのアップグレード {#upgrade-of-core-components}

バージョン管理されたコンポーネントのメリットの 1 つは、新しい AEM バージョンへの移行と新しいコンポーネントバージョンへの移行を切り離すことができる点です。また、新しいコンポーネントバージョンが使用可能になった場合は、コンポーネントごとに新バージョンへ個別に移行できます。

コアコンポーネントのバージョンが移行先の新しい AEM バージョンもサポートしている場合、新しい AEM バージョンへの移行はコアコンポーネントの動作に影響を与えません。[廃止または削除](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)された API を使用していない限り、コアコンポーネントのカスタマイズ部分も影響を受けません。

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

[AEM Modernization Tools](http://opensource.adobe.com/aem-modernize-tools/) を使用すると、以下の変換を容易におこなえるようになります。

* 静的テンプレートから編集可能テンプレートへ
* デザイン設定からポリシーへ
* 基盤コンポーネントからコアコンポーネントへ
* クラシック UI からタッチ操作対応 UI へ

これらのツールの使用方法について詳しくは、[ぞれぞれのドキュメント](http://opensource.adobe.com/aem-modernize-tools/)/を参照してください。

>[!NOTE]
>
>AEM Modernize Tools はコミュニティの取り組みであり、アドビによるサポートまたは保証の対象外です。

## コアコンポーネントのサポート {#core-component-support}

コアコンポーネントは AEM に不可欠な部分なので、クイックスタートの一部として提供される場合と同じ条件の下、現状のままでサポートされます。

他の AEM 製品機能と同様、原則的としてまず、コンポーネントの廃止が発表されてから、最短でその次のリリースで削除されます。これにより、サポートが終了する前に、コンポーネントの新バージョンに移行する猶予期間として少なくとも 1 回分のリリースサイクルを確保できます。

各コンポーネントのバージョンには、サポートされる AEM バージョンが明記されています。ある AEM バージョンのサポートが停止されると、その AEM バージョンでのコアコンポーネントのサポートも停止されます。

コンポーネントのカスタマイズのサポートについて詳しくは、[コアコンポーネントのカスタマイズ](customizing.md)を参照してください。

## Foundation コンポーネントのサポート {#foundation-component-support}

基盤コンポーネントは多数の AEM バージョンにわたって大規模プロジェクト開発の基礎の役割を果たしてきたので、今後も引き続きサポートされます。

ただし、アドビの開発の重点はコアコンポーネントに移っており、新機能はコアコンポーネントに追加されます。一方、[大部分の Foundation コンポーネントが AEM 6.5 で廃止され](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html)、今後 Foundation コンポーネントに対してはバグ修正のみがおこなわれます。

**関連項目：**

* [コアコンポーネントの使用](using.md) - 独自のプロジェクトにコアコンポーネントを導入する方法について説明します。
* [コンポーネントのガイドライン](guidelines.md) - コアコンポーネントの実装パターンについて説明します。
