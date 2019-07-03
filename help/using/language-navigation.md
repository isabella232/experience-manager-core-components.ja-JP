---
title: 言語ナビゲーションコンポーネント
seo-title: 言語ナビゲーションコンポーネント
description: 'null'
seo-description: 言語ナビゲーションコンポーネントは、サイトの言語/国ナビゲーションを提供し、訪問者が異なるロケールの同じページに移動できるようにします。
uuid: ce736458-9cdf-4bc2- b90f-9c5a62fe1ca0
content-type: リファレンス
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: 8f232eb0-65d5-4075-8668-75f1366882c8
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
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Language Navigation Component{#language-navigation-component}

言語ナビゲーションコンポーネントは、サイトの言語/国ナビゲーションを提供し、訪問者が異なるロケールの同じページに移動できるようにします。

## 使用 {#usage}

多くの場合、Webサイトは様々な地域の複数言語で提供されています。言語ナビゲーションコンポーネントを使用すると、訪問者は異なる言語/ロケールで同じページを表示できます。

[編集ダイアログ](#edit-dialog) を使用すると、グローバルサイトナビゲーションのルートを定義したり、ナビゲーションの構造をどれだけ深くするかを指定できます。[デザインダイアログ](#design-dialog)で、テンプレート作成者は同じオプションのデフォルト値を設定できます。

## Version and Compatibility {#version-and-compatibility}

言語ナビゲーションコンポーネントの現在のバージョンは、2018年1月のコアコンポーネントのリリース2.0.0で導入されたv1であり、このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 互換性 | 互換性 | 互換性 |


For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Language Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html).

## Technical Details {#technical-details}

The latest technical documentation about the Language Navigation Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編集ダイアログを使用すると、グローバルサイトナビゲーションのルートを定義したり、ナビゲーションの構造をどれだけ深くするかを指定できます。

![](assets/screen_shot_2018-01-12at133353.png)

* **ナビゲーションルート** ナビゲーション構造のルートページを定義します。
   * Use the **Open Selection Dialog** button to easily navigate the content structure and select the root.
* **ナビゲーションルートに対するグローバル言語構造の言語構造の深** さの深さ。

## Design Dialog {#design-dialog}

テンプレート作成者は、デザインダイアログを使用して、編集ダイアログで使用できるオプションのデフォルト値を設定できます。

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **コンテンツ作成者がコンテンツページに言語切り替えコンポーネントを配置したときのナビゲーションルートのナビゲーションルート** デフォルト値
* **コンテンツ作成者がコンテンツページに言語切り替えコンポーネントを配置するときの言語構造の深さ** のデフォルト値

### Styles Tab {#styles-tab}

The Language Navigation Component supports the AEM [Style System](authoring.md#component-styling).