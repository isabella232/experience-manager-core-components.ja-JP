---
title: パンくずコンポーネント
seo-title: パンくずコンポーネント
description: 'null'
seo-description: コアコンポーネントパンくずコンポーネントはナビゲーションコンポーネントで、コンテンツ階層内のページの場所に基づいてリンクのパンくずリストを構築します。
uuid: 13e858d5-24ad-4144- adc4-0fa1ffd257c1
contentOwner: User
content-type: リファレンス
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: prop237df-08b8-4deb-9881-66a1f0d65ef3
modalsize: 426x240
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# パンくずコンポーネント{#breadcrumb-component}

コアコンポーネントパンくずコンポーネントはナビゲーションコンポーネントで、コンテンツ階層内のページの場所に基づいてリンクのパンくずリストを構築します。

## 使用 {#usage}

階層階層コンポーネントには、サイト階層内の現在のページの位置が表示され、ページの訪問者が現在の場所からページ階層をナビゲートできます。これは多くの場合、ページヘッダーまたはフッターに統合されます。

Available options, such as the default navigation level and the ability to show the current page or hidden pages, can be defined by the template author in the [design dialog](#design-dialog). The content editor can then choose if hidden pages should be shown or not and the actual navigation level for the component in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

現在のバージョンのパンくずリストはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](breadcrumb-v1.md) | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Breadcrumb Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/breadcrumb/hidden/level-1/level-2/breadcrumb.html).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Breadcrumb Component supports [schema.org microdata](https://schema.org/BreadcrumbList).

## Technical Details {#technical-details}

The latest technical documentation about the Breadcrumb Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がパンくずリスト内の非表示ページとアクティブページを抑制し、表示する階層の深さを抑制できます。

![](assets/screen_shot_2018-01-12at124250.png)

* **ナビゲーション開始レベル** -階層内の階層階層コンポーネントで、現在のページまで移動し始める必要があります。例: We. Retail

   * 0 starts at `/content`

   * 1 starts at `/content/we-retail`
   * 2 starts at `/content/we-retail/<country>`

* **非表示のナビゲーション項目** を表示-パンくずリストで非表示にマークされているページを表示（デフォルトでは表示されません）
* **現在のページを非表示**-パンくずリスト内の現在のページを非表示にします（デフォルトで表示されます）。

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者が、パンくずリスト内の非表示ページとアクティブページを非表示にしたり、表示する必要のある階層の深さを非表示にしたりするためのオプションを定義できます。

### Main Tab {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **ナビゲーション開始レベル** -パンくずリストコンポーネントがページに追加されたときにパンくずリストコンポーネントが現在のページまで移動する必要がある場合に、階層内のデフォルト値を定義します。
* **非表示のナビゲーション項目を表示** -ページにパンくずリストコンポーネント **が追加されたときに、非表示のナビゲーション項目** を表示オプションのデフォルト値を定義します。

   * 作成者のオプションを有効または無効にすることはできません。デフォルト値のみを設定します。

* **現在のページを非表示** にする-ページにパンくずリストコンポーネントが追加されたときに、現在のページ **** を非表示オプションのデフォルト値を定義します。

   * 作成者のオプションを有効または無効にすることはできません。デフォルト値のみを設定します。

### Styles Tab {#styles-tab}

The Breadcrumb Component supports the AEM [Style System](authoring.md#component-styling).