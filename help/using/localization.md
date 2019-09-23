---
title: コアコンポーネントのローカリゼーション機能
seo-title: コアコンポーネントのローカリゼーション機能
description: コアコンポーネントのローカリゼーション機能
seo-description: コアコンポーネントのローカリゼーション機能
content-type: reference
topic-tags: core-components
index: y
internal: n
translation-type: tm+mt
source-git-commit: c8041e855386b7195fe32dd5dc53458f1d8270b8

---


# コアコンポーネントのローカリゼーション機能 {#localization-features-of-the-core-components}

多くのWebサイトでは、複数の言語や地域にわたってローカライズされた形式でコンテンツを配信する必要があります。 選択されたコアコンポーネントは、スマートリファレンス解決機能を備えており、ローカライズされたサイト構造に基づいて自動的に適合するローカライズされたすべてのコンテンツに対して、統合されたテンプレートを簡単に作成できます。

## 例 — ナビゲーションとフッターを含むローカライズされたページ {#example}

ほとんどのサイトでは、すべてのページにフッターを配置する必要があります。 これらのフッターは、通常、ページのすべてのコンテンツで一致します。 ただし、ローカライズされたコンテンツページの場合は、そのヘッダーまたはフッターのローカライズされたバージョンを表示する必要があります。

同様に、ナビゲーションコンポーネントは通常、すべてのページに表示する必要があります。 ただし、ローカライズされたページのコンテンツも反映する必要があります。

Navigation Core Componentと [Experience Fragment Core Componentのローカリゼーション機能と](navigation.md) 、AEM [の編集可能なテンプレートを使用すると、これは簡単](experience-fragment.md)[](https://docs.adobe.com/content/help/en/experience-manager-64/authoring/siteandpage/templates.html)な作業になります。 この例は、言語ナビゲーションコンポーネントを使用する [ように拡張する](language-navigation.md) こともできます。

## コンテンツ構造 {#content-structure}

AEMとそのコアコンポーネントのすべてのローカリゼーション機能は、ローカライズされたコンテンツに対して明確で論理的なコンテンツ構造に依存しています。

サイトが単に呼び出され、ここに配置されてい `my-site` るとします。

```
/content/my-site
```

また、英語でサイトを作成し、フランス語でも提供するとします。 そのため、単純なページ名がサイトのコン `my-page` テンツツリーの2つのローカリゼーションブランチにあるとします。

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

これは、追加のサイトページを作成するこれらのローカリゼーションブランチの下にあります。

ページフッターは通常、エクスペリエンスフラグメントを使用して作成されるので、ページと同様に英語版とフランス語版が必要になります。 However Experience Fragments are not pages, but are rather parts of pages that can be reused across pages, so they do not live directly under  as the rest of your pages. `/content`Instead they live under their own folder, but since they also must be localized, their structure must mirror the localization structure of your site.

```
/content
+-- experience-fragments
   +-- en
      \-- footer
   \-- fr
      \-- footer
\-- my-site
   +-- en
      \-- my-page
   \-- fr
      \-- my-page
```

対応するページに必要なローカライズコンテンツをコアコンポーネントが見つけられるのは、鏡像化されたローカリゼーション構造を通じてです。

## Page Footer - Experience Fragment {#xf-footer}

The Experience Fragment Component is very flexible and is well-suited for a page header or footer.

Because our hypothetical website is offered in English and French, we will need to create two Experience Fragments, both called  in the locations we described previously.`footer`[](#content-structure)

![](assets/screen-shot-2019-09-09-11.08.28.png)

## ページテンプレート {#template}

フッターは各ページに表示されるので、標準のページテンプレートにエクスペリエンスフラグメントを追加する必要があります。

テンプレートは単に呼び出され `my-template` 、他のテンプレートと共に配置されます。

```
/conf/my-site/settings/wcm/templates/my-template
```

このテンプレートに、ページの基にする基本コンポーネントを追加します。

* [ナビゲーションコンポーネント](navigation.md)
   * ナビゲーションコンポーネントは各ページの上部に表示されます。
   * ナビゲーションコンポーネントでは、ナビゲーションルートを定義し、サイトのナビゲーション構造が開始する場所をコンポーネントに示します。
   * ナビゲーションルートに基づいて、コンポーネントは対応するローカライズされたコンテンツを自動的に見つけることができます。
* [コンテナコンポーネント](container.md)
   * Every page will contain an editable Container Component so that authors can place additional content on the page.
* [エクスペリエンスフラグメント](experience-fragment.md)
   * We point the Experinece Fragment Component to the fragment path in our authoring language of the fragment that represents the footer.
   * Based on that fragment's path and the structure of the experience fragments that mirrors the localized page structure, the component can find the corresponding localized content automatically.
   ![](assets/screen-shot-2019-09-09-11.20.10.png)

## ページ {#pages}

By doing the hard work in setting up the site structure and template, the content author simply needs to add the necessary content to the pages. Thanks to the templates and the localization logic of the components, the navigation and footers will be automatically added to the page and localized.

For example, the author would only need to add content such as a text component to the English and French pages (represented in blue below).

The Navigation Component and Experience Fragment Component come from the page template and know to automatically display the correct content based on the localization structure and the location of the page itself (represented in white below).

![](assets/screen-shot-2019-09-09-11.22.14.png)

## Fitting It All Together {#fitting-it-all-together}

Here is the complete picture of how these simple, but powerful elements work together to deliver localized pages for the content authors.

![](assets/screen-shot-2019-09-09-11.27.58.png)
