---
title: AEM プロジェクトアーキタイプの使用
description: AEMプロジェクトのアーキタイプを使用して、最小限のベストプラクティスベースのAdobe Experience Managerプロジェクトを独自のAEMプロジェクトの出発点として作成する方法を説明します。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 33%

---


# AEM プロジェクトアーキタイプの使用 {#using-the-archetype}

このドキュメントでは、AEMプロジェクトアーキタイプを使用して、最小限のベストプラクティスベースのAdobe Experience Managerプロジェクトを独自のAEMプロジェクトの出発点として作成する方法を説明します。

一般的な使用パターンと、アーキタイプが何をおこなうかに焦点を当てます。 ビルドオプションと技術的な手順について詳しくは、アーキタイプの GitHub リポジトリにあるドキュメントを参照してください。

>[!TIP]
>
>最新のAEMプロジェクトアーキタイプと関連する技術ドキュメント [は GitHub にあります。](https://github.com/adobe/aem-project-archetype)

## はじめに {#getting-started}

プロジェクトのアーキタイプを使用すると、AEM での開発を簡単に開始できます。アーキタイプの最初の手順は、様々な方法でおこなえます。

* **WKND チュートリアル**  — アーキタイプの活用方法を含むAEMでの開発に関する優れた概要については、 [AEM Sites使用の手引き — WKND チュートリアル](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=ja) を参照してください。この実用的な例では、アーキタイプを使用して簡単なプロジェクトを実装する方法について説明します。
* **WKND イベントチュートリアル** - AEMでのシングルページアプリケーション (SPA) の開発に特に関心がある場合は、専用の [WKND イベントのチュートリアル](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=ja)
* **自分で始めなさい！**  — 簡単にダウンロードできます [GitHub で利用可能な現在のプロジェクトアーキタイプ](https://github.com/adobe/aem-project-archetype) 最初のプロジェクトを独自に作成します。

## アーキタイプの使用方法 {#how-to-use-the-archetype}

アーキタイプを使用する最初の手順は、を生成するプロジェクトを作成することです [モジュール](#what-you-get) をローカルファイル構造内に置き換えます。 プロジェクト生成の一環として、プロジェクト名、バージョン、様々なオプションの有効化など、プロジェクトの多数のプロパティを定義できます。

>[!TIP]
>
>アーキタイプを構築する際には常に、一連の読み取りデータも生成され、各モジュールの技術的な詳細と使用方法が次のように提供されます。 [以下にリンクされています。](#what-you-get)

Maven でプロジェクトを構築すると、AEM にデプロイできるアーティファクト（パッケージおよび OSGi バンドル）が作成されます。追加の Maven コマンドおよびプロファイルを使用して、プロジェクトのアーティファクトを AEM インスタンスにデプロイできます。

## アーキタイプを使用して得られる結果 {#what-you-get}

アーキタイプはモジュールで構成され、すべてのモジュールはアーキタイプの使用時に自動的に作成されます。

* **[コア](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** は、OSGi サービス、リスナー、スケジューラなどのすべてのコア機能、およびサーブレットや要求フィルターなどのコンポーネント関連の Java コードが含まれる Java バンドルです。
* **[it.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** は、Java ベースの統合テストです。
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)** 次を含む `/apps` および `/etc` プロジェクトの一部（JS および CSS の clientlib、コンポーネント、テンプレートなど）。
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)** ui.apps モジュールのコンポーネントを使用するサンプルコンテンツが含まれます。
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)** には、プロジェクト用の実行モード固有の OSGi 設定が含まれています。
* **[ui.frontend.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)** には、一般的な Webpack ベースのフロントエンドビルドモジュールの使用に必要なアーティファクトが含まれます（オプション）。
* **[ui.frontend.react](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)** **（オプション）** には、アーキタイプを使用して React に基づいてSPAプロジェクトを作成する場合に必要なアーティファクトが含まれます（オプション、ビルドパラメーターに依存）。
* **[ui.frontend.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)** **（オプション）** には、アーキタイプを使用してAngularに基づいてSPAプロジェクトを作成する場合に必要なアーティファクトが含まれます（オプション、ビルドパラメーターに応じて異なります）。
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** には、Selenium ベースの UI テストが含まれています。
* **[すべて](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)** は、ベンダーの依存関係を含むすべてのコンパイル済みモジュール（バンドルおよびコンテンツパッケージ）を埋め込んだ単一のコンテンツパッケージです。
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)** には、AMS/オンプレミスプロジェクト用の基本的な Dispatcher 設定が含まれています（オプション、ビルドパラメーターに応じて異なります）。
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)** には、AEMaaCS プロジェクトの基本的な dispatcher 設定が含まれています（オプション、ビルドパラメーターに応じて異なります）。

![コンテンツパッケージの構成](/help/assets/content-package-organization.png)

Maven で表されるアーキタイプのモジュールは、アプリケーション、コンテンツ、および必要な OSGi バンドルを表すコンテンツパッケージとしてAEMにデプロイされます。

## 親 POM {#parent-pom}

プロジェクトのルートにある `pom.xml`（`<src-directory>/<project>/pom.xml`）は親 POM と呼ばれ、プロジェクトの構造を駆動し、プロジェクトの依存関係と特定のグローバルプロパティを管理します。

### グローバルプロジェクトプロパティ {#global-properties}

親 POM の `<properties>` セクションでは、ユーザー名／パスワード、ホスト名／ポートなど、AEM インスタンスにプロジェクトをデプロイする際に重要なグローバルプロパティを定義します。

これらのプロパティは、ローカルの AEM インスタンスにデプロイするために設定されています。これは、開発者が行う最も一般的なビルドです。オーサーインスタンスにデプロイするためのプロパティおよびパブリッシュインスタンスにデプロイするためのプロパティが存在することに注意してください。ここでは AEM インスタンスを認証するための認証も設定されます。デフォルト `admin:admin` 資格情報が使用されます。

これらのプロパティは、より上位の環境にデプロイされる際には上書きされるよう設定されています。そうすることで、POM ファイルを変更する必要がなく、`aem.host` および `sling.password` などの変数をコマンドライン引数で上書きできます。

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### モジュール構造 {#module-structure}

親 POM の `<modules>` セクションは、プロジェクトが構築するモジュールを定義します。デフォルトでは、プロジェクトが構築されます [以前に定義した標準モジュール。](#what-you-get) プロジェクトの展開に合わせて、いつでもモジュールを追加できます。

### 依存関係 {#dependencies}

親 POM の `<dependencyManagement>` セクションは、プロジェクトで使用される API のすべての依存関係とバージョンを定義します。バージョンは親 POM で管理する必要があります。 サブモジュールにはバージョン情報を含めないでください。

#### Uber-Jar {#uber-jar}

主な依存関係の 1 つは、 [AEM Java API Jar。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=ja) これにより、AEMのバージョンに対して、すべてのAEM API が単一の依存関係エントリで含まれます。

>[!NOTE]
>
>ベストプラクティスとしては、AEM のターゲットバージョンに合わせて uber-jar のバージョンを更新することが推奨されます。例えば、AEM 6.5 にデプロイする予定の場合は、uber-jar のバージョンを 6.5.X に更新します。ここで、 `X` は、最新のサービスパックです。

#### コアコンポーネント {#core-components}

もちろん、のアーキタイプは [コアコンポーネント。](/help/introduction.md) したがって、すべてのデプロイメントでコアコンポーネントを活用するには、コアコンポーネントを Maven プロジェクトの一部に含めることをお勧めします。

core.wcm.components.examples は、コアコンポーネントの例を示す一連のサンプルページです。ベストプラクティスとして、実稼動用にプロジェクトをデプロイする場合は、この依存関係とサブパッケージのインクルージョンを削除する必要があります。

>[!NOTE]
>
>コアコンポーネントとアーキタイプは別々の GitHub プロジェクトとして管理されているので、そのリリースは異なります。
>
>アーキタイプの各リリースでは、リリース時に使用可能なコアコンポーネントの最新リリースを利用します。 ただし、コアコンポーネントとの依存関係を手動で更新することもできます。

## テスト {#testing}

プロジェクトには 3 つのレベルのテストが含まれており、テストのタイプが異なるので、実行方法も場所も異なります。

* **[単体テスト](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)**  — バンドルに含まれるコードの従来のユニットテスト
* **[統合テスト](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** - AEM環境 (AEMサーバー上など ) で単体型テストを実行するサーバー側統合テスト
* **[UI テスト](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)**  — ブラウザー側の動作を検証する Selenium ベースのブラウザーサイドテスト
