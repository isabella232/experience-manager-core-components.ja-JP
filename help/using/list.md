---
title: リストコンポーネント
seo-title: リストコンポーネント
description: 'null'
seo-description: コアコンポーネントリストコンポーネントを使用すると、静的リストと静的リストを簡単に作成できます。
uuid: 50a572e8- b444-4f7d-82bc-5a93ebb4be95
contentOwner: User
content-type: リファレンス
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: 89053323-6221-46ed-896a-31a42c55282e
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


# リストコンポーネント{#list-component}

コアコンポーネントリストコンポーネントを使用すると、静的リストと静的リストを簡単に作成できます。

## 使用 {#usage}

リストコンポーネントは、子ページの動的リストや、恣意的に定義された項目の静的リストなどの作成に使用できます。The type of lists available and formatting options can be defined by the template author in the [design dialog](#design-dialog). The content editor can select from available list types and how to format the list elements in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

List Componentの現在のバージョンはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](list-v1.md) | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the List Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/list.html).

### Technical Details {#technical-details}

The latest technical documentation about the List Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がリストとリスト項目を設定できます。

### List Settings Tab {#list-settings-tab}

リストは様々な方法で作成できます。

* [子ページ](#child-pages)
* [固定リスト](#fixed-list)
* [検索](#search-options)
* [タグ](#tags)

Regardless of how the list is built, there are [Sort Options](#sort-options) that can always be configured.

![](assets/chlimage_1-38.png)

コンテンツ作成者がリストの作成をどのように選択するかによって、追加の設定オプションが変更されます。

#### 子ページ {#child-pages}

このリストは、現在のページまたは別のページの子ページから作成できます。

![](assets/chlimage_1-39.png)

* **親ページ**
   * 子ページがリストを作成する必要があるページ
   * 現在のページを使用するには空白のままにします

* **Child- Depth** 階層内の下位レベルのレベルを使用する

#### 固定リスト {#fixed-list}

リストは、項目の固定リストを使用して作成できます。

![](assets/chlimage_1-40.png)

Tap or click the **Add** button to inset a new item to the list.

* Enter text for the item in the list or use the **Selection Dialog** to choose an item from AEM.
* ドラッグハンドルを使用して、リスト内の項目を再配置します。
* ごみ箱アイコンを使用してリスト内の項目を削除します。

#### 検索 {#search-options}

リストは、AEMコンテンツの検索結果を使用して作成できます。

![](assets/chlimage_1-41.png)

* **検索クエリ**
* **検索の実行** 場所の検索
   * **選択ダイアログ** を使用したAEMの場所の選択
   * 空白の場合は現在のページを使用

#### タグ {#tags}

リストは特定の場所の特定のタグに一致するページを使用して作成できます。

![](assets/chlimage_1-42.png)

* **タグマッチングが開始する親ページ**
   * **選択ダイアログ** を使用したAEMの場所の選択
   * 空白の場合は現在のページを使用
* **タグ** どのタグを照合するか
   * **参照** ダイアログを使用したタグの選択
* **一致** の種類を定義して、リストに含めるページを指定する
   * **いずれかのタグ**
   * **すべてのタグ**

#### Sort Options {#sort-options}

リストの作成方法にかかわらず、いつでも定義できる並べ替えオプションがあります。

![](assets/chlimage_1-43.png)

* **要素の順序付けによる** 順序
   * **タイトル**
   * **最終変更日**
* **並べ替え順序**
   * **昇順**
   * **降順**
* **最大項目** 数リストに表示される項目の最大数。
   * すべての項目を返すには、空のままにします。

### Item Settings Tab {#item-settings-tab}

「アイテムの設定」タブを使用すると、リスト要素の書式設定を設定できます。

![](assets/chlimage_1-44.png)

* **項目** リンク項目を対応するページにリンクする
* **リンク項目の説明** を表示の説明
* **リンク項目の日付** 表示日を表示

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者がコンテンツ作成者に許可するリストの種類と使用可能な項目設定を定義できます。

### リスト設定 {#list-settings}

On the **List Settings** tab, the date format can be defined as well as what type of lists should be available in the component to the content authors.

![](assets/chlimage_1-45.png)

* **最終変更日の表示に使用する日付形式** 形式
* **子** を無効にするコンポーネント内の子リストの種類を無効にする
* **スタティック** リストの種類を無効にするには、コンポーネントの静的リストの種類を無効にする
* **検索** を無効にするコンポーネント内の検索リストのタイプを無効にする
* **タグ** 無効化タグのリストタイプをコンポーネント内で無効にします

### 項目設定 {#item-settings}

On the **Item Settings** tab, the formatting options for the individual list elements that should be available in the component for the content authors can be defined.

![](assets/chlimage_1-46.png)

* **編集ダイアログで「項目** をリンク」オプションを [有効にする](#edit-dialog)
* **編集ダイアログで「** 説明を表示を有効にする」オプション [を表示](#edit-dialog)
* **編集ダイアログで日付** を有効にする [オプションを表示](#edit-dialog)

### Styles Tab {#styles-tab}

The Image Component supports the AEM [Style System](authoring.md#component-styling).