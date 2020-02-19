---
title: Angular SPAのフロントエンドビルド
description: AngularベースのSPAプロジェクトのフロントエンドビルドプロセスの説明
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Angular SPAのフロントエンドビルド {#frontend-angular}

このドキュメントでは、Angularフレームワークに基づいて単一ページアプリケーション(SPA)を作成する際に作成されるプロジェクトの詳細を説明します。 例えば、オプションをに設定し `frontendModule` た場合 `angular`。

## 概要 {#overview}

このプロジェクトは [Angular CLIでブートストラップされました](https://github.com/angular/angular-cli)。

このアプリケーションは、サイトのAEMモデルを使用するように構築されています。 これにより、 [@adobe/cq-angular-editable-componentsパッケージのヘルパーコンポーネントを使用してレイアウトが自動的に生成されます](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) 。

## スクリプト {#scripts}

プロジェクトディレクトリで、次のコマンドを実行できます。

### npm開始 {#npm-start}

```
npm start
```

このコマンドは、http://localhost:4502で実行されているローカルAEMインスタンスからJSONモデルをプロキシすることによって、アプリを開発モードで実行します。 これは、プロジェクト全体が（プロジェクトルート内で）少なくとも1回AEMにデプロイされ`mvn clean install -PautoInstallPackage` ていることを前提としています。

ui.frontendディレクトリでnpm startを実行すると、アプリが自動的にブラウザーで開きます(パス：http://localhost:4200/content/${appId}/${country}/${language}/home.html)。 編集を行うと、ページが再読み込みされます。

CORSに関連するエラーが発生する場合は、次のようにAEMを設定できます。

1. Configuration Manager(http://localhost:4502/system/console/configMgr)に移動します。
1. 「Adobe Granite Cross-Origin Resource Sharing Policy」の設定を開きます。
1. 次の値を追加して、新しい設定を作成します。
   * 許可されている起点：http://localhost:4200
   * サポートされるヘッダー：認証
   * 許可されているメソッド：オプション

### npmテスト {#npm-test}

```
npm test
```

このコマンドは、Karmaテストランナーを起動します。 詳細については、 [Angularのドキュメントを参照してテストの実行](https://angular.io/guide/testing) 。

### npm実行テスト：debug {#npm-run-test-debug}

```
npm run test:debug
```

このコマンドは、インタラクティブウォッチモードでKarmaテストランナーを起動します。

### npm実行ビルド {#npm-run-build}

```
npm run build
```

このコマンドは、実稼働用のアプリをbuildフォルダーに構築します。 Angularを実稼働モードでバンドルし、最適なパフォーマンスを得るためにビルドを最適化します。 詳細については、 [Angularの導入に関するドキュメント](https://angular.io/guide/deployment) を参照してください。

さらに、AEM clientLibは、aem-clientlib-generatorパッケージを使用して、ア [プリから生成されます](https://github.com/wcm-io-frontend/aem-clientlib-generator) 。

プロジェクトのアーキ [タイプでAEM clientLibsがどのように使用されるかについて詳しくは、一般的な](uifrontend.md#clientlibs) ui.frontendモジュールのドキュメントを参照してください。

## ブラウザーのサポート {#browser-support}

デフォルトでは、このプロジェクトは [Browserslistのデフォルトオプション](https://github.com/browserslist/browserslist)を使用して、ターゲットブラウザを識別します。 また、古いブラウザー（Internet Explorer 11など）をサポートする最新言語機能のポリフィルも含まれています。 このようなブラウザーをサポートする必要がない場合は、ポリフィルの依存関係とインポートを削除できます。
