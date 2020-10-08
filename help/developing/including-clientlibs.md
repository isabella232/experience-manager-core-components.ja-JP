---
title: クライアントライブラリを含める
description: 使用事例に応じてクライアントライブラリを含める方法は多数あります。
translation-type: tm+mt
source-git-commit: 87e39566617f64b91bd8e98b3779b9b5c426c31c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 82%

---


# ククライアントライブラリを含める{#including-client-libraries}

使用事例に応じて[クライアントライブラリ](/help/developing/archetype/uifrontend.md#clientlibs)を含める方法は多数あります。このドキュメントでは、それぞれの例とサンプル [HTL スニペット](https://docs.adobe.com/content/help/ja-JP/experience-manager-htl/using/overview.html) を紹介します。

## 推奨されるデフォルトの使用方法 {#recommended-default-usage}

状況に何が最適化を調べる時間がない場合は、次の HTL 行をページ `head` 要素内に配置して、クライアントライブラリを含めます。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

これにより、ページ `head` に CSS と JS の両方が含まれますが、JS `script` インクルードに `defer` 属性が追加されるので、ブラウザーは DOM は準備が完了するのを待ってスクリプトを実行し、ページの読み込み速度を最適化します。

## 基本的な使用方法 {#basic-usage}

クライアントライブラリカテゴリの JS と CSS の両方を含める基本構文は、次のとおりです。この構文は、対応するすべての CSS `link` 要素または JS `script` 要素を生成します。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

複数のクライアントライブラリカテゴリに対して、同じ処理を一度に行うには、文字列の配列を `categories` パラメーターに渡します。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## CSS または JS のみ {#css-js-only}

Frequently, one wants to place the CSS includes in the HTML `head` element, and the JS includes just before the closing of the `body` element.

JS ではなく CSS のみを含めるには、`head` で `cssIncludes` を使用します。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

CSS ではなく JS のみを含めるには、`body` を閉じる前に `jsIncludes` を使用します。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 属性 {#attributes}

生成される CSS `link` 要素や JS `script` 要素に属性を適用するには、次のように多数のパラメーターを使用できます。

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

`jsAndCssIncludes` および `cssIncludes` に渡すことができる CSS `link` 属性：

* `media`：文字列

JS `script` attributes that can be passed to `jsAndCssIncludes` and `jsIncludes`:

* `async`：ブール型
* `defer`：ブール型
* `onload`：文字列
* `crossorigin`：文字列

## インライン {#inlining}

In some cases, either for optimization, or for email or [AMP,](amp.md) it might be required to inline the CSS or JS into the output of the HTML.

CSS をインライン化するには、`cssInline` を使用できますが、その場合は前後に `style` 要素を記述する必要があります。

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同様に、`jsInline` を使用して JS をインライン化できますが、前後に `script` 要素を記述する必要があります。

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```
