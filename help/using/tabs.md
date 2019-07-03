---
title: タブコンポーネント
seo-title: タブコンポーネント
description: タブコンポーネントを使用すると、複数のタブを作成してページ上のコンテンツを配置できます。
seo-description: タブコンポーネントを使用すると、複数のタブを作成してページ上のコンテンツを配置できます。
uuid: 46f71233-8b12-4887- a0c6- ad24dc469cb1
content-type: リファレンス
topic-tags: コアコンポーネント
discoiquuid: 966d47fb- d35d-4103- b29d-4ef0aa739f24
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# タブコンポーネント

コアコンポーネントタブコンポーネントを使用すると、複数のタブにコンテンツを編成できます。

## 使用 {#usage}

タブコンポーネントを使用すると、コンテンツ作成者は複数のタブ内でページコンテンツを整理できます。

[編集ダイアログ](#edit-dialog) では、コンテンツ作成者が複数のタブを定義し、アクティブなタブを設定することができます。Using the [design dialog](#design-dialog), the template author can define which components can be added to tabs and customize the styles.

>[!NOTE]
>
>ネストされたタブコンポーネント（タブ内のタブ）はサポートされています。
>
>Simple (non-nested) tab components can be located/selected using the [content tree](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html), however nested tabs can not be.

## Version and Compatibility {#version-and-compatibility}

現在のバージョンのタブコンポーネントはv1であり、2018年10月のコアコンポーネントのリリース2.2.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Tabs Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/tabs.html).

### Technical Details {#technical-details}

The latest technical documentation about the Tabs Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がタブを作成、名前変更および並べ替え、アクティブなタブを定義することができます。

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-11at153557.png)

**「追加」** ボタンを使用してコンポーネントセレクターを開き、タブとして追加するコンポーネントを選択します。追加すると、エントリがリストに追加され、次の列が含まれます。

* **アイコン** -リストで簡単に識別できるようにする、タブのコンポーネントタイプのアイコン。マウスを移動すると、コンポーネント名がツールチップとして表示されます。
* **説明** -タブのテキストとして使用される説明。タブに対して選択されたコンポーネントの名前にデフォルトで設定されます。
* **削除** -タブコンポーネントからタブをタップまたはクリックして削除します。
* **整列** -タップまたはクリックしてドラッグし、タブの順序を並べ替えます。

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-10-19at140646.png)

**「プロパティ** 」タブでは、コンテンツ作成者はページの読み込み時にアクティブなタブを定義できます。**「デフォルト」** オプションでは、最初のタブが選択されます。

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different panel for editing as well as to easily rearrange the order of the tabs.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured tabs are displayed as a drop-down.

* リストは、割り当てられたタブの割り当て順に並べ替えられ、番号付けに反映されます。
* タブのコンポーネントタイプが最初に表示され、その後に薄いフォントでタブの説明が表示されます。

![](assets/screenshot_2018-10-11at165154.png)

* ドロップダウンのエントリをタップまたはクリックして、エディターのビューをそのタブに切り替えます。
* タブは、ドラッグハンドルを使用して配置し直すことができます。

>[!NOTE]
>
>**編集** モードでは、作成者がタブを選択できません。Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the tabs as a reader of the published content would.

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者がタブコンポーネントにアイテムとして追加できるコンポーネントを定義したり、コンテンツ作成者が使用できるカスタムスタイルを定義したりできます。

### Allowed Components Tab {#allowed-components-tab}

**「許可されているコンポーネント** 」タブを使用して、コンテンツ作成者がタブコンポーネントにアイテムとして追加できるコンポーネントを定義します。

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Tabs Component supports the AEM [Style System](authoring.md#component-styling).