---
title: AEM プロジェクトアーキタイプの使用
description: AEM プロジェクトのアーキタイプを使用して、最小限のベストプラクティスベースの Adobe Experience Manager プロジェクトを独自の AEM プロジェクトの起点として作成する方法について説明します。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: ht
source-wordcount: '1092'
ht-degree: 100%

---


# AEM プロジェクトアーキタイプの使用 {#using-the-archetype}

このドキュメントでは、AEM プロジェクトのアーキタイプを使用して、最小限のベストプラクティスベースの Adobe Experience Manager プロジェクトを独自の AEM プロジェクトの起点として作成できる方法について説明します。

一般的な使用パターンと、アーキタイプで何が行えるかに焦点を当てます。ビルドオプションと技術的な手順について詳しくは、アーキタイプの GitHub リポジトリにあるドキュメントを参照してください。

>[!TIP]
>
>最新の AEM プロジェクトのアーキタイプおよび技術的なドキュメントは、[GitHub を参照してください。](https://github.com/adobe/aem-project-archetype)

## はじめに {#getting-started}

プロジェクトのアーキタイプを使用すると、AEM での開発を簡単に開始できます。アーキタイプにおける最初の手順には、いくつかの方法があります。

* **WKND チュートリアル** - アーキタイプの活用方法など、AEM での開発に関する概要について詳しくは、[AEM Sites の概要 - WKND チュートリアル](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=ja)を参照して、アーキタイプを使用した単純なプロジェクトの実装手順を示す実例を確認してください。
* **WKND イベントチュートリアル** - AEM でのシングルページアプリケーション（SPA）の開発に特に関心がある場合は、専用の [WKND イベントチュートリアル](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=ja)を確認してください。
* **独自に開始する。** - [GitHub で利用可能な現在のプロジェクトのアーキタイプ](https://github.com/adobe/aem-project-archetype)を簡単にダウンロードして、最初のプロジェクトを独自に作成できます。

## アーキタイプの使用方法 {#how-to-use-the-archetype}

アーキタイプを使用する最初の手順は、ローカルファイル構造内に[モジュール](#what-you-get)を生成するプロジェクトを作成することです。プロジェクト生成の一環として、プロジェクト名、バージョン、様々なオプションの有効化など、プロジェクトの多数のプロパティを定義できます。

>[!TIP]
>
>アーキタイプを構築する際には常に、一連の readme も生成され、[以下にリンクされている](#what-you-get)各モジュールの技術的な詳細と使用方法が提供されます。

Maven でプロジェクトを構築すると、AEM にデプロイできるアーティファクト（パッケージおよび OSGi バンドル）が作成されます。追加の Maven コマンドおよびプロファイルを使用して、プロジェクトのアーティファクトを AEM インスタンスにデプロイできます。

## アーキタイプを使用して得られる結果 {#what-you-get}

アーキタイプはモジュールで構成され、すべてのモジュールはアーキタイプの使用時に自動的に作成されます。

* **[core](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)は、OSGi サービス、リスナー、スケジューラーなどのすべてのコア機能およびサーブレットやリクエストフィルターなどのコンポーネント関連の Java コードを含む Java バンドルです。**
* **[it.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** は、Java ベースの統合テストです。
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)** には、プロジェクトの `/apps` と `/etc` の部分（JS および CSS クライアントライブラリ、コンポーネント、テンプレート）が含まれます。
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)** には、ui.apps モジュールのコンポーネントを使用するサンプルコンテンツが含まれます。
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)** には、プロジェクトの実行モード固有の OSGi 設定が含まれます。
* **[ui.frontend.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)** には、一般的な Webpack ベースのフロントエンドのビルドモジュールの使用に必要なアーティファクトが含まれます（オプション）。
* **[ui.frontend.react](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)** **（オプション）**&#x200B;には、アーキタイプを使用して React に基づく SPA プロジェクトを作成する場合に必要なアーティファクトが含まれます（ビルドパラメーターに基づくオプション）。
* **[ui.frontend.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)** **（オプション）**&#x200B;には、アーキタイプを使用して Angular に基づく SPA プロジェクトを作成する場合に必要なアーティファクトが含まれます（ビルドパラメーターに基づくオプション）。
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** には Selenium ベースの UI テストが含まれます。
* **[all](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)** は、ベンダー依存関係を含むすべてのコンパイル済みモジュール（バンドルとコンテンツパッケージ）を組み込んだ単一のコンテンツパッケージです。
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)** には、AMS／オンプレミスプロジェクトの基本的な Dispatcher 設定が含まれます（ビルドパラメーターに基づくオプション）。
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)** には、AEMaaCS プロジェクトの基本的な Dispatcher 設定が含まれています（ビルドパラメーターに基づくオプション）。

