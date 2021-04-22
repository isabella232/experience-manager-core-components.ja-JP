---
title: クライアントライブラリを含める
description: 使用事例に応じてクライアントライブラリを含める方法は多数あります。
role: Architect, Developer, Administrator
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
translation-type: ht
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---

# クライアントライブラリを含める {#including-client-libraries}

使用事例に応じて[クライアントライブラリ](/help/developing/archetype/uifrontend.md#clientlibs)を含める方法は多数あります。このドキュメントでは、それぞれの例とサンプル [HTL スニペット](https://docs.adobe.com/content/help/ja-JP/experience-manager-htl/using/overview.html)を紹介します。

## 推奨されるデフォルトの使用方法 {#recommended-default-usage}

状況に何が最適かを調べる時間がない場合は、次の HTL 行をページ `head` 要素内に配置して、クライアントライブラリを含めます。

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

複数のクライアントライブラリカテゴリに対して、同じ処理を一度におこなうには、文字列の配列を `categories` パラメーターに渡します。

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## CSS または JS のみ {#css-js-only}

HTML `head` 要素に CSS インクルードを配置し、`body` 要素を閉じる直前に JS インクルードを配置することがよくあります。

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

* `media`：`jsAndCssIncludes` および `jsIncludes` に渡すことができる文字列 JS `script` 属性：
* `async`：ブール型
* `defer`：ブール型
* `onload`：文字列
* `crossorigin`：文字列

## インライン {#inlining}

場合によっては、最適化用、または電子メールまたは [AMP](amp.md) 用として、CSS または JS を HTML の出力にインライン化する必要が出ることがあります。

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

## コンテキスト対応 CSS と JavaScript の読み込み {#context-aware-loading}

[ページコンポーネント](/help/components/page.md)では、開発者定義のコンテキスト対応 CSS、JavaScript、メタタグの読み込みもサポートしています。

これをおこなうには、次の構造を使用して `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` の[コンテキスト対応リソース](context-aware-configs.md)を作成します。

```text
com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig
    - prefixPath="/some/path"
    + item01
        - element=["link"|"script"|"meta"]
        - location=["header"|"footer"]
        + attributes
            - attributeName01="attributeValue01"
            - attributeName02="attributeValue02"
            ...
    + item02
        ...
    ...
```

[詳しくは、ページコンポーネントの技術ドキュメントを参照してください。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
