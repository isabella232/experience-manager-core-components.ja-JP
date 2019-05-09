---
title: リストコンポーネント
seo-title: リストコンポーネント
description: 'null'
seo-description: コアコンポーネントリストコンポーネントを使用すると、静的リストと静的リストを簡単に作成できます。
uuid: 50a572e8- b444-4f7d-82bc-5a93ebb4be95
contentOwner: ユーザーは、
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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# リストコンポーネント{#list-component}

コアコンポーネントリストコンポーネントを使用すると、静的リストと静的リストを簡単に作成できます。

## 使用方法 {#usage}

リストコンポーネントは、子ページの動的リストや、恣意的に定義された項目の静的リストなどの作成に使用できます。使用可能なリストの種類とフォーマットオプションは [、デザインダイアログのテンプレート作成者によって定義](#design-dialog)できます。コンテンツエディターでは、利用可能なリストタイプから選択したり、 [編集ダイアログでリスト要素の書式を設定](#edit-dialog)したりできます。

## バージョンと互換性 {#version-and-compatibility}

List Componentの現在のバージョンはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](list-v1.md) | 互換性 | 互換性 | 互換性 |

コアコンポーネントバージョンとリリースについて詳しくは、ドキュメント [コアコンポーネントバージョン](versions.md)を参照してください。

## サンプルコンポーネントの出力 {#sample-component-output}

以下は、We. Retailから [取得されたサンプル](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)です。

### スクリーンショット {#screenshot}

![](assets/screen_shot_2018-01-12at105924.png)

### コンポーネントライブラリ

List Componentを体験したり、HTMLやJSON出力の設定オプションの例を確認するには [、コンポーネントライブラリを参照](http://opensource.adobe.com/aem-core-wcm-components/library/list.html)してください。

### 技術的詳細 {#technical-details}

リストコンポーネント [に関する最新の技術ドキュメントは、GitHubで確認](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list)できます。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## ダイアログを編集 {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がリストとリスト項目を設定できます。

### 「リスト設定」タブ {#list-settings-tab}

リストは様々な方法で作成できます。

* [子ページ](#child-pages)
* [固定リスト](#fixed-list)
* [検索](#search-options)
* [タグ](#tags)

リストのビルド方法に関係なく、常に設定できる [並べ替えオプション](#sort-options) があります。

![](assets/chlimage_1-38.png)

コンテンツ作成者がリストの作成をどのように選択するかによって、追加の設定オプションが変更されます。

#### 子ページ {#child-pages}

このリストは、現在のページまたは別のページの子ページから作成できます。

![](assets/chlimage_1-39.png)

* **親ページ**
   * 子ページがリストを作成する必要があるページ
   * 現在のページを使用するには空白のままにします

* **Child- Depth**階層内の下位レベルのレベルを使用する

#### 固定リスト {#fixed-list}

リストは、項目の固定リストを使用して作成できます。

![](assets/chlimage_1-40.png)

「 **追加」** ボタンをタップまたはクリックして、新しい項目をリストに挿入します。

* リスト内のアイテムのテキストを入力するか **、選択ダイアログ** を使用してAEMからアイテムを選択します。
* ドラッグハンドルを使用して、リスト内の項目を再配置します。
* ごみ箱アイコンを使用してリスト内の項目を削除します。

#### 検索 {#search-options}

リストは、AEMコンテンツの検索結果を使用して作成できます。

![](assets/chlimage_1-41.png)

* **Search query**
The string for which a full-text search will be run to generate the list elements
* **検索の実行**場所の検索
   * **選択ダイアログ** を使用したAEMの場所の選択
   * 空白の場合は現在のページを使用

#### タグ {#tags}

リストは特定の場所の特定のタグに一致するページを使用して作成できます。

![](assets/chlimage_1-42.png)

* **Parent page**
Where the tag matching should start
   * **選択ダイアログ** を使用したAEMの場所の選択
   * 空白の場合は現在のページを使用
* **タグ**どのタグを照合するか
   * **参照** ダイアログを使用したタグの選択
* **一致**の種類を定義して、リストに含めるページを指定する
   * **いずれかのタグ**
   * **すべてのタグ**

#### 並べ替えオプション {#sort-options}

リストの作成方法にかかわらず、いつでも定義できる並べ替えオプションがあります。

![](assets/chlimage_1-43.png)

* **要素の順序付けによる**順序
   * **タイトル**
   * **最終変更日**
* **Sort Order**
The order in which the items should be ordered
   * **昇順**
   * **降順**
* **最大項目**数リストに表示される項目の最大数。
   * すべての項目を返すには、空のままにします。

### 「アイテム設定」タブ {#item-settings-tab}

「アイテムの設定」タブを使用すると、リスト要素の書式設定を設定できます。

![](assets/chlimage_1-44.png)

* **項目**リンク項目を対応するページにリンクする
* **リンク項目の説明**を表示の説明
* **リンク項目の日付**表示日を表示

## デザインダイアログ {#design-dialog}

デザインダイアログでは、テンプレート作成者がコンテンツ作成者に許可するリストの種類と使用可能な項目設定を定義できます。

### リスト設定 {#list-settings}

「リスト設定 **」** タブでは、日付形式を定義したり、コンテンツ作成者に対してコンポーネントで使用できるリストの種類を定義したりできます。

![](assets/chlimage_1-45.png)

* **最終変更日の表示に使用する日付形式**形式
* **子**を無効にするコンポーネント内の子リストの種類を無効にする
* **スタティック**リストの種類を無効にするには、コンポーネントの静的リストの種類を無効にする
* **検索**を無効にするコンポーネント内の検索リストのタイプを無効にする
* **タグ**無効化タグのリストタイプをコンポーネント内で無効にします

### 項目設定 {#item-settings}

「 **アイテムの設定** 」タブでは、コンテンツ作成者用にコンポーネントで使用できる個々のリスト要素の書式設定オプションを定義できます。

![](assets/chlimage_1-46.png)

* **編集ダイアログで「項目**をリンク」オプションを [有効にする](#edit-dialog)
* **編集ダイアログで「**説明を表示を有効にする」オプション [を表示](#edit-dialog)
* **編集ダイアログで日付**を有効にする [オプションを表示](#edit-dialog)

### 「スタイル」タブ {#styles-tab}

Image Componentでは、AEM [スタイルシステム](authoring.md#component-styling)がサポートされています。