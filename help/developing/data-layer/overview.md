---
title: コアコンポーネントでの Adobe Client Data Layer の使用
description: コアコンポーネントでの Adobe Client Data Layer の使用
translation-type: ht
source-git-commit: 57116fa8f8a71259400881609775af4047cd2225
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---


# コアコンポーネントでの Adobe Client Data Layer の使用{#data-layer-core-components}

Adobe Client Data Layer の目標は、あらゆるスクリプトであらゆる種類のデータを表示およびアクセスできる標準化された方法を提供し、Web サイトを測定する際の手間を軽減することです。

Adobe Client Data Layer はプラットフォームに依存しませんが、AEM で使用するためにコアコンポーネントに完全に統合されています。

Adobe Client Data Layer のコードは、コアコンポーネントと同様、開発者向けドキュメントと共に GitHub で入手できます。このドキュメントでは、コアコンポーネントがデータレイヤーとやり取りする方法の概要について説明しますが、技術的な詳細は GitHub ドキュメントに従います。

>[!TIP]
>
>Adobe Client Data Layer の詳細については、[GitHub リポジトリのリソースを参照してください。](https://github.com/adobe/adobe-client-data-layer)
>
>Adobe Client Data Layer とコアコンポーネントの統合に関する技術的な詳細については、コアコンポーネントリポジトリの [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) ファイルを参照してください。


## インストールとアクティベーション {#installation-activation}

コアコンポーネントリリース 2.9.0 以降、データレイヤーは clientlib としてコアコンポーネントと共に配布されています。インストールは必要ありません。

ただし、データレイヤーはデフォルトではアクティブになっていません。データレイヤーをアクティブにするには

1. `/conf` ノードの配下に次の構造を作成します。
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * ノードタイプ：`nt:unstructured`
1. `enabled` という名前のブール型プロパティを追加し、`true` に設定します。
1. `sling:configRef` プロパティを `/content` 配下のサイトの `jcr:content` ノード（例：`/content/<mySite>/jcr:content`）に追加し、`/conf/<mySite>` に設定します。

有効にすると、エディター外のサイトのページを読み込んで、アクティベーションを検証することができます。ページを調べると、Adobe Client Data Layer が読み込まれていることがわかります。

## コアコンポーネントのデータスキーマ {#data-schemas}

コアコンポーネントがデータレイヤーで使用するスキーマのリストを以下に示します。

### コンポーネント／コンテナ項目スキーマ {#item}

コンポーネント／コンテナ項目スキーマは、次のコンポーネントで使用されます。

* [パンくず](/help/components/breadcrumb.md)
* [ボタン](/help/components/button.md)
* [言語ナビゲーション](/help/components/language-navigation.md)
* [リスト](/help/components/list.md)
* [ナビゲーション](/help/components/navigation.md)
* [ティーザー](/help/components/teaser.md)
* [テキスト](/help/components/text.md)
* [タイトル](/help/components/title.md)

コンポーネント／コンテナ項目スキーマは、次のように定義されます。

```
id: {                   // component ID
    @type               // resource type
    repo:modifyDate     // last modified date
    dc:title            // title
    dc:description      // description
    xdm:text            // text
    xdm:linkURL         // link URL
    parentId            // parent component ID
}
```


### ページスキーマ {#page}

ページスキーマは、次のコンポーネントで使用されます。

* [ページ](/help/components/page.md)

ページスキーマは次のように定義されます。

```
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    xdm:tags            // page tags
    repo:path           // page path
    xdm:template        // page template
    xdm:language        // page language
}
```

### コンテナスキーマ {#container}

コンテナスキーマは、次のコンポーネントで使用されます。

* [アコーディオン](/help/components/accordion.md)
* [タブ](/help/components/tabs.md)
* [カルーセル](/help/components/carousel.md)

コンテナスキーマは次のように定義されます。

```
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    shownItems          // array of the displayed item IDs
}
```

### 画像スキーマ {#image}

画像スキーマは、次のコンポーネントで使用されます。

* [画像](/help/components/image.md)

画像スキーマは次のように定義します。

```
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    image               // asset detail (see below section)
}
```

### アセットスキーマ {#asset}

アセットスキーマは、[画像コンポーネント](/help/components/image.md)内で使用されます。

アセットスキーマは次のように定義します。

```
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

