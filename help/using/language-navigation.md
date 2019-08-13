---
title: 言語ナビゲーションコンポーネント
seo-title: 言語ナビゲーションコンポーネント
description: 'null'
seo-description: 言語ナビゲーションコンポーネントは、言語／国を指定したサイトナビゲーション機能を提供し、訪問者が同じページを異なるロケールでナビゲートできるようにします。
uuid: ce736458-9cdf-4bc2-b90f-9c5a62fe1ca0
content-type: reference
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 8f232eb0-65d5-4075-8668-75f1366882c8
disttype: dist5
gnavtheme: light
groupsectionnavitems: ' no'
hidemerchandisingbar: inherit
hidepromocomponent: inherit
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8a34ecc432e489b8dc025aeda29d8eba9c788861

---


# 言語ナビゲーションコンポーネント{#language-navigation-component}

言語ナビゲーションコンポーネントは、言語／国を指定したサイトナビゲーション機能を提供し、訪問者が同じページを異なるロケールでナビゲートできるようにします。

## 使用方法 {#usage}

多くの場合、Webサイトは様々な地域の複数言語で提供されます。言語ナビゲーションコンポーネントを使用すれば、訪問者は同じページを異なる言語／ロケールで表示できます。したがって、スイスドイツ語バージョンのWebサイト上の読者は、同じページの英語版に簡単に切り替えることができます。言語ナビゲーションコンポーネントは、サイト言語のstuctureを理解し、対応するページを自動的に見つけます。

[編集ダイアログ](#edit-dialog)では、グローバルサイトナビゲーションのルートのほか、構造のナビゲーションの深さを定義できます。[デザインダイアログ](#design-dialog)では、同じオプションのデフォルト値をテンプレート作成者が設定できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、言語ナビゲーションコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

To experience the Language Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html).

## 技術的詳細 {#technical-details}

言語ナビゲーションコンポーネントに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation)。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## デザインダイアログ{#design-dialog}

編集ダイアログでは、グローバルサイトナビゲーションのルートのほか、構造のナビゲーションの深さを定義できます。

通常、これらの設定はページテンプレートのleveでのみ行う必要があります。ただし、 [編集ダイアログを使用してページレベルで変更](#edit-dialog)することができます。

### 「プロパティ」タブ {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **ナビゲーションルート**
   * サイトのナビゲーションナビゲーションが開始する場所です。
   * サイトの言語構造は、このルート下の次のレベルから始まります。
* **言語構造の深さ**
   * これは **、ナビゲーションルートの下のコンテンツツリーのレベルが、サイトの言語構造を** 表すものです。例:
      * `1` は、通常、言語のみが選択されていることを意味します。
      * `2` 言い換えれば、言語と国を自由に選択できます。
      * `3` 通常、言語、国、地域の選択があります。

#### 例 {#example}

コンテンツは次のようになります。

```
/content
+-- we-retail
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      +-- it
+-- wknd-events
\-- wknd-shop
```

サイトe. Retailの場合は、おそらくヘッダーの一部として言語ナビゲーションコンポーネントをページテンプレートに配置する必要があります。テンプレートの一部として、そのサイトの **ローカライズ** されたコンテンツが開始される `/content/we-retail` ため、コンポーネントのナビゲーションルートを設定できます。また、構造の2 **** つのレベル（国の場合はラグージュ）の構造の `2` ため、言語構造の深さを設定する必要もあります。

**«ナビゲーションルート** »の値を使用すると、言語コンポーネントは、ナビゲーションが開始した後 `/content/we-retail` に、コンテンツツリーの次の2レベルをサイトの言語ナビゲーション構造として認識できます（ **言語構造の深さ** の値で定義されているように、コンテンツツリーの次の2つのレベルを認識する）。

ユーザーがどのページを閲覧しているかにかかわらず、言語ナビゲーションコンポーネントは、現在のページの場所を把握し、その後に対応するページに転送して、対応するページを別の言語で見つけることができます。

### 「スタイル」タブ {#styles-tab}

言語ナビゲーションコンポーネントでは、AEM [スタイルシステム](authoring.md#component-styling)をサポートしています。

## 編集ダイアログ{#edit-dialog}

通常、言語ナビゲーションコンポーネントはサイトのページテンプレートに追加し、設定する必要があります。ただし、言語ナビゲーションコンポーネントを個々のコンテンツページに追加する必要がある場合、編集ダイアログでは、コンテンツ作成者がデザインダイアログで [説明したとおりに同じ値を設定](#design-dialog)できます。

![](assets/screen_shot_2018-01-12at133353.png)
