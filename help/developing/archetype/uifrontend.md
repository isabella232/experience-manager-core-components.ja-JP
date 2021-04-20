---
title: AEM プロジェクトのアーキタイプフロントエンドビルド
description: AEM ベースのアプリケーション用のプロジェクトテンプレート
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: ht
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: ht
source-wordcount: '1628'
ht-degree: 100%

---


# AEM プロジェクトアーキタイプの ui.frontend モジュール {#uifrontend-module}

AEM プロジェクトのアーキタイプには、Webpack ベースの専用フロントエンドビルドメカニズム（オプション）が含まれています。このように、ui.frontend モジュールは、JavaScript や CSS ファイルを含む、プロジェクトのすべてのフロントエンドリソースの中心となります。この便利で柔軟な機能を最大限に活用するには、AEM プロジェクトにフロントエンド開発がどのように適合するかを理解することが重要です。

## AEM プロジェクトとフロントエンド開発 {#aem-and-front-end-development}

簡単に言えば、AEM プロジェクトは、2 つの異なる関連部分から成ると考えることができます。

* AEM のロジックを駆動し、Java ライブラリ、OSGi サービスなどを生成するバックエンドの開発
* 結果として作成される Web サイトの表示と動作を促し、JavaScript ライブラリと CSS ライブラリを生成するフロントエンド開発

これらの 2 つの開発プロセスはプロジェクトの異なる部分に焦点を当てているので、バックエンドとフロントエンドの開発が並行しておこなわれる可能性があります。

![フロントエンドワークフロー図](/help/assets/front-end-flow.png)

ただし、作成されるプロジェクトでは、バックエンドとフロントエンドの両方の開発作業の出力を使用する必要があります。

`npm run dev` を実行するとフロントエンドビルドプロセスが開始します。このプロセスでは ui.frontend モジュールに保存されている JavaScript ファイルと CSS ファイルを収集し「`clientlib-site`」と「`clientlib-dependencies`」という縮小された 2 つのクライアントライブラリ（ClientLibs）を作成して ui.apps モジュールにデポジットします。ClientLibs は AEM にデプロイされ、クライアント側のコードをリポジトリに保存できるようになります。

AEM プロジェクトのアーキタイプ全体が `mvn clean install -PautoInstallPackage` を使用して実行されると、ClientLibs を含むすべてのプロジェクトアーティファクトが AEM インスタンスにプッシュされます。

