---
title: クイック検索コンポーネント
description: クイック検索コンポーネントは、Web サイトに検索機能を提供し、訪問者がサイト内を検索して結果を絞り込めるように検索結果を表示します。
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# クイック検索コンポーネント {#quick-search-component}

クイック検索コンポーネントは、Web サイトに検索機能を提供し、一致するコンテンツを訪問者が容易に見つけて結果を表示できるように検索結果を表示します。

## 使用方法 {#usage}

クイック検索コンポーネントを使用すれば、サイト訪問者がコンテンツを検索し、その結果をインプレースで表示し、一致するページに容易に移動できるようになります。ユーザーが検索結果をスクロールすると、それに合わせて新しい結果が動的に取得されます。

[編集ダイアログ](#edit-dialog)では、コンテンツツリー内の検索の開始位置をコンテンツ作成者が定義できます。[デザインダイアログ](#design-dialog)を使用すれば、コンテンツツリーにおける検索の開始位置のデフォルト値、結果セットサイズの上限、検索語句の長さの下限をテンプレート作成者が設定できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、クイック検索コンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.2.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 | クラウドサービスとしてのAEM |
|--- |--- |--- |--- |---|
| v1 | 互換性あり | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retailのサンプルです](https://docs.adobe.com/content/help/en/experience-manager-65/developing/bestpractices/we-retail/we-retail.html)。

### スクリーンショット {#screenshot}

![](assets/screen_shot_2018-01-19at094248.png)

### HTML {#html}

```
<section class="cmp-search" role="search" data-cmp-is="search" data-cmp-min-length="3" data-cmp-results-size="10">
    <form class="cmp-search__form" data-cmp-hook-search="form" method="get" action="/content/we-retail/us/en/equipment.searchresults.json/_jcr_content/root/responsivegrid/search" autocomplete="off">
        <div class="cmp-search__field">
            <i class="cmp-search__icon" data-cmp-hook-search="icon"></i>
            <span class="cmp-search__loading-indicator" data-cmp-hook-search="loadingIndicator"></span>
            <input class="cmp-search__input" data-cmp-hook-search="input" type="text" name="fulltext" placeholder="Search" role="combobox" aria-autocomplete="list" aria-haspopup="true" aria-invalid="false">
            <button class="cmp-search__clear" data-cmp-hook-search="clear">
                <i class="cmp-search__clear-icon"></i>
            </button>
        </div>
    </form>
    <div class="cmp-search__results" data-cmp-hook-search="results" role="listbox" aria-multiselectable="false"></div>
    
<script data-cmp-hook-search="itemTemplate" type="x-template">
    <a class="cmp-search__item" data-cmp-hook-search="item">
        <span class="cmp-search__item-title" data-cmp-hook-search="itemTitle"></span>
    </a>
</script>
</section>
```

### JSON {#json}

```
"search":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "relativePath":"/jcr:content/root/responsivegrid/search",
                     "resultsSize":10,
                     "searchTermMinimumLength":3,
                     ":type":"core/wcm/components/search/v1/search"
                  }
```

### 技術的詳細 {#technical-details}

>[!NOTE]
>
>DOS 攻撃からの検索コンポーネントや AEM ベースアプリケーションの保護は、ディスパッチャーで `mod_security` を使用すればいった、より高いレベルで実装する必要があります。

The latest technical documentation about the Quick Search Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_search_v1).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 編集ダイアログ{#edit-dialog}

編集ダイアログでは、コンテンツツリー内の検索の開始位置をコンテンツ作成者が定義できます。

![](assets/screen_shot_2018-04-03at120132.png)

**検索ルート** - 検索の開始位置となるルートページ。検索ルートは、ブループリントマスター、言語マスター、通常のページのいずれでもかまいません。

## デザインダイアログ{#design-dialog}

デザインダイアログを使用すれば、コンテンツツリーにおける検索の開始位置のデフォルト値、結果セットサイズの上限、検索語句の長さの下限をテンプレート作成者が設定できます。デザインダイアログでは、コンテンツ作成者が使用できるテキスト書式設定オプションをテンプレート作成者が定義できます。

### 「プロパティ」タブ {#properties-tab}

![](assets/screen_shot_2018-04-03at120028.png)

* **検索ルート** - コンテンツ作成者がクイック検索コンポーネントをコンテンツページに配置したときの検索ルートのデフォルト値
* **結果のサイズ** - 検索リクエストで取得される結果の最大数
* **検索語句の最小の長さ** - 検索を開始するために使用される検索語句の長さの下限

>[!NOTE]
>
>「**結果のサイズ**」と「**検索語句の最小の長さ**」は、デザインモード（テンプレートレベル）でしか設定できません。つまり、コンテンツ作成者はこれらの値を変更できません。

>[!CAUTION]
>
>「**結果のサイズ**」が大きすぎる場合や、「**検索語句の最小の長さ**」が小さすぎる場合は、パフォーマンスに影響が出る可能性があります。

### 「スタイル」タブ {#styles-tab}

クイック検索コンポーネントでは、AEM [スタイルシステム](authoring.md#component-styling)をサポートしています。
