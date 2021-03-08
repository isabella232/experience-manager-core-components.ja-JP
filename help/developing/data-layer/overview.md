---
title: コアコンポーネントでの Adobe Client Data Layer の使用
description: コアコンポーネントでの Adobe Client Data Layer の使用
translation-type: ht
source-git-commit: 57582c5c938e0f345b27785bd6fd6d5ed5454bd0
workflow-type: ht
source-wordcount: '974'
ht-degree: 100%

---


# コアコンポーネントでの Adobe Client Data Layer の使用 {#data-layer-core-components}

Adobe Client Data Layer の目標は、あらゆるスクリプトであらゆる種類のデータを表示およびアクセスできる標準化された方法を提供し、Web サイトを測定する際の手間を軽減することです。

Adobe Client Data Layer はプラットフォームに依存しませんが、AEM で使用するためにコアコンポーネントに完全に統合されています。

Adobe Client Data Layer のコードは、コアコンポーネントと同様、開発者向けドキュメントと共に GitHub で入手できます。このドキュメントでは、コアコンポーネントがデータレイヤーとやり取りする方法の概要について説明しますが、技術的な詳細は GitHub ドキュメントに従います。

>[!TIP]
>
>Adobe Client Data Layer の詳細については、[GitHub リポジトリーのリソースを参照してください。](https://github.com/adobe/adobe-client-data-layer)
>
>Adobe Client Data Layer とコアコンポーネントの統合に関する技術的な詳細については、コアコンポーネントリポジトリーの [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) ファイルを参照してください。

## インストールとアクティベーション {#installation-activation}

コアコンポーネントリリース 2.9.0 の時点では、データレイヤーはコアコンポーネントとともに AEM クライアントライブラリとして配布され、インストールの必要はありません。[AEM Project Archetype v. 24 以降](/help/developing/archetype/overview.md)で生成されるすべてのプロジェクトには、アクティブ化されたデータレイヤーがデフォルトで含まれます。

データレイヤーを手動でアクティブにするには、[コンテキストに応じた設定](/help/developing/context-aware-configs.md)を作成する必要があります。

1. `/conf/<mySite>` フォルダーの下に次の構造を作成します。`<mySite>` はサイトのプロジェクトの名前です。
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 各ノードには、`nt:unstructured` に対する `jcr:primaryType` セットがあります。
1. `enabled` という名前のブール型プロパティを追加し、`true` に設定します。

   ![WKND リファレンスサイトの DataLayerConfig の場所](/help/assets/datalayer-contextaware-sling-config.png)

   *WKND リファレンスサイトの DataLayerConfig の場所*

1. `sling:configRef` プロパティを `/content` 配下のサイトの `jcr:content` ノード（例：`/content/<mySite>/jcr:content`）に追加し、以前の手順の `/conf/<mySite>` に設定します。

1. 有効にすると、エディター外のサイトのページを読み込んで、アクティベーションを検証できます。例えば、エディターで「**公開されているとおりに表示**」オプションを使用します。ページソースを検査し、`<body>` タグには属性 `data-cmp-data-layer-enabled` を含める必要があります。

   ```html
   <body class="page basicpage" id="page-id" data-cmp-data-layer-enabled>
       <script>
         window.adobeDataLayer = window.adobeDataLayer || [];
         adobeDataLayer.push({
             page: JSON.parse("{\x22page\u002D6c5d4b9fdd\x22:{\x22xdm:language\x22:\x22en\x22,\x22repo:path\x22:\x22\/content\/wknd\/language\u002Dmasters\/en.html\x22,\x22xdm:tags\x22:[],\x22xdm:template\x22:\x22\/conf\/wknd\/settings\/wcm\/templates\/landing\u002Dpage\u002Dtemplate\x22,\x22@type\x22:\x22wknd\/components\/page\x22,\x22dc:description\x22:\x22WKND is a collective of outdoors, music, crafts, adventure sports, and travel enthusiasts that want to share our experiences, connections, and expertise with the world.\x22,\x22dc:title\x22:\x22WKND Adventures and Travel\x22,\x22repo:modifyDate\x22:\x222020\u002D09\u002D29T07:50:13Z\x22}}"),
             event:'cmp:show',
             eventInfo: {
                 path: 'page.page\u002D6c5d4b9fdd'
             }
         });
       </script>
   ```

1. また、ブラウザーの開発者ツールを開き、コンソールで `adobeDataLayer` JavaScript オブジェクトを使用できるようにします。次のコマンドを入力して、現在のページのデータレイヤーの状態を取得します。

   ```javascript
   window.adobeDataLayer.getState();
   ```

## サポートされているコンポーネント {#supported-components}

データレイヤーをサポートしているコンポーネントは次のとおりです。

* [アコーディオン](/help/components/accordion.md)
* [パンくず](/help/components/breadcrumb.md)
* [ボタン](/help/components/button.md)
* [カルーセル](/help/components/carousel.md)
* [コンテンツフラグメント](/help/components/content-fragment-component.md)
* [画像](/help/components/image.md)
* [言語ナビゲーション](/help/components/language-navigation.md)
* [リスト](/help/components/list.md)
* [ナビゲーション](/help/components/navigation.md)
* [ページ](/help/components/page.md)
* [プログレスバー](/help/components/progress-bar.md)
* [タブ](/help/components/tabs.md)
* [ティーザー](/help/components/teaser.md)
* [テキスト](/help/components/text.md)
* [タイトル](/help/components/title.md)

[コンポーネントでトリガーされるイベント](#events-components)も参照してください。

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

```javascript
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

次の[イベント](#events)は、コンポーネント／コンテナ項目スキーマに関連します。

* `cmp:click`

### ページスキーマ {#page}

ページスキーマは、次のコンポーネントで使用されます。

* [ページ](/help/components/page.md)

ページスキーマは次のように定義されます。

```javascript
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

ページの読み込み時に `cmp:show` イベントがトリガーされます。このイベントは、開始 `<body>` タグのすぐ下にあるインライン JavaScript からディスパッチされるので、データレイヤーイベントキューで最も早いイベントになります。

### コンテナスキーマ {#container}

コンテナスキーマは、次のコンポーネントで使用されます。

* [アコーディオン](/help/components/accordion.md)
* [タブ](/help/components/tabs.md)
* [カルーセル](/help/components/carousel.md)

コンテナスキーマは次のように定義されます。

```javascript
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

次の[イベント](#events)は、コンテナスキーマに関連します。

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 画像スキーマ {#image}

画像スキーマは、次のコンポーネントで使用されます。

* [画像](/help/components/image.md)

画像スキーマは次のように定義します。

```javascript
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

次の[イベント](#events)は、画像スキーマに関連します。

* `cmp:click`

### アセットスキーマ {#asset}

アセットスキーマは、[画像コンポーネント](/help/components/image.md)内で使用されます。

アセットスキーマは次のように定義します。

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

次の[イベント](#events)は、アセットスキーマに関連します。

* `cmp:click`

### コンテンツフラグメントスキーマ {#content-fragment}

コンテンツフラグメントスキーマは、[コンテンツフラグメントコンポーネント](/help/components/content-fragment-component.md)で使用されます。

コンテンツフラグメントスキーマは次のように定義されています。

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    elements            // array of the Content Fragment elements
}
```

コンテンツフラグメント要素に使用されるスキーマは次のとおりです。

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## コアコンポーネントのイベント {#events}

コアコンポーネントがデータレイヤーを介してトリガーするイベントは多数あります。データレイヤーを操作する際のベストプラクティスは、[イベントリスナーを登録](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener)し&#x200B;*、*&#x200B;イベントタイプや、イベントをトリガーしたコンポーネントに基づいてアクションを実行することです。これにより、非同期スクリプトで競合が発生する可能性を回避できます。

AEM コアコンポーネントが提供する初期設定のイベントを以下に示します。

* **`cmp:click`** - クリック可能な要素（`data-cmp-clickable` 属性を持つ要素）をクリックすると、データレイヤーによって `cmp:click` イベントがトリガーされます。
* **`cmp:show`** および **`cmp:hide`** - アコーディオン（展開/折りたたみ）、カルーセル（次へ／前へのボタン）、タブ（タブ選択）の各コンポーネントを操作すると、データレイヤーがそれぞれ `cmp:show` および `cmp:hide` イベントをトリガーします。`cmp:show` イベントはページの読み込み時にもディスパッチされ、最初のイベントと見なされます。
* **`cmp:loaded`** - データレイヤーにページ上のコアコンポーネントが入力されるとすぐに、データレイヤーが `cmp:loaded` イベントをトリガーします。

### コンポーネントによってトリガーされるイベント {#events-components}

次の表に、これらのイベントと共にイベントをトリガーする標準的なコアコンポーネントを示します。

| コンポーネント | イベント |
|---|---|
| [アコーディオン](/help/components/accordion.md) | `cmp:show` および `cmp:hide` |
| [ボタン](/help/components/button.md) | `cmp:click` |
| [パンくず](/help/components/breadcrumb.md) | `cmp:click` |
| [カルーセル](/help/components/carousel.md) | `cmp:show` および `cmp:hide` |
| [言語ナビゲーション](/help/components/language-navigation.md) | `cmp:click` |
| [ナビゲーション](/help/components/navigation.md) | `cmp:click` |
| [ページ](/help/components/page.md) | `cmp:show` |
| [タブ](/help/components/tabs.md) | `cmp:show` および `cmp:hide` |
| [ティーザー](/help/components/teaser.md) | `cmp:click` |

### イベントパス情報 {#event-path-info}

AEM コアコンポーネントによってトリガーされる各データレイヤーイベントには、以下の JSON オブジェクトを含むペイロードが含まれます。

```json
eventInfo: {
    path: '<component-path>'
}
```

ここでは、`<component-path>` はイベントをトリガーしたデータレイヤー内のコンポーネントへの JSON パスです。`event.eventInfo.path` を介して使用できる値は、パラメーターとして `adobeDataLayer.getState(<component-path>)` に使用できるので重要です。このパラメーターは、イベントをトリガーしたコンポーネントの現在の状態を取得し、カスタムコードが追加のデータにアクセスしてデータレイヤーに追加できるようにします。

次に例を示します。

```javascript
function logEventObject(event) {
    if(event.hasOwnProperty("eventInfo") && event.eventInfo.hasOwnProperty("path")) {
        var dataObject = window.adobeDataLayer.getState(event.eventInfo.path);
        console.debug("The component that triggered this event: ");
        console.log(dataObject);
    }
}

window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function (dl) {
     dl.addEventListener("cmp:show", logEventObject);
});
```

## チュートリアル

データレイヤーとコアコンポーネントをさらに詳しく調べたい場合は、[次の実践チュートリアルをご覧ください](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html)。

>[!TIP]
>
>データレイヤーの柔軟性をさらに詳しく調べるには、カスタムコンポーネントでデータレイヤーを有効にする方法などの統合オプションについて確認してください。
