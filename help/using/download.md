---
title: コンポーネントのダウンロード
seo-title: コンポーネントのダウンロード
description: 'null'
seo-description: コアコンポーネントダウンロードコンポーネントを使用すると、ページ上でダウンロードオプションを作成できます。
uuid: ec807de9- f76c-4850-9ece- c3e439a1d626
contentOwner: User
content-type: reference
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: f093f58e-9755-4a4f-803a- ab93a50e6870
translation-type: tm+mt
source-git-commit: 88bc68b60e5de247fe800ac041ffefdf9238cce1

---


# Download Component{#download-component}

コアコンポーネントダウンロードコンポーネントを使用すると、ページ上でダウンロードオプションを作成できます。

## 使用 {#usage}

コアコンポーネントダウンロードコンポーネントを使用すると、ダウンロードオプションと関連アセットをページに含めることができます。

* The download option&#39;s properties can be selected in the [configure dialog](#configure-dialog).
* Defaults for the download component can be defined in the [design dialog](#design-dialog).

## Version and Compatibility {#version-and-compatibility}

ダウンロードコンポーネントの現在のバージョンは、2019年6月のコアコンポーネントのリリース2.5.0で導入されたv1です。このドキュメントで説明します。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Download Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/download.html).

## Technical Details {#technical-details}

The latest technical documentation about the Download Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

設定ダイアログでは、コンテンツ作成者がダウンロードアイテムを定義し、そのページへの訪問者の行動と表示方法を定義できます。

![](assets/screen-shot-2019-06-17-09.49.14.png)

### Asset Tab {#asset-tab}

The selection of a download asset is very similar to the functionality of the [Image Component](image.md) and likewise leverages AEM&#39;s DAM.

* **アセットをダウンロード**
   * [アセットブラウザからアセットをドロップ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) するか、 **または参照** オプションをタップしてローカルファイルシステムからアップロードします。
   * Tap or click **Clear** to de-select the currently selected image.
   * **アセット** エディターでアセットのレンディションを [作成するには、「編集」を](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) タップまたはクリックします。

### Properties Tab {#properties-tab}

![](assets/screen-shot-2019-06-17-09.49.51.png)

* **タイトル** -ダウンロードアイテムのヘッドラインとして表示されます
   * **DAMアセットからタイトルを取得** -選択すると、タイトルにDAMアセットのタイトルが自動的に入力されます。
* **説明** -ダウンロードアイテムの説明的なサブヘッドラインとして表示
   * **DAMアセットから説明を取得** -選択すると、説明にDAMアセットの説明が自動的に入力されます。
* **アクションテキスト** -ダウンロードアイテムのアクションテキストとして表示されます
   * このフィールドは、ファイルシステムからアセットをアップロードするときに必要です。
   * **インライン表示** -指定した **アクションテキスト** を選択するとインライン表示されます。

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者が、コンポーネントのダウンロードを使用するコンテンツ作成者に提供されるオプションを定義できます。

### Properties Tab {#properties-tab-design}

![](assets/screen-shot-2019-06-17-10.04.31.png)

* **デフォルトのアクションテキスト** -作成者が「コンポーネントのダウンロード」をページに追加したときに提供される **デフォルトのアクションテキスト** を定義します。
* **ファイルシステムからのアップロードを許可** -コンテンツ作成者が、自分のローカルファイルシステムからアセットをダウンロードアセットとしてアップロードできるようにします。
   * デフォルト値は選択されていません。
* **タイトルタイプ** -コンポーネントのダウンロードタイトルに使用するHTML要素。
   * 値が選択されていない場合、デフォルト値はH3です。
* **表示ファイルサイズ** -選択すると、アセットのファイルサイズがダウンロードコンポーネントに表示されます。
   * デフォルト値が選択されます。
* **表示ファイル形式** -選択すると、アセットのファイル形式がダウンロードコンポーネントに表示されます。
   * デフォルト値が選択されます。
* **表示ファイル名** -選択すると、アセットのファイル名がダウンロードコンポーネントに表示されます。
   * デフォルト値が選択されます。

### Styles Tab {#styles-tab}

The Image Component supports the AEM [Style System](authoring.md#component-styling).
