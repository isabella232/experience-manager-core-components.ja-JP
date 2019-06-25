---
title: ナビゲーションコンポーネント
seo-title: ナビゲーションコンポーネント
description: 'null'
seo-description: ナビゲーションコンポーネントを使用すると、グローバル化されたサイト構造を容易にナビゲートできます。
uuid: 616c03fb-39b3-402a- b990- f56c87bc6df4
content-type: reference
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: da8d67d7- b65e-4041- bc0e- e998f24a68f9
disttype: dist5
gnavtheme: light
groupsectionnavitems: ' '
hidemerchandisingbar: inherit
hidepromocomponent: inherit
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c58826c133eb112b305fa4facbe2a81e577eb896

---


# Navigation Component{#navigation-component}

ナビゲーションコンポーネントを使用すると、グローバル化されたサイト構造を容易にナビゲートできます。

## 使用 {#usage}

ナビゲーションコンポーネントを使用すると、ブループリントのライブコピー、言語マスターの言語コピー、または単純なページの単純なツリーから構築できます。ページのユーザーは、ページ構造を簡単にナビゲートできます。

[編集ダイアログ](#edit-dialog) では、コンテンツ作成者がナビゲーションのルートページをナビゲーションの深さと共に定義できます。[デザインダイアログ](#design-dialog) では、テンプレート作成者がナビゲーションルートと深さのデフォルト値を定義できます。

## Version and Compatibility {#version-and-compatibility}

現在のバージョンのナビゲーションコンポーネントは、2018年1月のコアコンポーネントのリリース2.0.0で導入されたv1であり、このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 互換性 | 互換性 | 互換性 |


For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/navigation.html).

## Technical Details {#technical-details}

The latest technical documentation about the Navigation Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md.

>[!NOTE]
>
>As of Core Components release 2.1.0, the Navigation Component supports [schema.org microdata](https://schema.org).

## Edit Dialog {#edit-dialog}

編集ダイアログで、コンテンツ作成者はナビゲーションのルートページを定義し、ナビゲーション構造の深さを定義できます。

![](assets/screen_shot_2018-04-03at112055.png)

* **ナビゲーションルート** ナビゲーションツリーの生成に使用されるルートページ。
* **除外ナビゲーションルート** の除外結果ツリーのナビゲーションルートを除外するには、その子孫のみを含めます。
* **すべての子ページ** を収集ナビゲーションルートの子孫であるすべてのページを収集します。
* **ナビゲーション構造の深さ** ナビゲーションツリーの下に表示するレベルの数を定義します。ナビゲーションのルートに対する相対的なレベル（«すべての子ページ **** を収集»が選択されていない場合のみ利用可能）。

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者がコンテンツ作成者に表示されるナビゲーションルートページとナビゲーションの深さのデフォルト値を設定できます。

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-04-03at112357.png)

* **ナビゲーションルート** ナビゲーション構造のルートページのデフォルト値。ナビゲーションツリーの生成に使用され、コンテンツ作成者がページにコンポーネントを追加するときにデフォルトで使用されます。
* **Exclude navigation root**（ナビゲーションルートを除外）:結果のツリー内のナビゲーションルートを除外します。
* **すべての子ページ** を収集すべてのページを収集し、ナビゲーションルートの子孫であるすべてのページを収集します。
* **ナビゲーション構造の深さ** ナビゲーション構造の深さのデフォルト値

### Styles Tab {#styles-tab}

The Navigation Component supports the AEM [Style System](authoring.md#component-styling).