![コンテンツパッケージの構成](/help/assets/content-package-organization.png)

Maven で表されるアーキタイプのモジュールは、アプリケーション、コンテンツおよび必要な OSGi バンドルを表すコンテンツパッケージとして AEM にデプロイされます。

## 親 POM {#parent-pom}

プロジェクトのルートにある `pom.xml`（`<src-directory>/<project>/pom.xml`）は親 POM と呼ばれ、プロジェクトの構造を駆動し、プロジェクトの依存関係と特定のグローバルプロパティを管理します。

### グローバルプロジェクトプロパティ {#global-properties}

親 POM の `<properties>` セクションでは、ユーザー名／パスワード、ホスト名／ポートなど、AEM インスタンスにプロジェクトをデプロイする際に重要なグローバルプロパティを定義します。

これらのプロパティは、ローカルの AEM インスタンスにデプロイするために設定されています。これは、開発者が行う最も一般的なビルドです。オーサーインスタンスにデプロイするためのプロパティおよびパブリッシュインスタンスにデプロイするためのプロパティが存在することに注意してください。ここでは AEM インスタンスを認証するための認証も設定されます。デフォルトの `admin:admin` 資格情報が使用されます。

これらのプロパティは、より上位の環境にデプロイされる際には上書きされるよう設定されています。そうすることで、POM ファイルを変更する必要がなく、`aem.host` および `sling.password` などの変数をコマンドライン引数で上書きできます。

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### モジュール構造 {#module-structure}

親 POM の `<modules>` セクションは、プロジェクトが構築するモジュールを定義します。デフォルトでは、プロジェクトは[定義済みの標準モジュールをビルドします。](#what-you-get)プロジェクトの拡大に合わせて、いつでもモジュールを追加できます。

### 依存関係 {#dependencies}

親 POM の `<dependencyManagement>` セクションは、プロジェクトで使用される API のすべての依存関係とバージョンを定義します。バージョンは親 POM で管理する必要があります。サブモジュールには、バージョン情報を含めないでください。

#### Uber-Jar {#uber-jar}

主要な依存関係の 1 つが [AEM Java API Jar です。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=ja)これは、AEM のバージョンに対応する 1 つの依存関係エントリだけで、すべての AEM API を組み込みます。

>[!NOTE]
>
>ベストプラクティスとしては、AEM のターゲットバージョンに合わせて uber-jar のバージョンを更新することが推奨されます。例えば、AEM 6.5 をデプロイする予定であれば、uber-jar のバージョンを 6.5.X に更新します（`X` は最新のサービスパックです）。

#### コアコンポーネント {#core-components}

もちろん、アーキタイプは[コアコンポーネントを利用します。](/help/introduction.md)そのため、すべてのデプロイメントでコアコンポーネントを使用するには、それらを Maven プロジェクトの一部に組み込むことが推奨されます。

core.wcm.components.examples は、コアコンポーネントの例を示す一連のサンプルページです。ベストプラクティスとして、実稼動用にプロジェクトをデプロイする場合は、この依存関係とサブパッケージのインクルージョンを削除する必要があります。

>[!NOTE]
>
>コアコンポーネントとアーキタイプは別々の GitHub プロジェクトとして維持管理されているので、そのリリースは異なります。
>
>アーキタイプの各リリースでは、リリース時に使用可能なコアコンポーネントの最新リリースを利用します。ただし、コアコンポーネントへの依存関係を手動で更新することもできます。

## テスト {#testing}

プロジェクトには 3 つのレベルのテストが含まれており、テストのタイプが異なるので、実行方法も場所も異なります。

* **[単体テスト](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** - バンドルに含まれているコードの従来の単体テスト
* **[統合テスト](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** - AEM 環境（つまり AEM サーバー上）で単体に似たテストを実行するサーバーサイド統合テスト
* **[UI テスト](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** - ブラウザー側の動作を検証する Selenium ベースのブラウザーサイドテスト
