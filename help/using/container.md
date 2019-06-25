---
title: コンテナコンポーネント
seo-title: コンテナコンポーネント
description: 'null'
seo-description: Core Component Containerコンポーネントを使用すると、ページ上の複数の追加コンポーネント用のコンテナを作成できます。
uuid: ec807de9- f76c-4850-9ece- c3e439a1d626
contentOwner: User
content-type: reference
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: f093f58e-9755-4a4f-803a- ab93a50e6870
translation-type: tm+mt
source-git-commit: 3e2e7a297c6ee1d6c8d092c619df8febdc900e25

---


# Container Component{#container-component}

Core Component Containerコンポーネントを使用すると、ページ上の複数の追加コンポーネント用のコンテナを作成できます。

## 使用 {#usage}

コアコンポーネントコンテナコンポーネントを使用すると、ページ上に複数の追加コンポーネント用のコンテナを作成したり、他のコンポーネントをグループ化したり、共通のスタイルやレイアウトを適用したりできます。

* The container&#39;s properties can be selected in the [configure dialog](#configure-dialog).
* Defaults for the Container Component when adding it to a page can be defined in the [design dialog](#design-dialog).

## Version and Compatibility {#version-and-compatibility}

現在のバージョンのContainer Componentは、2019年6月のコアコンポーネントのリリース2.5.0で導入されたv1であり、このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Container Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/container.html).

## Technical Details {#technical-details}

The latest technical documentation about the Container Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

設定ダイアログでは、コンテンツ作成者がコンテナ項目を定義し、そのページへの訪問者の行動と表示方法を定義できます。

![](assets/screen-shot-2019-06-21-13.59.26.png)

* **レイアウト** -このオプションは、コンテナコンポーネントの動作またはレイアウト動作を定義します。
   * **シンプル** -コンテナをシンプルなコンポーネントのコレクションとして定義します
   * **レスポンシブグリッド** - [AEMレスポンシブグリッドとしてコンテナを定義します](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)
* **ID** -このオプションを使用して、コンポーネントに適用するHTML ID属性を定義します。
* **背景色** -自由形式のRGB値または設定に応じてカラーピッカーを使用し [て定義](#background-tab)
* **背景画像** -設定に応じてコンテナの背景色を定義します [](#background-tab)

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者がコンテナコンポーネントを使用するコンテンツ作成者に使用できるオプションを定義できます。

### Allowed Components Tab {#allowed-components-tab}

**「許可されているコンポーネント** 」タブを使用して、コンテンツ作成者によってコンテナコンポーネントにアイテムとして追加できるコンポーネントを定義します。

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Default Components Tab {#default-components-tab}

The Default Components tab is used to define which component is added to the component when a particular asset type is dropped on the container, similar to [how default components are defined on the page template](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html#EditingTemplatesTemplateAuthors).

### Responsive Settings Tab {#responsive-settings-tab}

![](assets/screen-shot-2019-06-21-09.33.03.png)

* **列** -結果のコンテナのグリッド内の列数を定義します。

### Background Tab {#background-tab}

![](assets/screen-shot-2019-06-21-09.42.42.png)

* **背景画像**
   * **背景画像を有効にする** -コンテンツ作成者がコンテナの背景画像を定義できるようにするには、このオプションを選択します。
* **背景色**
   * **背景色を有効にする** -コンテンツ作成者がコンテナの背景色を定義できるようにするには、このオプションを選択します。
   * **スウォッチのみ** -このオプションを選択すると、コンテンツ作成者は、コンテナの背景色に定義済みのカラースウォッチからのみ選択できます。
      * Only available when **Enable background color** is selected
* **許可されているスウォッチ** -コンテンツ作成者がコンテナの背景色を選択できる定義済みのカラーを定義
   * **「追加」** ボタンを使用して、定義済みのカラースウォッチを追加します。追加すると、エントリがリストに追加され、次の列が含まれます。
   * **値** - RGB値を使用して手動で色を定義
      * カラーピッカーをタップまたはクリックして、個別のRGB値を調整するか、16進数値を定義して、より簡単にカラーを選択します。
   * **削除** -スウォッチをタップまたはクリックして削除します。
   * **整列** -タップまたはクリックしてドラッグし、スウォッチの順序を並べ替えます。

### Styles Tab {#styles-tab}

The Container Component supports the AEM [Style System](authoring.md#component-styling).
