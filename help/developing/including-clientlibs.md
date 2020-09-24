---
title: クライアントライブラリを含める
description: 使用事例に応じて、クライアントライブラリを含める方法はいくつかあります。
translation-type: tm+mt
source-git-commit: 24f718be2ba66113eda970c213c6ce4baec51752
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---


# クライアントライブラリを含める {#including-client-libraries}

使用事例に応じて、 [クライアントライブラリを含める方法はいくつかあります](/help/developing/archetype/uifrontend.md#clientlibs) 。 このドキュメントでは、それぞれの例とサンプル [HTLスニペット](https://docs.adobe.com/content/help/ja-JP/experience-manager-htl/using/overview.html) を紹介します。

## 推奨されるデフォルトの使用方法 {#recommended-default-usage}

状況に最適なものを調べる時間がない場合は、次のHTL行をページ `head` 要素内に配置して、クライアントライブラリを含めます。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

ページにはCSSとJSの両方が含まれますが、JSのインクルードに `head``defer``script` 属性が追加されるので、ブラウザーはDOMの準備が完了するのを待ってスクリプトを実行し、ページの読み込み速度を最適化します。

## 基本的な使用方法 {#basic-usage}

クライアントライブラリカテゴリのJSとCSSの両方を含める基本構文は、次のとおりです。この構文は、対応するすべてのCSS `link` 要素またはJS `script` 要素を生成します。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

複数のクライアントライブラリカテゴリに対して同じ処理を一度に行うには、文字列の配列を `categories` パラメーターに渡します。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## CSSまたはJSのみ {#css-js-only}

CSSインクルードをHTML `head``body` 要素に配置し、JSインクルードを要素の終了直前に配置することがよくあります。&#x200B;
で、JS `head`ではなくCSSのみを含める場合は、次を使用しま `cssIncludes`す。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

閉じる前に、CSSではなくJSのみを含める場合は、次を使用し `body` ま `jsIncludes`す。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 属性 {#attributes}

生成されるCSS `link` 要素やJS `script` 要素に属性を適用するには、次のような多数のパラメータを使用できます。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base',
    media='print',
    async=true,
    defer=true,
    onload='console.log(\'loaded: \' + this.src)',
    crossorigin='anonymous'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

CSS `link` 属性のうち、 `jsAndCssIncludes` およびに渡すことができるもの `cssIncludes`:

* `media`:文字列&#x200B;JS `script` 属性を指定します。この属性は、およびに渡すこ `jsAndCssIncludes` とができ `jsIncludes`ます。

* `async`: ブール型
* `defer`: ブール型
* `onload`: string
* `crossorigin`: string

## インライン {#inlining}

場合によっては、最適化のため、または電子メールまたは [AMPのために](amp.md) 、CSSまたはJSをHTMLの出力にインライン化する必要があります。
CSSをインラインにするに `cssInline` は、を使用できます。この場合、周囲の `style` 要素を記述する必要があります。

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同様に、JSをインラインにする場合 `jsInline` は、を使用できます。この場合、周囲の `script` 要素を記述する必要があります。

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```
