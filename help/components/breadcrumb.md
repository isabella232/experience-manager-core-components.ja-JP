---
title: パンくずコンポーネント
description: コアコンポーネントのパンくずコンポーネントはナビゲーションコンポーネントです。コンテンツ階層におけるページの場所に基づいてリンクのパンくずリストを作成します。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# パンくずコンポーネント{#breadcrumb-component}

コアコンポーネントのパンくずコンポーネントはナビゲーションコンポーネントです。コンテンツ階層におけるページの場所に基づいてリンクのパンくずリストを作成します。

## 使用方法 {#usage}

パンくずコンポーネントには、サイト階層における現在のページの位置が表示され、ページの訪問者は現在の場所からページ階層内を移動することができます。多くの場合、パンくずコンポーネントはページヘッダーやフッターに統合されています。

デフォルトのナビゲーションレベルや現在のページまたは非表示のページを表示する機能などの使用可能なオプションは、テンプレート作成者が[デザインダイアログ](#design-dialog)で定義できます。次に、非表示のページを表示するかどうかやコンポーネントの実際のナビゲーションレベルをコンテンツ編集者が[編集ダイアログ](#edit-dialog)で選択できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、パンくずコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v2）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | 互換性あり | 互換性あり | 互換性あり | 互換性あり |
| [v1](v1/breadcrumb-v1.md) | 互換性あり | 互換性あり | 互換性あり | - |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

To experience the Breadcrumb Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Breadcrumb Component supports [schema.org microdata](https://schema.org/BreadcrumbList).

## 技術的詳細 {#technical-details}

The latest technical documentation about the Breadcrumb Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 編集ダイアログ{#edit-dialog}

編集ダイアログでは、コンテンツ作成者がパンくずリスト内の非表示ページとアクティブページおよび表示する階層の深さを無効化できます。

![](/help/assets/screen_shot_2018-01-12at124250.png)

* **ナビゲーション開始レベル** - パンくずコンポーネントが現在のページへの移動を開始する、階層内の位置。例えば、We.Retail では次のようになります。

   * 「0」の場合は `/content` で開始
   * 「1」の場合は `/content/we-retail` で開始
   * 「2」の場合は `/content/we-retail/<country>` で開始

* **非表示のナビゲーション項目を表示** - パンくずリストで非表示とマークされているページを表示します（デフォルトでは表示されません）
* **現在のページを非表示** - パンくずリストの現在のページを非表示にします（デフォルトでは表示されます）

## デザインダイアログ{#design-dialog}

デザインダイアログでは、テンプレート作成者が、パンくずリスト内の非表示ページとアクティブページおよび表示する階層の深さを無効化するオプションのデフォルト値を定義できます。

### 「メイン」タブ {#main-tab}

![](/help/assets/screen_shot_2018-01-12at124437.png)

* **ナビゲーション開始レベル** - パンくずコンポーネントをページに追加したときに階層内でパンくずコンポーネントが現在のページへの移動を開始する位置のデフォルト値を定義します。
* **非表示のナビゲーション項目を表示** - パンくずコンポーネントをページに追加したときに使用される「**非表示のナビゲーション項目を表示**」オプションのデフォルト値を定義します。

   * 作成者用のオプションは有効または無効にはなりません。デフォルト値のみ設定されます。

* **現在のページを非表示** - パンくずコンポーネントをページに追加したときに使用される「**現在のページを非表示**」オプションのデフォルト値を定義します。

   * 作成者用のオプションは有効または無効にはなりません。デフォルト値のみ設定されます。

### 「スタイル」タブ {#styles-tab}

パンくずコンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
