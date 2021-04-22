---
title: React SPA のフロントエンドビルド
description: React ベースの SPA プロジェクトのフロントエンドビルドプロセスの説明
feature: コアコンポーネント、AEM プロジェクトアーキタイプ
role: Architect, Developer, Administrator
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
translation-type: ht
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: ht
source-wordcount: '517'
ht-degree: 100%

---

# React SPA のフロントエンドビルド {#frontend-react}

このドキュメントでは、アーキタイプを使用して React フレームワークに基づく単一ページアプリケーション（SPA）を作成するプロジェクトの詳細を説明します。例えば、`frontendModule` オプションを `react` に設定する場合です。

## 概要 {#overview}

このプロジェクトは、[create-react-app](https://github.com/facebook/create-react-app) でブートストラップ処理されました。

このアプリケーションは、サイトの AEM モデルを使用するようにビルドされています。これにより、[@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components) パッケージのヘルパーコンポーネントを使用してレイアウトが自動的に生成されます。

## スクリプト {#scripts}

プロジェクトディレクトリで、次のコマンドを実行できます。

### npm start {#npm-start}

```shell
npm start
```

このコマンドは、http://localhost:4502 で実行されるローカル AEM インスタンスから JSON モデルをプロキシすることで、アプリを開発モードで実行します。これは、プロジェクト全体が少なくとも 1 回 AEM にデプロイされていることを前提としています（プロジェクトルートの `mvn clean install -PautoInstallPackage`）。

[ui.frontend](uifrontend.md) ディレクトリで `npm start` を実行すると、アプリが自動的にブラウザーで開きます（パス `http://localhost:3000/content/<appId>/<country>/<language>/home.html`）。編集すると、ページがリロードされます。

CORS に関連するエラーが発生する場合は、次のように AEM を設定します。

1. 設定マネージャーに移動します（http://localhost:4502/system/console/configMgr）
1. 「Adobe Granite Cross-Origin Resource Sharing Policy」の設定を開きます。
1. 次の値を追加して、新しい設定を作成します。
   * 許可されるオリジン：http://localhost:3000
   * サポートされるヘッダー：Authorization
   * 許可されるメソッド：OPTIONS

### npm test {#npm-test}

```shell
npm test
```

このコマンドは、インタラクティブ監視モードでテストランナーを起動します。詳しくは、[テスト実行に関する React のドキュメント](https://facebook.github.io/create-react-app/docs/running-tests)を参照してください。

### npm run build {#npm-run-build}

```shell
npm run build
```

このコマンドは、実稼動用のアプリケーションを build フォルダーにビルドします。実稼動モードで React をバンドルし、最適なパフォーマンスを得るためにビルドを最適化します。詳しくは、[デプロイメントに関する React のドキュメント](https://facebook.github.io/create-react-app/docs/deployment)を参照してください。

さらに、AEM clientLib は、[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) パッケージを使用して、アプリから生成されます。

## ブラウザーのサポート {#browser-support}

デフォルトでは、このプロジェクトは [Browserslist](https://github.com/browserslist/browserslist) のデフォルトオプションを使用して、ターゲットブラウザーを識別します。また、古いブラウザー（Internet Explorer 11 など）をサポートする最新言語機能のポリフィルも含まれています。このようなブラウザーをサポートする必要がない場合は、ポリフィルの依存関係と読み込みを削除できます。

## コード分割 {#code-splitting}

React アプリケーションは、デフォルトで[コード分割](https://webpack.js.org/guides/code-splitting)を使用するように設定されます。実稼動用にアプリケーションを作成する場合、コードは複数のチャンクで出力されます。

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

必要な場合にのみチャンクを読み込むことで、アプリケーションのパフォーマンスが大幅に向上します。

この機能を AEM で使用するには、AEM で生成された HTML から、どの JS ファイルと CSS ファイルがリクエストされる必要があるのかを、アプリケーションが識別できる必要があります。これは、asset-manifest.json ファイルの「entrypoints」キーを使用して実現できます。ファイルは clientlib.config.js で解析され、entrypoints ファイルのみが ClientLib にバンドルされます。残りのファイルは ClientLib のリソースディレクトリに配置され、動的にリクエストされるので、実際に必要な場合にのみ読み込まれます。

プロジェクトのアーキタイプで AEM clientLibs がどのように使用されるかについて詳しくは、一般的な [ui.frontend モジュールのドキュメント](uifrontend.md#clientlibs)を参照してください。
