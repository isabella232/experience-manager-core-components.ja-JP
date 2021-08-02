---
title: Angular SPA のフロントエンドビルド
description: Angular ベースの SPA プロジェクトのフロントエンドビルドプロセスの説明
feature: コアコンポーネント、AEM プロジェクトアーキタイプ
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '409'
ht-degree: 100%

---

# Angular SPA のフロントエンドビルド {#frontend-angular}

このドキュメントでは、アーキタイプを使用して Angular フレームワークに基づく単一ページアプリケーション（SPA）を作成するプロジェクトの詳細を説明します。例えば、`frontendModule` オプションを `angular` に設定する場合です。

## 概要 {#overview}

このプロジェクトは [Angular CLI](https://github.com/angular/angular-cli) でブートストラップ処理されました。

このアプリケーションは、サイトの AEM モデルを使用するようにビルドされています。これにより、[@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) パッケージのヘルパーコンポーネントを使用してレイアウトが自動的に生成されます。

## スクリプト {#scripts}

プロジェクトディレクトリで、次のコマンドを実行できます。

### npm start {#npm-start}

```
npm start
```

このコマンドは、http://localhost:4502 で実行されるローカル AEM インスタンスから JSON モデルをプロキシすることで、アプリを開発モードで実行します。これは、プロジェクト全体が少なくとも 1 回 AEM にデプロイされていることを前提としています（プロジェクトルートの `mvn clean install -PautoInstallPackage`）。

ui.frontend ディレクトリで npm start を実行すると、アプリが自動的にブラウザーで開きます（パス：http://localhost:4200/content/${appId}/${country}/${language}/home.html）。編集すると、ページがリロードされます。

CORS に関連するエラーが発生する場合は、次のように AEM を設定します。

1. 設定マネージャーに移動します（http://localhost:4502/system/console/configMgr）
1. 「Adobe Granite Cross-Origin Resource Sharing Policy」の設定を開きます。
1. 次の値を追加して、新しい設定を作成します。
   * 許可されるオリジン：http://localhost:4200
   * サポートされるヘッダー：Authorization
   * 許可されるメソッド：OPTIONS

### npm test {#npm-test}

```shell
npm test
```

このコマンドは、Karma テストランナーを起動します。詳細については、[テスト実行に関する Angular のドキュメント](https://angular.io/guide/testing)を参照してください。

### npm run test:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

このコマンドは、インタラクティブ監視モードで Karma テストランナーを起動します。

### npm run build {#npm-run-build}

```shell
npm run build
```

このコマンドは、実稼動用のアプリケーションを build フォルダーにビルドします。実稼動モードで Angular をバンドルし、最適なパフォーマンスを得るためにビルドを最適化します。詳しくは、[デプロイメントに関する Angular のドキュメント](https://angular.io/guide/deployment)を参照してください。

さらに、AEM clientLib は、[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) パッケージを使用して、アプリから生成されます。

プロジェクトのアーキタイプで AEM clientLibs がどのように使用されるかについて詳しくは、一般的な [ui.frontend モジュールのドキュメント](uifrontend.md#clientlibs)を参照してください。

## ブラウザーのサポート {#browser-support}

デフォルトでは、このプロジェクトは [Browserslist](https://github.com/browserslist/browserslist) のデフォルトオプションを使用して、ターゲットブラウザーを識別します。また、古いブラウザー（Internet Explorer 11 など）をサポートする最新言語機能のポリフィルも含まれています。このようなブラウザーをサポートする必要がない場合は、ポリフィルの依存関係と読み込みを削除できます。