>[!TIP]
>
>[AEM 開発ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=ja-JP)で AEM による ClientLibs の処理方法および[それらを含める](/help/developing/including-clientlibs.md)方法をご確認ください。また、[ui.frontend モジュールで ClientLibs がどのように使用されるか](#clientlib-generation)については以下を参照してください。

## ClientLibs の概要 {#clientlibs}

フロントエンドモジュールは、[AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=ja-JP) を使用して利用可能になります。NPM ビルドスクリプトを実行すると、アプリケーションがビルドされ、aem-clientlib-generator パッケージがビルド出力結果を取得して、そのような ClientLib に変換します。

ClientLib は、次のファイルとディレクトリで構成されます。

* `css/`：HTML で要求できる CSS ファイル
* `css.txt`：ファイルを結合できるように、`css/` 内のファイルの順序と名前を AEM に指示します。
* `js/`：HTML で要求できる JavaScript ファイル
* `js.txt`：ファイルを結合できるように、`js/` 内のファイルの順序と名前を AEM に指示します。
* `resources/`：ソースマップ、非エントリポイントコードチャンク（コード分割による）、静的アセット（アイコンなど）など。

## 可能なフロントエンド開発ワークフロー {#possible-workflows}

フロントエンドビルドモジュールは、便利で柔軟なツールですが、どのように使用されるすべきかについてはユーザーに任されています。以下の 2 つは&#x200B;*可能な*&#x200B;使用例ですが、個々のプロジェクトでは他の使用モデルが必要になる場合があります。

### Webpack 静的開発サーバーの使用 {#using-webpack}

Webpack を使用すると、ui.frontend モジュール内の AEM Web ページの静的出力に基づいてスタイルを設定し、開発することができます。

1. ページプレビューモードを使用するか、URL に `wcmmode=disabled` を渡すことによって、AEM でページをプレビューする
1. ui.frontend モジュール内でページソースを表示し、静的 HTML として保存する
1. [Webpack を起動](#webpack-dev-server)して、必要な JavaScript と CSS のスタイル設定と生成を開始する
1. `npm run dev` を実行して ClientLibs を生成する

このフローでは、AEM 開発者が手順 1 と 2 を実行して、静的 HTML をフロントエンド開発者に渡し、フロントエンド開発者が AEM HTML 出力に基づいて開発をおこなうことができます。

>[!TIP]
>
>また、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_jp)を利用して、各コンポーネントのマークアップ出力のサンプルを取り込み、ページレベルではなくコンポーネントレベルで作業することもできます。

### Storybook の使用 {#using-storybook}

[Storybook ](https://storybook.js.org)を使用すると、よりアトミックなフロントエンド開発を実行できます。Storybook は AEM プロジェクトのアーキタイプには含まれていませんが、Storybook をインストールすると、ui.frontend モジュール内に Storybook アーティファクトを保存することができます。AEM 内でテストをおこなう準備が整ったら、`npm run dev` を実行して Storybook を ClientLibs としてデプロイできます。

>[!NOTE]
>
>[Storybook](https://storybook.js.org) は AEM プロジェクトのアーキタイプには含まれていません。使用する場合は、個別にインストールする必要があります。

### マークアップの決定 {#determining-markup}

プロジェクトに実装するフロントエンド開発ワークフローに関しては、まずバックエンド開発者とフロントエンド開発者がマークアップに同意する必要があります。通常、AEM はマークアップを定義し、これがコアコンポーネントで提供されます。[ただし、必要に応じてカスタマイズすることができます](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend モジュール {#ui-frontend-module}

AEM プロジェクトのアーキタイプには、次の機能を備えた Webpack ベースの専用フロントエンドビルドメカニズム（オプション）が含まれています。

* Full TypeScript、ES6 および ES5 のサポート（適用可能な Webpack ラッパーを使用）
* TSLint ルールセットを使用した TypeScript および JavaScript の構文チェック
* レガシーブラウザーサポート用 ES5 出力
* グロビング
   * インポートをどこにも追加する必要がない
   * すべての JS ファイルと CSS ファイルを各コンポーネントに追加できるようになりました。
      * ベストプラクティスの追加先は、`/clientlib/js`、`/clientlib/css` または `/clientlib/scss` の配下です。
   * すべてが webpack 経由で実行されるので、`.content.xml` または `js.txt`／`css.txt` ファイルは不要です。
   * グローバーは、`/component/` フォルダーの下にあるすべての JS ファイルを取り込みます。
      * Webpack を使用すると、JS ファイル経由で CSS／SCSS ファイルをチェーンにすることができます。
      * 2 つのエントリポイント（`sites.js` および `vendors.js`）から取り込まれます。
   * AEM が使用すファイルは、`/clientlib-site` の出力ファイル `site.js` と `site.css`、および `/clientlib-dependencies` の `dependencies.js` と `dependencies.css` のみです。
* チャンク
   * メイン（サイトの js／css）
   * ベンダー（依存関係の js／css）
* 完全な Sass／SCSS のサポート（Sass は webpack を介して CSS にコンパイルされます）
* AEM のローカルインスタンスに対するプロキシが組み込まれた静的 webPack 開発サーバー

>[!NOTE]
>
>ui.frontend モジュールに関する技術的な情報については、[GitHub のドキュメント](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)を参照してください。

## インストール {#installation}

1. [NodeJS](https://nodejs.org/en/download/)（v10 以降）をグローバルにインストールします。これにより、npm もインストールされます。
1. プロジェクト内の ui.frontend に移動し、`npm install` を実行します。

>[!NOTE]
>
>ui.frontend フォルダーに入力するには、`-DoptionIncludeFrontendModule=y` オプションを使用して[アーキタイプを実行](overview.md)している必要があります。

## 使用方法 {#usage}

次の npm スクリプトは、フロントエンドワークフローを動かします。

* `npm run dev` - JS 最適化を無効（ツリーシェイクなど）、ソースマップを有効、CSS 最適化を無効にした完全なビルド。
* `npm run prod` - JS 最適化を有効（ツリーシェイクなど）、ソースマップを無効、CSS 最適化を有効にした完全なビルド。
* `npm run start` - AEM への依存性を最小限に抑えて、ローカル開発用の静的 webPack 開発サーバーを起動します。

## 出力 {#output}

ui.frontend モジュールは、`ui.frontend/src` フォルダーでコードをコンパイルし、コンパイル済みの CSS と JS、および、ある場合はリソースを `ui.frontend/dist` フォルダーに出力します。

* **サイト** - `site.js`、`site.css`、レイアウト依存画像とフォントのための `resources/` フォルダーは `dist/` clientlib-site フォルダーに作成されます。
* **依存関係** - `dependencies.js` および `dependencies.css` は、`dist/clientlib-dependencies` フォルダーに作成されます。

### JavaScript {#javascript}

* 最適化 — 実稼動ビルドでは、使用や呼び出しがおこなわれていないすべての JS が削除されます。

### CSS {#css}

* 自動修正 — すべての CSS がプリフィクサーを介して実行され、プリフィックスが必要なプロパティは CSS に自動で追加されます。
* 最適化 — 投稿時、すべての CSS はオプティマイザー（cssnano）を通じて実行され、以下のデフォルトのルールに従って正規化されます。
   * CSS 計算式を可能な限り縮小し、ブラウザの互換性と圧縮の両方を確保します。同等の長さ、時間、角度の値が変換されます。デフォルトでは、長さの値は変換されません。
   * ルール、セレクターおよび宣言に関するコメントを削除する
   * 重複するルール、@ ルールおよび宣言を削除する
      * これは、完全な複製に対してのみ機能します。
   * 空のルール、メディアクエリ、空のセレクターを含むルールは、出力に影響を与えないので削除する
   * 隣接するルールをセレクター、および重なっているプロパティと値のペア別に結合する
   * CSS ファイルに 1 つの @charset のみが存在することを確認し、ドキュメントの先頭に移動させる
   * 結果の出力が小さい場合、CSS の初期キーワードを実際の値に置き換える
   * インライン SVG 定義を SVGO で圧縮する
* クリーニング — 生成された CSS、JS、およびマップファイルをオンデマンドで消去するための明示的なクリーンタスクを含みます。
* ソースマッピング — 開発ビルドのみ

>[!NOTE]
>
>フロントエンドビルドオプションでは、共通の設定ファイルを使用する開発専用と製品専用の webpack 設定ファイルを利用します。これにより、開発設定と実稼動設定を個別に変更できます。

### クライアントライブラリの生成 {#clientlib-generation}

ui.frontend モジュールのビルドプロセスでは、[aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) プラグインを利用して、コンパイル済みの CSS、JS および、任意のリソースを ui.apps モジュールに移動します。Aem-clientlib-generator の設定は、`clientlib.config.js` で定義されています。次のクライアントライブラリが生成されます。

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### ページへのクライアントライブラリの追加 {#clientlib-inclusion}

`clientlib-site` および `clientlib-dependencies` カテゴリは、デフォルトテンプレートの一部として、[ページポリシー設定](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/implementing/components-templates/templates.html#template-definitions)を使用して、ページに含められます。ポリシーを表示するには、**コンテンツページテンプレート／ページ情報／ページポリシー**&#x200B;を編集します。

サイトページにクライアントライブラリを最終的に含める方法は次のとおりです。

```html
<HTML>
    <head>
        <link rel="stylesheet" href="clientlib-base.css" type="text/css">
        <script type="text/javascript" src="clientlib-dependencies.js"></script>
        <link rel="stylesheet" href="clientlib-dependencies.css" type="text/css">
        <link rel="stylesheet" href="clientlib-site.css" type="text/css">
    </head>
    <body>
        ....
        <script type="text/javascript" src="clientlib-site.js"></script>
        <script type="text/javascript" src="clientlib-base.js"></script>
    </body>
</HTML>
```

上記のインクルードは、ページポリシーを更新したり、各クライアントライブラリのカテゴリや埋め込みプロパティを変更したりすることで、変更できます。

### 静的 webpack 開発サーバー {#webpack-dev-server}

ui.frontend モジュールには、AEM の外部での迅速なフロントエンド開発のためのライブリロードを提供する webpack-dev-server が含まれています。この設定では、html-webpack-plugin を利用して、ui.frontend モジュールからコンパイルされた CSS と JS を静的 HTML テンプレートに自動的に挿入します。

#### 重要なファイル {#important-files}

* `ui.frontend/webpack.dev.js`
   * Webpack-dev-serve の設定が含まれ、使用する HTML テンプレートを参照します。
   * また、localhost:4502 上で実行されている AEM インスタンスへのプロキシ設定も含まれます。
* `ui.frontend/src/main/webpack/static/index.html`
   * これは、サーバーが実行される静的 HTML です。
   * これにより、開発者は CSS/JS の変更をおこない、マークアップに直ちに反映させることができます。
   * このファイルに配置されたマークアップは、AEM コンポーネントによって生成されたマークアップを正確に反映していると想定されます。
   * このファイル内のマークアップは、AEM コンポーネントのマークアップとは自動的に同期されません。
   * また、このファイルには、コアコンポーネント CSS やレスポンシブグリッド CSS など、AEM に保存されるクライアントライブラリへの参照も含まれています。
   * Webpack 開発サーバーは、これらの CSS/JS インクルードを `ui.frontend/webpack.dev.js` で見つかった構成に基づいて実行中のローカル AEM インスタンスからプロキシするように設定されています。

#### 使用 {#using-webpack-server}

1. プロジェクトのルート内から「`mvn -PautoInstallSinglePackage clean install`」コマンドを実行して、`localhost:4502` で実行している AEM インスタンスにプロジェクト全体をインストールします。
1. `ui.frontend` フォルダー内を移動します。
1. 「`npm run start`」コマンドを実行して、webpack 開発サーバーを起動します。サーバーが起動したら、ブラウザーを開きます（`localhost:8080` または次に使用可能なポート）。

CSS、JS、SCSS および TS ファイルを変更すると、変更が webpack 開発サーバーに直ちに反映されるようになります。
