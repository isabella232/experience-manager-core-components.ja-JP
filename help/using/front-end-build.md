---
title: AEM プロジェクトのアーキタイプフロントエンドビルド
seo-title: AEM プロジェクトのアーキタイプフロントエンドビルド
description: AEM ベースのアプリケーション用のプロジェクトテンプレート
seo-description: AEM ベースのアプリケーション用のプロジェクトテンプレート
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: ht
source-git-commit: 0a61f4e6d1ad8b4d5e3778018838dc70d496e1fc

---


# AEM プロジェクトのアーキタイプフロントエンドビルド {#aem-project-archetype-front-end-build}

AEM プロジェクトのアーキタイプには、次の機能を備えた Webpack ベースの専用フロントエンドビルドメカニズム（オプション）が含まれています。

* Full TypeScript、ES6 および ES5 のサポート（適用可能な Webpack ラッパーを使用）
* TSLint ルールセットを使用した TypeScript および JavaScript の構文チェック
* レガシーブラウザーサポート用 ES5 出力
* グロビング
   * インポートをどこにも追加する必要がない
   * すべての JS ファイルと CSS ファイルを各コンポーネントに追加できるようになりました。
      * ベストプラクティスの追加先は、`/clientlib/js`、`/clientlib/css` または `/clientlib/scss` の配下です。
   * すべてが Webpack 経由で実行されるので、`.content.xml` または `js.txt`／`css.txt` ファイルは不要です。
   * グローバーは、`/component/` フォルダーの下にあるすべての JS ファイルを取り込みます。
      * Webpack を使用すると、JS ファイル経由で CSS／SCSS ファイルをチェーンにすることができます。
      * 2 つのエントリポイント（`sites.js` および `vendors.js`）から取り込まれます。
   * AEM が使用すファイルは、`/clientlib-site` の出力ファイル `site.js` と `site.css`、および `/clientlib-dependencies` の `dependencies.js` と `dependencies.css` のみです。
* チャンク
   * メイン（サイトの js／css）
   * ベンダー（依存関係の js／css）
* 完全な Sass／Scss のサポート（Sass は Webpack を介して CSS にコンパイルされます）。

## インストール {#installation}

1. [NodeJS](https://nodejs.org/en/download/)（v10 以降）をグローバルにインストールします。これにより、npm もインストールされます。
1. プロジェクト内の ui.frontend に移動し、`npm install` を実行します。

## 使用方法 {#usage}

次の npm スクリプトは、フロントエンドワークフローを動かします。

* `npm run dev` - JS 最適化を無効（ツリーシェイクなど）、ソースマップを有効、CSS 最適化を無効にした完全なビルド。
* `npm run prod` - JS 最適化を有効（ツリーシェイクなど）、ソースマップを無効、CSS 最適化を有効にした完全なビルド。

## 出力 {#output}

### 一般 {#general}

* Site — `site.js` および `site.css` は、clientlib-site フフォルダーに作成されます。
* 依存関係 — `dependencies.js` および `dependencies.css` は、clientlib-dependencies フォルダーに作成されます。

### JavaScript {#javascript}

* 最適化 — 実稼働ビルドでは、使用や呼び出しがおこなわれていないすべての JS が削除されます。

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
* クリーニング — 生成されたCSS、JS、およびマップファイルをオンデマンドで消去するための明示的なクリーンタスクを含みます。
* ソースマッピング — 開発ビルドのみ

>[!NOTE]
>フロントエンドビルドオプションでは、共通の設定ファイルを使用する開発専用と製品専用の webpack 設定ファイルを利用します。これにより、開発設定と実稼働設定を個別に変更できます。
