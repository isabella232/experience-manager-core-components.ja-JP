---
title: カルーセルコンポーネント
seo-title: カルーセルコンポーネント
description: 'null'
seo-description: カルーセルコンポーネントを使用すると、コンテンツ作成者は回転カルーセル内のコンテンツを表示できます。
uuid: 34934491- bd85-4f1e- ae22- bb48ed4dbd5c
content-type: リファレンス
topic-tags: コアコンポーネント
discoiquuid: 3510812b-9d3e-40fe- b986-0f15d40b42ad
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


# Carousel Component{#carousel-component}

コアコンポーネントカルーセルコンポーネントを使用すると、コンテンツ作成者はナビゲーション可能なカルーセル内にコンテンツを表示できます。

## 使用 {#usage}

コンテンツ作成者はカルーセルコンポーネントを使用して、スライドの回転カルーセル内のコンテンツを整理します。

[編集ダイアログ](#edit-dialog) では、コンテンツ作成者が複数のスライドを作成、名前付けおよび順序付け、自動トランジションを遅延と共に有効にすることができます。[デザインダイアログ](#design-dialog)で、テンプレート作成者は、カルーセルに追加できるコンポーネントの定義、自動トランジションの有効化または無効化、スタイルのカスタマイズを行うことができます。

## Version and Compatibility {#version-and-compatibility}

カルーセルコンポーネントの最新バージョンはv1であり、2018年10月のコアコンポーネントのリリース2.2.0で導入されました。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Carousel Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html).

### Technical Details {#technical-details}

The latest technical documentation about the Carousel Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がスライドの追加、名前の変更および並べ替え、自動トランジション設定の定義を行うことができます。

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-12at102451.png)

**「追加」** ボタンを使用してコンポーネントセレクターを開き、タブとして追加するコンポーネントを選択します。追加すると、エントリがリストに追加され、次の列が含まれます。

* **アイコン** -リストで簡単に識別できるようにする、タブのコンポーネントタイプのアイコン。マウスを移動すると、コンポーネント名がツールチップとして表示されます。
* **説明** -タブのテキストとして使用される説明。タブに対して選択されたコンポーネントの名前にデフォルトで設定されます。
* **削除** -タブコンポーネントからタブをタップまたはクリックして削除します。
* **並べ替え** -タップまたはクリックしてドラッグし、タブを並べ替えます。

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-11-28at141054.png)

**「プロパティ** 」タブで、コンテンツ作成者はスライドを自動的に移行するように設定できます。

* **自動トランジションスライド** -アクティブな場合、指定した遅延後にコンポーネントが自動的に次のスライドに進みます。
* **トランジション遅延** -スライドを自動的にトランジションするときに、この値を使用してトランジション間のトランジションの間隔を定義します（ミリ秒単位）。
* **カーソルを合わせ** たときに自動一時停止を無効にする- **自動的にトランジションをスライド** すると、カルーセルの上にカーソルを置くとカルーセルトランジションが自動的に一時停止します。トランジションを一時停止しないようにするには、このオプションを選択します。

>[!NOTE]
>
>The slide advance controls are not enabled when in **Edit** mode. Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the carousel as a reader of the published content would.
>
>The auto-advance feature is not enabled when in **Edit** mode. **[「公開済みとして表示」](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** オプションを使用すると、公開済みコンテンツの読者として自動早送り機能を確認できます。

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different slide for editing as well as to easily rearrange the order of the slides.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured slides are displayed as a drop-down.

* リストは、割り当てられたスライドの割り当て順に並べ替えられ、番号付けに反映されます。
* 最初にスライドのコンポーネントタイプが表示され、続いて薄いフォントでスライドの説明が表示されます。

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* ドロップダウンのエントリをタップまたはクリックして、エディターのビューをスライドに切り替えます。
* スライドは、ドラッグハンドルを使用して順番に並べ替えることができます。

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者が、スライドとして追加できるコンポーネントをカルーセルコンポーネントに定義したり、自動トランジションデフォルトを定義したり、コンテンツ作成者が使用できるカスタムスタイルを定義したりできます。

### Properties Tab {#properties-tab-1}

The **Properties** tab is used to define the default settings for the slide transitions when a content author adds the carousel component to a page.

![](assets/screenshot_2018-11-28at141824.png)

* **自動的にスライドを切り替え** -コンテンツ作成者がカルーセルコンポーネントをページに追加したときに、カルーセルを自動的に次のスライドに自動的に進むオプションを定義するかどうかを定義します。
* **トランジション遅延** -コンテンツ作成者がページにカルーセルコンポーネントを追加したときに、スライド間のトランジション遅延のデフォルト値を定義します。
* **ホバー時に自動停止を無効にする** -デフォルトでは、コンテンツ作成者が **自動的にスライドをスライド** するときに自動スライド一時停止を無効にするオプションが有効になっているかどうかを定義します。

### Allowed Components Tab {#allowed-components-tab}

**「許可されているコンポーネント** 」タブを使用して、コンテンツ作成者がカルーセルコンポーネントにスライドとして追加できるコンポーネントを定義します。

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Carousel Component supports the AEM [Style System](authoring.md#component-styling).