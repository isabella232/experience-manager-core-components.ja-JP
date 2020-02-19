---
title: 反応SPAのフロントエンドビルド
description: ReactベースのSPAプロジェクトのフロントエンドビルドプロセスの説明
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 反応SPAのフロントエンドビルド {#frontend-react}

このドキュメントでは、アーキタイプを使用してReactフレームワークに基づく単一ページアプリケーション(SPA)を作成する場合に作成されるプロジェクトの詳細を説明します。 例えば、オプションをに設定し `frontendModule` た場合 `react`。

## 概要 {#overview}

このプロジェクトは、 [create-react-appでブートストラップされました](https://github.com/facebook/create-react-app)。

このアプリケーションは、サイトのAEMモデルを使用するように構築されています。 これにより、 [@adobe/cq-react-editable-componentsパッケージのヘルパーコンポーネントを使用してレイアウトが自動的に生成されます](https://www.npmjs.com/package/@adobe/cq-react-editable-components) 。

## スクリプト {#scripts}

プロジェクトディレクトリで、次のコマンドを実行できます。

### npm開始 {#npm-start}

```
npm start
```

このコマンドは、http://localhost:4502で実行されているローカルAEMインスタンスからJSONモデルをプロキシすることによって、アプリを開発モードで実行します。 これは、プロジェクト全体が（プロジェクトルート内で）少なくとも1回AEMにデプロイされ`mvn clean install -PautoInstallPackage` ていることを前提としています。

ui.frontendディレ `npm start` クトリで実 [行すると](uifrontend.md) 、アプリが自動的にブラウザーで開きます(パス `http://localhost:3000/content/<appId>/<country>/<language>/home.html`)。 編集を行うと、ページが再読み込みされます。

CORSに関連するエラーが発生する場合は、次のようにAEMを設定できます。

1. Configuration Manager(http://localhost:4502/system/console/configMgr)に移動します。
1. 「Adobe Granite Cross-Origin Resource Sharing Policy」の設定を開きます。
1. 次の値を追加して、新しい設定を作成します。
   * 許可されている起点：http://localhost:3000
   * サポートされるヘッダー：認証
   * 許可されているメソッド：オプション

### npmテスト {#npm-test}

```
npm test
```

このコマンドは、インタラクティブ監視モードでテストランナーを起動します。 詳しくは、テス [トの実行に関するReactのドキュメント](https://facebook.github.io/create-react-app/docs/running-tests) を参照してください。

### npm実行ビルド {#npm-run-build}

```
npm run build
```

このコマンドは、実稼働用のアプリをbuildフォルダーに構築します。 実稼働モードでReactをバンドルし、最適なパフォーマンスを得るためにビルドを最適化します。 詳しくは、デプロ [イメントに関するReactのドキュメント](https://facebook.github.io/create-react-app/docs/deployment) を参照してください。

さらに、AEM clientLibは、aem-clientlib-generatorパッケージを使用して、ア [プリから生成されます](https://github.com/wcm-io-frontend/aem-clientlib-generator) 。

## ブラウザーのサポート {#browser-support}

デフォルトでは、このプロジェクトは [Browserslistのデフォルトオプション](https://github.com/browserslist/browserslist)を使用して、ターゲットブラウザを識別します。 また、古いブラウザー（Internet Explorer 11など）をサポートする最新言語機能のポリフィルも含まれています。 このようなブラウザーをサポートする必要がない場合は、ポリフィルの依存関係とインポートを削除できます。

## コード分割 {#code-splitting}

Reactアプリは、デフォルトでコード分割を使用するよ [うに設定さ](https://webpack.js.org/guides/code-splitting) れます。 実稼働用にアプリを作成する場合、コードは複数のチャンクで出力されます。

```
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

必要な場合にのみチャンクを読み込むと、アプリのパフォーマンスが大幅に向上します。

この機能をAEMで使用するには、AEMによって生成されたHTMLからリクエストする必要があるJSファイルとCSSファイルを、アプリが識別できる必要があります。 これは、asset-manifest.jsonファイルの「entrypoints」キーを使用して実現できます。 ファイルはclientlib.config.jsで解析され、エントリポイントファイルのみがClientLibにバンドルされます。 残りのファイルはClientLibのリソースディレクトリに配置され、動的に要求されるので、実際に必要な場合にのみ読み込まれます。

プロジェクトのアーキ [タイプでAEM clientLibsがどのように使用されるかについて詳しくは、一般的な](uifrontend.md#clientlibs) ui.frontendモジュールのドキュメントを参照してください。
