---
title: Adobeクライアントデータレイヤーとコアコンポーネントの使用
description: Adobeクライアントデータレイヤーとコアコンポーネントの使用
translation-type: tm+mt
source-git-commit: 539a4250c954ac830731a9ecf010e129b2cf9c3a
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---


# Adobeクライアントデータレイヤーとコアコンポーネントの使用 {#data-layer-core-components}

Adobeクライアントデータレイヤーの目標は、スクリプトの任意の種類のデータを公開し、アクセスするための標準化された方法を提供することで、Webサイトの計測の手間を軽減することです。

Adobe Client Data Layerはプラットフォームにとらわれませんが、AEMで使用するためにコアコンポーネントに完全に統合されています。

コアコンポーネントと同様、Adobe Client Data Layerのコードは、開発者向けドキュメントと共にGitHubで入手できます。 このドキュメントでは、コアコンポーネントがデータレイヤーとやり取りする方法の概要を説明しますが、技術的な詳細はGitHubドキュメントの提供を延期します。

>[!TIP]
>
>Adobe Client Data Layerの詳細については、GitHubリポジトリのリソースを [参照してください。](https://github.com/adobe/adobe-client-data-layer)
>
>Adobe Client Data Layerとコアコンポーネントの統合に関する技術的な詳細については、コアコンポーネントリポジトリの [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) ファイルを参照してください。


## インストールとアクティベーション {#installation-activation}

コアコンポーネントリリース2.9.0以降、データレイヤーはclientlibとしてコアコンポーネントと共に配布されます。 インストールは必要ありません。

ただし、データレイヤーはデフォルトではアクティブになっていません。 データレイヤーをアクティブにするには

1. ノードの下に次の構造を作成し `/conf` ます。
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
1. を呼び出し、に追加設定したブール型プロパティ `enabled``true`。
1. 下追加のサイトの `sling:configRef` ノードに対するプロパティ `jcr:content``/content` ( `/content/<mySite>/jcr:content`)をクリックし、に設定し `/conf/<mySite>`ます。

有効にすると、アクティベーションの外部にサイトのページを読み込んで、エディターを検証できます。 ページを調べると、Adobeクライアントデータレイヤーが読み込まれていることがわかります。

## コアコンポーネントのデータスキーマ {#data-schemas}

以下は、コアコンポーネントがデータレイヤーで使用するスキーマのリストです。

### コンポーネント/コンテナ項目スキーマ {#item}

コンポーネント/コンテナ項目スキーマは、次のコンポーネントで使用されます。

* [パンくず](/help/components/breadcrumb.md)
* [ボタン](/help/components/button.md)
* [言語ナビゲーション](/help/components/language-navigation.md)
* [リスト](/help/components/list.md)
* [ナビゲーション](/help/components/navigation.md)
* [ティーザー](/help/components/teaser.md)
* [テキスト](/help/components/text.md)
* [タイトル](/help/components/title.md)

コンポーネント/コンテナ項目スキーマは、次のように定義します。

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

イメージスキーマは次のように定義します。

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

アセットスキーマは、 [画像コンポーネント内で使用されます。](/help/components/image.md)

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

