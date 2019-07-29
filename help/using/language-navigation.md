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
translation-type: ht
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 言語ナビゲーションコンポーネント{#language-navigation-component}

言語ナビゲーションコンポーネントは、言語／国を指定したサイトナビゲーション機能を提供し、訪問者が同じページを異なるロケールでナビゲートできるようにします。

## 使用方法 {#usage}

多くの場合、Web サイトは様々な地域向けに複数の言語で提供されています。言語ナビゲーションコンポーネントを使用すれば、訪問者は同じページを異なる言語／ロケールで表示できます。

[編集ダイアログ](#edit-dialog)では、グローバルサイトナビゲーションのルートのほか、構造のナビゲーションの深さを定義できます。[デザインダイアログ](#design-dialog)では、同じオプションのデフォルト値をテンプレート作成者が設定できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、言語ナビゲーションコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 互換性あり | 互換性あり | 互換性あり |


コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

言語ナビゲーションコンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html)を参照してください。

## 技術的詳細 {#technical-details}

言語ナビゲーションコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 編集ダイアログ{#edit-dialog}

編集ダイアログでは、グローバルサイトナビゲーションのルートのほか、構造のナビゲーションの深さを定義できます。

![](assets/screen_shot_2018-01-12at133353.png)

* **ナビゲーションルート** - ナビゲーション構造のルートページを定義します。
   * 「**選択ダイアログを開く**」ボタンを使用すれば、コンテンツ構造を容易にナビゲートし、ルートを選択できます。
* **言語構造の深さ** - ナビゲーションルートを基準としたグローバル言語構造の深さ。

## デザインダイアログ{#design-dialog}

デザインダイアログでは、編集ダイアログで使用できるオプションのデフォルト値をテンプレート作成者が設定できます。

### 「プロパティ」タブ {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **ナビゲーションルート** - コンテンツ作成者が言語切り替えコンポーネントをコンテンツページに配置するときのナビゲーションルートのデフォルト値
* **言語構造の深さ** - コンテンツ作成者が言語切り替えコンポーネントをコンテンツページに配置するときの言語構造の深さのデフォルト値

### 「スタイル」タブ {#styles-tab}

言語ナビゲーションコンポーネントでは、AEM [スタイルシステム](authoring.md#component-styling)をサポートしています。