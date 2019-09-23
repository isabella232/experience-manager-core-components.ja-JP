---
title: パンくずコンポーネント
seo-title: パンくずコンポーネント
description: 'null'
seo-description: コアコンポーネントのパンくずコンポーネントはナビゲーションコンポーネントです。コンテンツ階層におけるページの場所に基づいてリンクのパンくずリストを作成します。
uuid: 13e858d5-24ad-4144-adc4-0fa1ffd257c1
contentOwner: ユーザー
content-type: reference
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: ecd237df-08b8-4deb-9881-66a1f0d65ef3
modalsize: 426x240
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# パンくずコンポーネント{#breadcrumb-component}

コアコンポーネントのパンくずコンポーネントはナビゲーションコンポーネントです。コンテンツ階層におけるページの場所に基づいてリンクのパンくずリストを作成します。

## 使用方法 {#usage}

パンくずコンポーネントには、サイト階層における現在のページの位置が表示され、ページの訪問者は現在の場所からページ階層内を移動することができます。多くの場合、パンくずコンポーネントはページヘッダーやフッターに統合されています。

デフォルトのナビゲーションレベルや現在のページまたは非表示のページを表示する機能などの使用可能なオプションは、テンプレート作成者が[デザインダイアログ](#design-dialog)で定義できます。次に、非表示のページを表示するかどうかやコンポーネントの実際のナビゲーションレベルをコンテンツ編集者が[編集ダイアログ](#edit-dialog)で選択できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、パンくずコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v2）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性あり | 互換性あり | 互換性あり |
| [v1](breadcrumb-v1.md) | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

To experience the Breadcrumb Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/breadcrumb/hidden/level-1/level-2/breadcrumb.html).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Breadcrumb Component supports [schema.org microdata](https://schema.org/BreadcrumbList).

## 技術的詳細 {#technical-details}

The latest technical documentation about the Breadcrumb Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 編集ダイアログ{#edit-dialog}

編集ダイアログでは、コンテンツ作成者がパンくずリスト内の非表示ページとアクティブページおよび表示する階層の深さを無効化できます。

![](assets/screen_shot_2018-01-12at124250.png)

* **ナビゲーション開始レベル** - パンくずコンポーネントが現在のページへの移動を開始する、階層内の位置。例えば、We.Retail では次のようになります。

   * 「0」の場合は `/content` で開始

   * 「1」の場合は `/content/we-retail` で開始
   * 「2」の場合は `/content/we-retail/<country>` で開始

* **非表示のナビゲーション項目を表示** - パンくずリストで非表示とマークされているページを表示します（デフォルトでは表示されません）
* **現在のページを非表示** - パンくずリストの現在のページを非表示にします（デフォルトでは表示されます）

## デザインダイアログ{#design-dialog}

デザインダイアログでは、テンプレート作成者が、パンくずリスト内の非表示ページとアクティブページおよび表示する階層の深さを無効化するオプションのデフォルト値を定義できます。

### 「メイン」タブ {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **ナビゲーション開始レベル** - パンくずコンポーネントをページに追加したときに階層内でパンくずコンポーネントが現在のページへの移動を開始する位置のデフォルト値を定義します。
* **非表示のナビゲーション項目を表示** - パンくずコンポーネントをページに追加したときに使用される「**非表示のナビゲーション項目を表示**」オプションのデフォルト値を定義します。

   * 作成者用のオプションは有効または無効にはなりません。デフォルト値のみ設定されます。

* **現在のページを非表示** - パンくずコンポーネントをページに追加したときに使用される「**現在のページを非表示**」オプションのデフォルト値を定義します。

   * 作成者用のオプションは有効または無効にはなりません。デフォルト値のみ設定されます。

### 「スタイル」タブ {#styles-tab}

パンくずコンポーネントでは、AEM [スタイルシステム](authoring.md#component-styling)をサポートしています。