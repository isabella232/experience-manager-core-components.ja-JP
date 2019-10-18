---
title: AEMプロジェクトのアーキタイプフロントエンドビルド
seo-title: AEMプロジェクトのアーキタイプフロントエンドビルド
description: AEMベースのアプリケーション用のプロジェクトテンプレート
seo-description: AEMベースのアプリケーション用のプロジェクトテンプレート
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 0a61f4e6d1ad8b4d5e3778018838dc70d496e1fc

---


# AEMプロジェクトのアーキタイプフロントエンドビルド {#aem-project-archetype-front-end-build}

AEMプロジェクトのアーキタイプには、次の機能を備えたWebpackベースのオプションの専用フロントエンドビルドメカニズムが含まれています。

* Full typeScript, ES6, ES5 support （適用可能なWebpackラッパー付き）
* TSLintルールセットを使用したTypeScriptおよびJavaScriptの構文チェック
* ES5出力、レガシーブラウザーサポート用
* グロビング
   * インポートをどこにも追加する必要がない
   * すべてのJSファイルとCSSファイルを各コンポーネントに追加できるようになりました。
      * ベストプラクティスは、、 `/clientlib/js`または `/clientlib/css`の下です。 `/clientlib/scss`
   * WebPackを使用し `.content.xml` て実行され `js.txt`るファイル`css.txt` /ファイルは不要
   * グローバーは、フォルダーの下にあるすべてのJSファイルを取り `/component/` 込みます。
      * Webpackを使用すると、CSS/SCSSファイルをJSファイル経由でチェーンできます。
      * 2つのエントリポイントを通して引き込まれ `sites.js` ます `vendors.js`。
   * AEMが使用する唯一のファイルは、出力ファ `site.js` イル `site.css` と、 `/clientlib-site` および `dependencies.js``dependencies.css` です `/clientlib-dependencies`
* チャンク
   * メイン（サイトのjs/css）
   * ベンダー（js/cssの依存関係）
* 完全なSass/Scssのサポート（SassはWebpackを介してCSSにコンパイルされます）。

## インストール {#installation}

1. NodeJS [](https://nodejs.org/en/download/) （v10以降）をグローバルにインストールします。 npmもインストールされます。
1. プロジェクト内のui.frontendに移動し、を実行します `npm install`。

## 使用方法 {#usage}

次のnpmスクリプトは、フロントエンドワークフローを駆動します。

* `npm run dev` - JS最適化が無効な完全ビルド（ツリーシェイクなど）、ソースマップが有効な状態で、CSS最適化が無効な状態で。
* `npm run prod` - JS最適化を有効にしたフルビルド（ツリーシェイクなど）、ソースマップが無効になり、CSS最適化が有効になります。

## 出力 {#output}

### 一般 {#general}

* Site — および `site.js` は、clientlib `site.css` -siteフォルダに作成されます。
* 依存関係 — お `dependencies.js` よびは、 `dependencies.css` clientlib-dependenciesフォルダーに作成されます。

### JavaScript {#javascript}

* 最適化 — 実稼働ビルドでは、使用または呼び出されていないすべてのJSが削除されます。

### CSS {#css}

* 自動修正 — すべてのCSSがプリフィクサーを介して実行され、プリフィックスが必要なプロパティは自動的にCSSに追加されます。
* 最適化 — 投稿時に、すべてのCSSはオプティマイザ(cssnano)を通じて実行され、以下のデフォルトのルールに従って正規化されます。
   * CSS計算式を可能な限り縮小し、ブラウザの互換性と圧縮の両方を確保します。同等の長さ、時間、角度の値が変換されます。 デフォルトでは、長さの値は変換されません。
   * ルール、セレクターおよび宣言に関するコメントを削除します。
   * 重複するルール、atルールおよび宣言を削除します。
      * これは、完全な複製に対してのみ機能します。
   * 空のルール、メディアクエリ、空のセレクターを含むルールは、出力に影響を与えないので削除します
   * 隣接するルールをセレクター別にマージし、プロパティと値のペアを重ね合わせます。
   * CSSファイルに1つの@charsetのみが存在することを確認し、ドキュメントの先頭に移動します。
   * 結果の出力が小さい場合、CSSの初期キーワードを実際の値に置き換えます
   * インラインSVG定義をSVGOで圧縮します
* クリーニング — 生成されたCSS、JS、およびMapファイルをオンデマンドで消去するための明示的なクリーンタスクが含まれます。
* ソースマッピング — 開発ビルドのみ

>[!NOTE]
>フロントエンドビルドオプションは、共通の設定ファイルを共有する開発専用および製品専用のWebPack設定ファイルを使用します。 これにより、開発設定と実稼働設定を個別に変更できます。
