---
title: AEMプロジェクトのアーキタイプの使用
description: AEMプロジェクトのアーキタイプの使用方法の詳細
translation-type: tm+mt
source-git-commit: 477a1774a856725f52b9db7a978c534de4700661

---


# AEM プロジェクトアーキタイプ {#aem-project-archetype}

AEM プロジェクトのアーキタイプは、最小限のベストプラクティスベースの Adobe Experience Manager プロジェクトを独自の AEM プロジェクトの起点として作成します。このアーキタイプを使用する際に指定する必要があるプロパティにより、このプロジェクトのすべての部分の名前を指定し、特定のオプション機能を制御できます。

## アーキタイプを使用する理由 {#why-use-the-archetype}

AEM プロジェクトのアーキタイプを使用すると、数回のキー操作で、ベストプラクティスベースの AEM プロジェクトを構築するためのパスが設定されます。アーキタイプを使用すると、すべての要素が配置され、結果として生成されるプロジェクトを最小限に抑えながら、AEM の[主要機能](#features)すべてが実装されることになります。これにより、必要な作業はその上に構築して拡張するだけとなります。

もちろん、成功する AEM プロジェクトには多数の要素がありますが、AEM プロジェクトのアーキタイプを使用すると健全な基盤を構築できるので、あらゆる AEM プロジェクトで強くお勧めします。

## 概要 {#getting-started}

プロジェクトのアーキタイプを使用すると、AEM での開発を簡単に開始できます。最初の手順にはいくつかの方法があります。

* WKND チュートリアル - アーキタイプの活用方法など、AEM での開発に関する詳しい概要については、「[AEM Sites の概要 - WKND チュートリアル](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)」を参照して、アーキタイプを使用した単純なプロジェクトの実装手順を示す実例を確認してください。
* WKND イベントチュートリアル - AEM でのシングルページアプリケーション（SPA）の開発に特に関心がある場合は、専用の [WKND イベントチュートリアル](https://helpx.adobe.com/jp/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)を必ずご覧ください。
* ダウンロードして開始しましょう。- [以下の簡単な手順に従うと](#how-to-use-the-archetype)、GitHub で利用可能な現在のプロジェクトのアーキタイプを簡単にダウンロードして、最初のプロジェクトを作成できます。

## アーキタイプを使用して得られる結果 {#what-you-get}

AEM アーキタイプは、次のモジュールで構成されています。

* **[core](core.md)**：OSGi サービス、リスナー、スケジューラなどのすべてのコア機能、およびサーブレットや要求フィルターなどのコンポーネント関連の Java コードが含まれる Java バンドル。
* **[ui.apps](uiapps.md)**：プロジェクトの`/apps`部分と`/etc`部分（JS と CSS の clientlib、コンポーネント、テンプレート、実行モード固有の設定、Hobbes テストなど）が含まれます。
* **[ui.content](uicontent.md)**：ui.apps モジュールのコンポーネントを使用するサンプルコンテンツが含まれます。
* **[ui.tests](uitests.md)**：サーバー側で実行される JUnit テストが含まれる Java バンドル。このバンドルは実稼動環境にはデプロイされません。
* **ui.launcher**：ui.tests バンドル（および依存するバンドル）をサーバーにデプロイし、JUnit のリモート実行をトリガーするグルーコードが含まれます。
* **[ui.frontend.general](uifrontend.md)**：**（オプション）**一般的な Webpack ベースのフロントエンドビルドモジュールの使用に必要なアーティファクトが含まれます。
* **[ui.frontend.react](uifrontend-react.md)**：**（オプション）**アーキタイプを使用して React に基づく SPA プロジェクトを作成する場合に必要なアーティファクトが含まれます。
* **[ui.frontend.angular](uifrontend-angular.md)**：**（オプション）**アーキタイプを使用して Angular に基づく SPA プロジェクトを作成する場合に必要なアーティファクトが含まれます。

![](/help/assets/archetype-structure.png)

Maven で表される AEM アーキタイプのモジュールは、アプリケーション、コンテンツ、および必要な OSGi バンドルを表すコンテンツページとして AEM にデプロイされます。

## アーキタイプの使用方法{#how-to-use-the-archetype}

アーキタイプを使用するには、最初にプロジェクトを作成し、[前述のとおりに](#what-you-get)ローカルファイル構造でモジュールを生成する必要があります。プロジェクト生成の一環として、プロジェクト名、バージョンなど、プロジェクトの多数のプロパティを定義できます。

Maven でプロジェクトを構築すると、AEM にデプロイできるアーティファクト (パッケージおよび OSGi バンドル) が作成されます。追加の Maven コマンドおよびプロファイルを使用して、プロジェクトのアーティファクトを AEM インスタンスにデプロイできます。

### プロジェクトの作成 {#create-project}

最初に、最も簡単に [AEM Eclipse 拡張機能](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/developing/devtools/aem-eclipse.html)を使用し、新しいプロジェクトウィザードに従って「**AEM Sample Multi-Module Project**」を選択し、リリースされたバージョンのアーキタイプを使用できます。

もちろん、Maven を直接呼び出すこともできます。

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.granite.archetypes \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* Set `XX` to the [version number](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) of the latest AEM Project Archetype.
* AEMをク `aemVersion=cloud` ラウ [ドサービスとして設定](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html);\
   アドビ `aemVersion=6.5.0` の [Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)、またはオンプレミスに設定します。
コアコンポーネントの依存関係は、非クラウドAEMバージョンに対してのみ追加されます。これは、コアコンポーネントがAEM用にクラウドサービスとしてOOTBを提供するためです。
* Webサイトのタ `appTitle="My Site"` イトルとコンポーネントグループを定義するように調整します。
* Maven artifactId、 `appId="mysite"` コンポーネント、設定、コンテンツのフォルダー名、およびクライアントライブラリ名を定義するように調整します。
* Maven groupIdとJava `groupId="com.mysite"` ソースパッケージを定義するように調整します。
* 使用可能なプロパティのリストを参照して、調整するプロパティの数が多いかどうかを確認します。

>[!NOTE]
>
>ベストプラクティスとしては、repo.adobe.com を自動で maven のビルドプロセスに追加するために、`adobe-public` プロファイルを Maven の `settings.xml` ファイルに追加することが推奨されます。
>
>POM の例は[こちらにあります](https://helpx.adobe.com/jp/experience-manager/kb/SetUpTheAdobeMavenRepository.html)。

### プロパティ {#properties}

アーキタイプを使用してプロジェクトを作成する場合は、次のプロパティを使用できます。

| 名前 | デフォルト値は | 説明 |
--------------------------|----------------|--------------------
| `appTitle` |  | アプリのタイトル。Webサイトのタイトルやコンポーネントグループ( `"My Site"`)。 |
| `appId` |  | 技術的な名前。コンポーネント、設定、コンテンツのフォルダー名、クライアントライブラリ名(例： `"mysite"`)。 |
| `artifactId` | *`${appId}`* | Base Maven artifact ID (e.g. `"mysite"`). |
| `groupId` |  | Base Maven group ID (e.g. `"com.mysite"`). |
| `package` | *`${groupId}`* | Javaソースパッケージ(例： `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | プロジェクトのバージョン(例： `1.0-SNAPSHOT`)。 |
| `aemVersion` | `6.5.0` | ターゲットAEMバージョン(クラウドサ `cloud` ービ [スとしてのAEM用に指定可能](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html)。また `6.5.0`は、 `6.4.4`Adobe Managed Services `6.3.3`[](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) またはオンプレミスの場合)。 |
| `sdkVersion` | `latest` | `aemVersion=cloud` SDKバージョ [ンを指定できる場合](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (例： `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | の値（またはの可能性）に応じて、クラウドまたはAMS/オンプレミスのディスパッチャー設 `aemVersion` 定を含め `y` ます `n`。 |
| `frontendModule` | `none` | クライアントライブラリ（通常のサイトの場合と、通常のサイトの場合）を生成するWebpackフロントエンドビル `general` ドモジュール `none` が含まれています。は、 `angular` または `react`[SPAエディターを実装する単一ページアプリ](https://docs.adobe.com/content/help/en/experience-manager-65/developing/headless/spas/spa-overview.html)用)。 |
| `languageCountry` | `en_us` | Language and country code to create the content structure from (e.g. `en_us`). |
| `singleCountry` | `y` | 言語マスターのコンテンツ構造を含めます(または `y`のいずれか `n`)。 |
| `includeExamples` | `y` | コンポーネン [トライブラリ](https://www.aemcomponents.dev/) のサンプルサイトを含めます( `y`または `n`)。 |
| `includeErrorHandler` | `n` | インスタンス全体に対してグローバルに表示されるカスタム404応答ページを含めます(または `y` 可能 `n`です)。 |

>[!NOTE]
> アーキタイプを初めてインタラクティブモードで実行する際には、デフォルト値のプロパティは変更できません（詳しくは [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) を参照してください）。この値は、最後のプロパティ確認が拒否され、質問が繰り返された場合や、コマンドラインでパラメータを渡す際に変更できます（例：`-DoptionIncludeExamples=n`）。

>[!NOTE]
>Windows 上で実行して Dispatcher 設定を生成する場合は、管理者権限のコマンドプロンプトまたは Windows Subsystem for Linux から実行する必要があります（[問題 329](https://github.com/adobe/aem-project-archetype/issues/329) を参照）。

### プロファイル {#profiles}

生成された Maven プロジェクトは、`mvn install` の実行時に様々なデプロイメントプロファイルをサポートします。

| プロファイル ID | 説明 |
--------------------------|------------------------------
| `autoInstallBundle` | maven-sling-plugin を含むコアバンドルを felix コンソールにインストールします。 |
| `autoInstallPackage` | パッケージマネージャーに content-package-maven-plugin を使用し、ui.content と ui.apps のコンテンツパッケージをローカルホスト（ポート 4502）のデフォルトのオーサーインスタンスにインストールします。ホスト名とポートは、`aem.host` および `aem.port` ユーザー定義プロパティを使用して変更できます。 |
| `autoInstallPackagePublish` | パッケージマネージャーに content-package-maven-plugin を使用し、ui.content と ui.apps のコンテンツパッケージをローカルホスト（ポート 4503）のデフォルトのパブリッシュインスタンスにインストールします。ホスト名とポートは、`aem.host` および `aem.port` ユーザー定義プロパティを使用して変更できます。 |
| `autoInstallSinglePackage` | パッケージマネージャーに content-package-maven-plugin を使用し、`all` のコンテンツパッケージをローカルホスト（ポート 4502）のデフォルトのオーサーインスタンスにインストールします。ホスト名とポートは、`aem.host` および `aem.port` ユーザー定義プロパティを使用して変更できます。 |
| `autoInstallSinglePackagePublish` | パッケージマネージャーに content-package-maven-plugin を使用し、`all` のコンテンツパッケージをローカルホスト（ポート 4503）のデフォルトのパブリッシュインスタンスにインストールします。ホスト名とポートは、`aem.host` および `aem.port` ユーザー定義プロパティを使用して変更できます。 |
| `integrationTests` | 提供された統合テストを AEM インスタンスで実行します（`verify` フェーズのみ）。 |

### ビルドとインストール {#building-and-installing}

プロジェクトのルートディレクトリで実行するすべてのモジュールを構築するには、次の Maven コマンドを使用します。

```
mvn clean install
```

実行中の AEM インスタンスがある場合は、次の Maven コマンドを使用して、プロジェクト全体を構築およびパッケージ化し、AEM にデプロイできます。

```
mvn clean install -PautoInstallPackage
```

パブリッシュインスタンスにデプロイするには、次のコマンドを実行します。

```
mvn clean install -PautoInstallPackagePublish
```

または、パブリッシュインスタンスにデプロイするには、次のコマンドを実行します。

```
mvn clean install -PautoInstallPackage -Daem.port=4503
```

または、オーサーにバンドルのみをデプロイするには、次のコマンドを実行します。

```
mvn clean install -PautoInstallBundle
```

## 親 POM {#parent-pom}

プロジェクトのルートにある`<src-directory>/<project>/pom.xml`（`pom.xml`）は親 POM と呼ばれ、プロジェクトの構造を駆動し、プロジェクトの依存関係と特定のグローバルプロパティを管理します。

### グローバルプロジェクトプロパティ {#global-properties}

親 POM の `<properties>` セクションでは、ユーザー名／パスワード、ホスト名／ポートなど、AEM インスタンスにプロジェクトをデプロイする際に重要なグローバルプロパティを定義します。

これらのプロパティは、ローカルの AEM インスタンスにデプロイするために設定されています。これは、開発者がおこなう最も一般的なビルドです。オーサーインスタンスにデプロイするためのプロパティおよびパブリッシュインスタンスにデプロイするためのプロパティが存在することに注意してください。ここでは AEM インスタンスを認証するための認証も設定されます。デフォルトの admin:admin 認証が使用されています。

これらのプロパティは、より上位の環境にデプロイされる際には上書きされるよう設定されています。そうすることで、POM ファイルを変更する必要がなく、`aem.host` および `sling.password` などの変数をコマンドライン引数で上書きできます。

````
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
````

### モジュール構造 {#module-structure}

親 POM の `<modules>` セクションは、プロジェクトが構築するモジュールを定義します。デフォルトでは、プロジェクトは[以前に定義された標準モジュール](#what-you-get)（core、ui.apps、ui.content、ui.tests および it.launcher）を構築します。プロジェクトの拡大に合わせて、いつでもモジュールを追加できます。

### 依存関係 {#dependencies}

親 POM の `<dependencyManagement>` セクションは、プロジェクトで使用される API のすべての依存関係とバージョンを定義します。バージョンは親 POM 内で管理する必要があり、コアや ui.apps などのサブモジュールにはバージョン情報を一切含めてはなりません。

#### Uber-Jar {#uber-jar}

主要な依存関係の 1 つに [AEM uber-jar](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies) があります。これにより、AEM のバージョンに対して、すべての AEM API が単一の依存関係のエントリで含められます。

>[!NOTE]
>
>ベストプラクティスとしては、AEM のターゲットバージョンに合わせて uber-jar のバージョンを更新することが推奨されます。例えば、AEM 6.4 をデプロイする予定であれば、uber-jar のバージョンを 6.4.0 に更新します。

#### コアコンポーネント {#core-components}

もちろん、AEM プロジェクトのアーキタイプはコアコンポーネントを活用します。

コアコンポーネントは、デフォルトの実行モードで AEM に自動的にインストールされます。また、サンプルの We.Retail サイトで使用されます。[実稼動実行モード](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/administering/security/production-ready.html)（`nosamplecontent`）では、コアコンポーネントは使用できません。

そのため、すべてのデプロイメントでコアコンポーネントを使用するには、それらを Maven プロジェクトの一部に組み込むことが推奨されます。

>[!NOTE]
>
>最新のアーキテクチャでコアコンポーネントの最新バージョンが使用されるよう、通常は、コアコンポーネントの各リリースに続き、AEM プロジェクトアーキタイプがリリースされます。
>
>ただし、新しいバージョンのアーキタイプは、新しいバージョンのコアコンポーネントに直接従っていない可能性があるので、コアコンポーネントの依存関係を最新バージョンに更新することができます。

>[!NOTE]
>
>core.wcm.components.examples は、コアコンポーネントの例を示す一連のサンプルページです。ベストプラクティスとして、実稼動用にプロジェクトをデプロイする場合は、この依存関係とサブパッケージのインクルージョンを削除する必要があります。

## テスト {#testing}

プロジェクトには 3 つのレベルのテストが含まれており、テストのタイプが異なるので、実行方法も場所も異なります。

* コアでの単体テスト：バンドルに含まれるコードの従来のユニットテストを示しています。テストするには、次の手順を実行します。
   * `mvn clean test`
* サーバーサイド統合テスト：これらのテストは、AEM 環境（AEM サーバー上など）で実行されます。テストするには、次の手順を実行します。
   * `mvn clean verify -PintegrationTests`
* クライアントサイドの Hobbes.js テスト：ブラウザー側の動作を検証する JavaScript ベースのブラウザーサイドテストです。テストするには：
   1. ページの作成時と同様に、ブラウザーに AEM を読み込みます。
   1. ページを[開発者モード](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/developing/components/developer-mode.html)で開きます。
   1. 左のパネルを開き、「**Tests**」タブに切り替えます。
   1. 生成された **MyName Tests** を見つけ、実行します。

## 次の手順 {#next-steps}

AEM プロジェクトアーキタイプを構築し、インストールしました。次は何をすればよいでしょうか。アーキタイプは小さいとはいえ、推奨ベストプラクティスに従って設定された、多数の強力な AEM 機能の例で構成されています。これらを使用すれば、プロジェクトで機能をどのように活用できるかがわかります。どのプロジェクトでも、次の作業が必要になる可能性があります。

* [既存のコアコンポーネントを拡張するコンポーネントのカスタマイズ](/help/developing/customizing.md)
* [テンプレートの追加](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [ローカリゼーション構造の適応](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/administering/introduction/tc-prep.html)
* [フロントエンドビルドモジュールの詳細](uifrontend.md)
