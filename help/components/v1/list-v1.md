---
title: リストコンポーネント（v1）
description: コアコンポーネントのリストコンポーネントを使用すれば、静的リストや静的リストを簡単に作成できます。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 100%

---

# リストコンポーネント（v1）{#list-component-v}

コアコンポーネントのリストコンポーネントを使用すれば、静的リストや静的リストを簡単に作成できます。

## 使用方法 {#usage}

リストコンポーネントを使用すれば、子ページの動的リストや、自由に定義した項目の静的リストなどを作成できます。

[デザインダイアログ](#design-dialog)では、利用可能なリストの種類や書式設定のオプションをテンプレート作成者が定義できます。[編集ダイアログ](#edit-dialog)では、利用可能なリストタイプやリスト要素の書式設定方法の中から、コンテンツエディターが選択できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 のコアコンポーネントのリリース 1.0.0 で最初に導入された、リストコンポーネントの v1 について説明します。

次の表に、リストコンポーネントの v1 の互換性の一覧を示します。

| AEM のバージョン | リストコンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、リストコンポーネントの v1 について説明します。
>
>リストコンポーネントの現在のバージョンについて詳しくは、[リストコンポーネント](/help/components/list.md)ドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retail](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html) から取得したサンプルです。

### スクリーンショット {#screenshot}

![](/help/assets/chlimage_1-47.png)

### HTML {#html}

```
<div class="cmp cmp-list aem-GridColumn aem-GridColumn--default--12">

<ul>
    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/arctic-surfing-in-lofoten.html">
            <span class="cmp-list--item-title">Arctic Surfing In Lofoten</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/summit-success-in-the-himalayas.html">
            <span class="cmp-list--item-title">Summit Success in the Himalayas</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-on-kalymnos-island--greece.html">
            <span class="cmp-list--item-title">Climbing on Kalymnos Island, Greece</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/running-at-the-great-wall-marathon.html">
            <span class="cmp-list--item-title">Running at the Great Wall Marathon</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/skiing-deep-powder-in-siberia.html">
            <span class="cmp-list--item-title">Skiing deep powder in Siberia</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-in-the-massif-du-mont-blanc.html">
            <span class="cmp-list--item-title">Climbing in the Massif du Mont Blanc</span>
            
        </a>
        
    </article>
</li>
</ul>

</div>
```

### JSON {#json}

```
"articles_list": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/articleslist",
              "tagsMatch": "any",
              "displayAs": "teaser",
              "feedEnabled": "true",
              "listFrom": "children",
              "limit": "0",
              "orderBy": "cq:lastModified",
              "pageMax": "0"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](/help/versions.md)を参照してください。

## 編集ダイアログ {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がリストとリスト要素を設定できます。

### リスト設定 {#list-settings}

リストは様々な方法で作成できます。

* [子ページ](#child-pages)
* [固定リスト](#fixed-list)
* [検索](#search-list)
* [タグ](#tags)

リストの作成方法に関係なく、常に設定できる[並べ替えオプション](#sort-options)があります。

![](/help/assets/chlimage_1-38.png)

コンテンツ作成者が選択したリストの作成方法に応じて、追加の設定オプションが変わります。

#### 子ページ {#child-pages}

リストは、現在のページまたは別のページの子ページから作成できます。

![](/help/assets/chlimage_1-39.png)

* **親ページ**
   * リストを作成する子ページの親ページ
   * 現在のページを使用する場合は空のままにします
* **子の深さ** - 階層内の何個下のレベルまで使用するか

#### 固定リスト {#fixed-list}

リストは、項目の固定リストを使用して作成できます。

![](/help/assets/chlimage_1-40.png)

「**追加**」ボタンをタップまたはクリックして、新しい項目をリストに挿入します。

* リスト内の項目のテキストを入力するか、**選択ダイアログ**&#x200B;を使用して AEM から項目を選択します。
* リスト内の項目を再配置するには、ドラッグハンドルを使用します。
* リスト内の項目を削除するには、ごみ箱アイコンを使用します。

#### 検索 {#search-list}

リストは、AEM コンテンツの検索結果を使用して作成できます。

![](/help/assets/chlimage_1-41.png)

* **検索クエリー** - フルテキスト検索を実行してリスト要素を生成する際の対象となる文字列
* **検索範囲** - 検索の実行場所
   * **選択ダイアログ**&#x200B;を使用して AEM 内の場所を選択します。
   * 空のままにした場合は現在のページが使用されます

#### タグ {#tags}

リストは、特定の場所の下で特定のタグに一致するページを使用して作成できます。

![](/help/assets/chlimage_1-42.png)

* **親ページ** - タグマッチングの開始場所
   * **選択ダイアログ**&#x200B;を使用して AEM 内の場所を選択します。
   * 空のままにした場合は現在のページが使用されます
* **タグ** - マッチングの対象となるタグ
   * **参照**&#x200B;ダイアログを使用してタグを選択します
* **一致** - リストに含まれるページの条件となる一致の種類を定義します
   * **いずれかのタグ**
   * **すべてのタグ**

#### 並べ替えオプション {#sort-options}

リストの作成方法にかかわらず、いつでも定義できる並べ替えオプションがあります。

![](/help/assets/chlimage_1-43.png)

* **並べ替え順** - 要素の並べ替え方法
   * **タイトル**
   * **最終変更日**
* **並べ替え順序** - 項目の並べ替え順序
   * **昇順**
   * **降順**
* **最大項目数** - リストに表示される項目の最大数。
   * すべての項目を返すには、空のままにします。

### 項目設定 {#item-settings}

「**項目設定**」タブを使用すれば、リスト要素の書式設定を設定できます。

![](/help/assets/chlimage_1-44.png)

* **項目をリンク**
項目を対応するページにリンクします
* **説明を表示**
リンク項目の説明を表示します
* **日付を表示**
リンク項目の変更日を表示します

## デザインダイアログ {#design-dialog}

デザインダイアログでは、テンプレート作成者が、コンテンツ作成者に許可するリストの種類や、使用可能な項目設定を定義できます。

### リスト設定 {#list-settings-1}

「**リスト設定**」タブでは、日付の形式を定義したり、コンポーネントでコンテンツ作成者が使用できるリストの種類を定義したりできます。

![](/help/assets/chlimage_1-45.png)

* **日付の形式** - 最終変更日の表示に使用する形式
* **子を無効にする** - コンポーネントで子リストタイプを無効にします
* **静的を無効にする** - コンポーネントで静的リストタイプを無効にします
* **検索を無効にする** - コンポーネントで検索リストタイプを無効にします
* **タグを無効にする** - コンポーネントでタグリストタイプを無効にします

### 項目設定 {#item-settings-1}

「**項目設定**」タブでは、コンテンツ作成者がコンポーネント内で使用できる個々のリスト要素の書式設定オプションを定義することができます。

![](/help/assets/chlimage_1-46.png)

* **項目をリンク** - [編集ダイアログ](#edit-dialog)で「項目をリンク」オプションを有効にします
* **説明を表示** - [編集ダイアログ](#edit-dialog)で「説明を表示」オプションを有効にします
* **日付を表示** - [編集ダイアログ](#edit-dialog)で「日付を表示」オプションを有効にします

## 技術的詳細 {#technical-details}

リストコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list) を参照してください。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。
