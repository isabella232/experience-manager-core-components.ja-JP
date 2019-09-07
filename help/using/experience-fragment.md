---
title: エクスペリエンスフラグメントコンポーネント
seo-title: エクスペリエンスフラグメントコンポーネント
description: エクスペリエンスフラグメントコンポーネントを使用すると、コンテンツ作成者はエクスペリエンスフラグメントのバリエーションをページに追加できます。
seo-description: エクスペリエンスフラグメントコンポーネントを使用すると、コンテンツ作成者はエクスペリエンスフラグメントのバリエーションをページに追加できます。
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 12d18a31c5507f5bbc713383f4d194d8ab8c4d58

---


# エクスペリエンスフラグメントコンポーネント{#experience-fragment-component}

コアコンポーネントエクスペリエンスフラグメントコンポーネントを使用すると、コンテンツ作成者はローカライズされたサイト構造をサポートしながら、エクスペリエンスフラグメントのバリエーションをページに配置できます。

## 使用方法 {#usage}

コアコンポーネントエクスペリエンスフラグメントコンポーネントを使用すると、コンテンツ作成者は既存のエクスペリエンスフラグメントのアドレスから選択し、コンテンツページに配置できます。エクスペリエンスフラグメントコンポーネントは、ローカライズされたサイト構造もサポートしています。

* The components's properties can be defined in the [configure dialog](#configure-dialog).
* Defaults for the component when adding it to a page can be defined in the [design dialog](#design-dialog).

## ローカライズされたサイト構造のサポート {#localized-site-structure}

エクスペリエンスフラグメントコンポーネントは、ローカライズされたサイト構造に適応し、ページのローカリゼーションに基づいて適切なエクスペリエンスフラグメントをレンダリングします。これを行うには、エクスペリエンスフラグメントは次の条件を満たす必要があります。

* エクスペリエンスフラグメントコンポーネントがテンプレートに追加されます。
* このテンプレートは、下 `/content/<site>`のローカライズされた構造の一部である新しいコンテンツページを作成するために使用します。
* コンテンツページで参照されるエクスペリエンスフラグメントは、以下の `/content/experience-fragments` サイトと同じパターン名を使用することにより、 `/content/<site>` 下のサイトと同じパターンに従う、ローカライズされたエクスペリエンスフラグメント構造の一部です。

この場合、現在のページと同じローカリゼーション（言語、ブループリントまたはライブコピー）を持つフラグメントがテンプレートの一部としてレンダリングされます。

この動作は、テンプレートに追加されるエクスペリエンスフラグメントコンポーネントに制限されます。個々のコンテンツページに追加されたエクスペリエンスフラグメントコンポーネントは、コンポーネント内で設定された正確なエクスペリエンスフラグメントレンディションをレンダリングします。

### 例 {#example}

コンテンツが次のような構造になっているとします。

```
/content
+-- experience-fragments
   \-- we-retail
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- we-retail
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

下の構造は、構造を `/content/experience-fragments/we-retail` 反映していることに注意 `/content/we-retail`してください。

この場合、エクスペリエンスフラグメントコンポーネント `/content/experience-fragments/we-retail/us/en/footerTextXf` がテンプレートに配置されている場合、ローカライズされたページはローカライズされたコンテンツのページに対応するローカライズされたエクスペリエンスフラグメントを自動的にレンダリングします。

したがって、同じテンプレートを使用する `/content/we-retail/ch/de` コンテンツページに移動すると、で `/content/experience-fragments/we-retail/ch/de/footerTextXf``/content/experience-fragments/we-retail/us/en/footerTextXf`はなくレンダリングされます。

### フォールバック {#fallback}

エクスペリエンスフラグメントコンポーネントは、対応するローカライズされたコンポーネントを次の順序で探します。

1. Ffirstは、言語ルートを見つけようとします。
1. 見つからない場合は、blueprintが検出されます。
1. 見つからない場合は、ライブコピーを見つけようとします。
1. 見つからない場合、コンポーネントで設定されているエクスペリエンスフラグメントがデフォルトで設定されます。

## バージョンと互換性 {#version-and-compatibility}

エクスペリエンスフラグメントコンポーネントの現在のバージョンは、2019年8月のコアコンポーネントのリリース2.6.0で導入されたv1であり、このドキュメントで説明しています。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

To experience the Experience Fragment Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/experience-fragment.html).

## 技術的詳細 {#technical-details}

エクスペリエンスフラグメントコンポーネントに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment)。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツ作成者がページにレンダリングするエクスペリエンスフラグメントのバリエーションを選択できます。

![](assets/screen-shot-2019-08-23-10.49.21.png)

"Select Selection **Dialog** 」ボタンを使用して、コンポーネントセレクターを開き、コンテンツページに追加するエクスペリエンスフラグメントコンポーネントのバリエーションを選択します。

エクスペリエンスフラグメントコンポーネントをテンプレートに追加すると、エクスペリエンスフラグメントがローカライズされると自動的にローカライズされます。したがって、ページ上でレンダリングされるものは、明示的に選択したコンポーネントと異なる場合があります。[詳しくは、上記](#example) の例を参照してください。

## デザインダイアログ{#design-dialog}

テンプレート作成者は、テンプレート作成者が、エクスペリエンスフラグメントコンポーネントを使用するコンテンツ作成者に提供されるオプションを定義し、エクスペリエンスフラグメントコンポーネントを配置する際にデフォルト設定されたオプションを定義できます。

![](assets/screen-shot-2019-08-23-10.48.36.png)

The Experience Fragment Component supports the AEM [Style System](authoring.md#component-styling).
