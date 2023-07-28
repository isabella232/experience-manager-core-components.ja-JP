---
title: AEM プロジェクトアーキタイプ
description: AEM ベースのアプリケーション用のプロジェクトテンプレート
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 4d93ba2e1aac91521496ecfef127157c9bc8776c
workflow-type: ht
source-wordcount: '1192'
ht-degree: 100%

---

# AEM プロジェクトアーキタイプ {#aem-project-archetype}

AEM プロジェクトアーキタイプは、Web サイトの出発点として、ベストプラクティスに基づいた最小限の Adobe Experience Manager（AEM）プロジェクトを作成する Maven テンプレートです。

>[!TIP]
>
>最新の AEM プロジェクトアーキタイプは [GitHub で入手できます](https://github.com/adobe/aem-project-archetype)。

## リソース {#resources}

* **アーキタイプのドキュメント（本ドキュメント）：**&#x200B;アーキタイプアーキテクチャとその様々なモジュールの概要です。
   * **[アーキタイプの使用：](using.md)**&#x200B;アーキタイプと使用可能なモジュールの使用に関する詳細
   * **[ui.frontend：](uifrontend.md)**&#x200B;フロントエンドビルドモジュールの使用方法
* **次のチュートリアルは、このアーキタイプに基づいています。**
   * **[WKND サイト：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=ja)**&#x200B;新しい Web サイトを開始する方法を説明します。
   * **[WKND シングルページアプリ：](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=ja)** AEM で完全にオーサリング可能な React または Angular Web アプリを作成する方法を説明します。

## 機能 {#features}

* **ベストプラクティス：**&#x200B;アドビの最新の推奨プラクティスをすべて活用して、サイトをブートストラップできます。
* **ローコード（低コード）：**&#x200B;テンプレートの編集、コンテンツの作成、CSS のデプロイを行うと、サイトの運用開始準備が整います。
* **クラウド対応：**&#x200B;必要に応じて、[AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja) を使用して、数日以内に運用を開始でき、スケーラビリティとメンテナンスの向上を図れます。
* **Dispatcher：**&#x200B;プロジェクトには、速度とセキュリティを確実に達成できる [Dispatcher 設定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=ja)が必要です。
* **マルチサイト：**&#x200B;必要に応じて、[マルチ言語およびマルチリージョンセットアップ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html?lang=ja)用のコンテンツ構造がアーキタイプから生成されます。
* **コアコンポーネント：**&#x200B;作成者は、アドビの汎用の[標準コンポーネントセット](/help/introduction.md)を使用して、ほぼどのようなレイアウトでも作成できます。
* **編集可能なテンプレート：**&#x200B;ほとんどすべての[テンプレートをコードなしで](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html?lang=ja)組み立てることができ、作成者による編集が可能な範囲を定義できます。
* **レスポンシブレイアウト：**&#x200B;テンプレートまたは個々のページで、定義されたブレークポイントについて[要素がどのようにリフローするかを定義](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=ja)できます。
* **ヘッダーとフッター：** [コンポーネントのローカライゼーション機能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=ja)を使用して、コードなしで組み立ててローカライズできます。
* **スタイルシステム：**&#x200B;作成者が[様々なスタイルを適用](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html?lang=ja)できるようにすることで、カスタムコンポーネントを作成しないようにすることができます。
* **フロントエンドビルド：**&#x200B;フロントエンド開発者は、[AEM ページのモックを作成](uifrontend.md#webpack-dev-server)し、Webpack、TypeScript、SASS を使用して[クライアントライブラリをビルド](uifrontend.md)することができます。
* **Web アプリ対応：** [React](uifrontend-react.md) または [Angular](uifrontend-angular.md) を使用するサイトの場合は、[SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html?lang=ja) を使用して、[アプリのコンテキスト内オーサリング](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=ja)を維持できます。
* **コマースに対応：**[AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html?lang=ja)を [Magento](https://magento.com/jp) などのコマースソリューションと統合するプロジェクトの場合は、[Commerce コアコンポーネント](https://github.com/adobe/aem-core-cif-components)を使用します。
* **コード例：** HelloWorld コンポーネントのほか、サンプルのモデル、サーブレット、フィルター、スケジューラーをチェックアウトできます。
* **オープンソース：**&#x200B;何か問題がある場合は、改善案を[寄稿](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md)できます。

## 使用方法 {#usage}

プロジェクトを生成する場合は、次のコマンドラインを必要に応じて調整します。

```shell
mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* `XX` を最新の[アーキタイプバージョン番号](#requirements)に置き換えます。
* [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja) の場合は、`aemVersion=cloud` と設定します。\
  [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) またはオンプレミスの場合は、`aemVersion=6.5.0` と設定します。
AEM as a Cloud Service の場合はコアコンポーネントがすぐに使用できる形で提供されているので、コアコンポーネントの依存関係は、非クラウドバージョンの AEM の場合にのみ追加します。
* `appTitle="My Site"` を調整して、Web サイトのタイトルやコンポーネントグループを定義します。
* `appId="mysite"` を調整して、Maven アーティファクト ID、コンポーネントフォルダー名、設定フォルダー名、コンテンツフォルダー名、およびクライアントライブラリ名を定義します。
* `groupId="com.mysite"` を調整して、Maven グループ ID と Java ソースパッケージを定義します。
* 使用可能なプロパティのリストを調べて、調整が必要なプロパティが他にあるかどうかを確認します。

## 使用可能なプロパティ {#available-properties}

| 名前 | デフォルト値は | 説明 |
|---------------------------|----------------|--------------------|
| `appTitle` |                | アプリケーションのタイトル。Web サイトのタイトルやコンポーネントグループに使用されます（例：`"My Site"`）。 |
| `appId` |                | 技術的な名前。コンポーネント、設定、コンテンツのフォルダー名やクライアントライブラリ名に使用されます（例：`"mysite"`）。 |
| `artifactId` | *`${appId}`* | 基本 Maven アーティファクト ID です（例：`"mysite"`）。 |
| `groupId` |                | ベース Maven グループ ID です（例：`"com.mysite"`）。この値は、[有効な Java パッケージ名](https://docs.oracle.com/javase/specs/jls/se6/html/packages.html#7.7)である必要があります。 |
| `package` | *`${groupId}`* | Java ソースパッケージです（例：`"com.mysite"`）。 |
| `version` | `1.0-SNAPSHOT` | プロジェクトのバージョンです（例：`1.0-SNAPSHOT`）。 |
| `aemVersion` | `cloud` | ターゲット AEM バージョンです（[AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja) の場合は `cloud`。[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) またはオンプレミスの場合は、`6.5.0`、`6.4.4` のいずれか）。 |
| `sdkVersion` | `latest` | `aemVersion=cloud` の場合は、[SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=ja) のバージョンを指定できます（例：`2020.02.2265.20200217T222518Z-200130`）。 |
| `includeDispatcherConfig` | `y` | `aemVersion` の値に応じて、クラウドか AMS／オンプレミスのいずれかの Dispatcher 設定を組み込みます（`y` または `n`）。 |
| `frontendModule` | `general` | クライアントライブラリを生成する Webpack フロントエンドビルドモジュールを組み込みます（通常のサイトの場合は `general` または `none`。[SPA エディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html?lang=ja)を実装しているシングルページアプリの場合は `angular` または `react`）。 |
| `language` | `en` | コンテンツ構造の作成に使用する言語コード（ISO 639-1）（例：`en`、`deu`）。 |
| `country` | `us` | コンテンツ構造の作成に使用する国コード（ISO 3166-1）（例：`US`）。 |
| `singleCountry` | `y` | 言語マスターコンテンツ構造を組み込みます（`y` または `n`）。 |
| `includeExamples` | `n` | [コンポーネントライブラリ](https://www.aemcomponents.dev/)のサンプルサイトを組み込みます（`y` または `n`）。 |
| `includeErrorHandler` | `n` | インスタンス全体でグローバルに使用されるカスタムの 404 応答ページを組み込みます（`y` または `n`）。 |
| `includeCommerce` | `n` | [CIF コアコンポーネント](https://github.com/adobe/aem-core-cif-components)の依存関係を含み、対応するアーティファクトを生成します。 |
| `commerceEndpoint` |                | CIF でのみ必須です。使用するコマースシステム GraphQL サービスのオプションのエンドポイント（例：`https://hostname.com/grapql`）をクリックします。 |
| `includeFormscommunications` | `n` | [Forms コアコンポーネント](https://github.com/adobe/aem-core-forms-components)の依存関係、テンプレート、フォームデータモデル、テーマを組み込み、Forms Communications プログラムに対応するアーティファクトを生成します。 |
| `includeFormsenrollment` | `n` | [Forms コアコンポーネント](https://github.com/adobe/aem-core-forms-components)の依存関係、テンプレート、フォームデータモデル、テーマを組み込み、Forms 登録プログラムに対応するアーティファクトを生成します。 |
| `sdkFormsVersion` | `latest` | `aemVersion=cloud` および `includeFormsenrollment=y` または `includeFormscommunications=y` のいずれかの場合、Forms SDK のバージョンを指定できます（例： `2020.12.17.02`）。 |
| `datalayer` | `y` | [Adobe クライアントデータレイヤー](/help/developing/data-layer/overview.md)との統合をアクティブ化します。 |
| `amp` | `n` | 生成されたプロジェクトテンプレートに対して [AMP](/help/developing/amp.md) のサポートを有効にします。 |
| `enableDynamicMedia` | `n` | プロジェクトポリシー設定で基盤 Dynamic Media コンポーネントを有効にし、コア画像コンポーネントのポリシーで Dynamic Media 機能をアクティブ化します。 |
| `enableSSR` | `n` | フロントエンドプロジェクトに対して SSR を有効にするオプション |
| `precompiledScripts` | `n` | `ui.apps` のサーバーサイドスクリプトを[事前にコンパイル](/help/developing/archetype/precompiled-bundled-scripts.md)して、`ui.apps` プロジェクトのセカンダリバンドルアーティファクトとしてビルドにアタッチするオプション。`aemVersion` を `cloud` に設定する必要があります。 |
| `includeFormsheadless` | `n` |  [Forms コアコンポーネント](https://github.com/adobe/aem-core-forms-components)の依存関係、 `ui.frontend.react.forms.af` およびヘッドレスアーティファクトを組み込みます。 |

## システム要件 {#requirements}

| アーキタイプ | AEM as a Cloud Service | AEM 6.5 | Java SE | Maven |
|---------|---------|---------|---------|---------|
| [43](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-43) | 継続的 | 6.5.7.0+ | 8、11 | 3.3.9 以上 |

[AEM as a Cloud Service SDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html?lang=ja) または[旧バージョンの AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=ja) のローカル開発環境をセットアップします。

### 既知の問題 {#known-issues}

Windows 上で実行して Dispatcher 設定を生成する場合は、管理者権限のコマンドプロンプトまたは Windows Subsystem for Linux から実行する必要があります（[問題 329](https://github.com/adobe/aem-project-archetype/issues/329) を参照）。

（`-B` パラメーターを指定せずに）インタラクティブモードでアーキタイプを実行する際は、最終確認が却下された場合を除き、デフォルト値を持つプロパティは変更できません。その場合は、デフォルト値を持つプロパティを含めることで質問が繰り返し表示されます（詳しくは [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) を参照してください）。

`File -> New -> Maven Project` で新しいプロジェクトを開始する際に、Eclipse でこのアーキタイプを使用することはできません。これは、生成後のスクリプト `archetype-post-generate.groovy` が [Eclipse の問題](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993)によって実行されないことが原因です。回避策は、上記のコマンドラインを使用し、Eclipse で `File -> Import -> Existing Maven Project` を使用することです。

## 参考情報 {#further-reading}

利点、オプション、モジュールの動作など、アーキタイプの使用について詳しくは、[アーキタイプの使用](using.md)を参照してください。
