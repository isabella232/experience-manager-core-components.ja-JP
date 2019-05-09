---
title: 言語ナビゲーションコンポーネント
seo-title: 言語ナビゲーションコンポーネント
description: 'null'
seo-description: 言語ナビゲーションコンポーネントは、サイトの言語/国ナビゲーションを提供し、訪問者が異なるロケールの同じページに移動できるようにします。
uuid: ce736458-9cdf-4bc2- b90f-9c5a62fe1ca0
content-type: リファレンス
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: 8f232eb0-65d5-4075-8668-75f1366882c8
disttype: dist5
gnavtheme: light
groupsectionnavitems: ' '
hidemerchandisingbar: inherit
hidepromocomponent: inherit
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 言語ナビゲーションコンポーネント{#language-navigation-component}

言語ナビゲーションコンポーネントは、サイトの言語/国ナビゲーションを提供し、訪問者が異なるロケールの同じページに移動できるようにします。

## 使用方法 {#usage}

多くの場合、Webサイトは様々な地域の複数言語で提供されています。言語ナビゲーションコンポーネントを使用すると、訪問者は異なる言語/ロケールで同じページを表示できます。

[編集ダイアログ](#edit-dialog) を使用すると、グローバルサイトナビゲーションのルートを定義したり、ナビゲーションの構造をどれだけ深くするかを指定できます。[デザインダイアログ](#design-dialog)で、テンプレート作成者は同じオプションのデフォルト値を設定できます。

## バージョンと互換性 {#version-and-compatibility}

言語ナビゲーションコンポーネントの現在のバージョンは、2018年1月のコアコンポーネントのリリース2.0.0で導入されたv1であり、このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 互換性 | 互換性 | 互換性 |


コアコンポーネントバージョンとリリースについて詳しくは、ドキュメント [コアコンポーネントバージョン](versions.md)を参照してください。

## サンプルコンポーネントの出力 {#sample-component-output}

以下は、We. Retailから [取得されたサンプル](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)です。

### スクリーンショット {#screenshot}

![](assets/screen_shot_2018-01-12at133119.png)

### HTML {#html}

```
<nav class="cmp-languagenavigation">
    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-en cmp-languagenavigation__item--level-0 cmp-languagenavigation__item--active">
        
    <span class="cmp-languagenavigation__item-title" lang="en">United States</span>

    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-en cmp-languagenavigation__item--level-1 cmp-languagenavigation__item--active">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/us/en/equipment.html" hreflang="en" lang="en" rel="alternate" title="English">English</a>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-es cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/us/es.html" hreflang="es" lang="es" rel="alternate" title="Español">Español</a>

    </li>

    </ul>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--countrycode-CA cmp-languagenavigation__item--langcode-en-CA cmp-languagenavigation__item--level-0">
        
    <span class="cmp-languagenavigation__item-title" lang="en-CA">Canada</span>

    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--countrycode-CA cmp-languagenavigation__item--langcode-en-CA cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/ca/en/equipment.html" hreflang="en-CA" lang="en-CA" rel="alternate" title="English">English</a>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--countrycode-CA cmp-languagenavigation__item--langcode-en-CA cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/ca/fr.html" hreflang="en-CA" lang="en-CA" rel="alternate" title="Français">Français</a>

    </li>

    </ul>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--countrycode-CH cmp-languagenavigation__item--langcode-de-CH cmp-languagenavigation__item--level-0">
        
    <span class="cmp-languagenavigation__item-title" lang="de-CH">Switzerland</span>

    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--countrycode-CH cmp-languagenavigation__item--langcode-de-CH cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/ch/de.html" hreflang="de-CH" lang="de-CH" rel="alternate" title="Deutsch">Deutsch</a>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--countrycode-CH cmp-languagenavigation__item--langcode-de-CH cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/ch/fr.html" hreflang="de-CH" lang="de-CH" rel="alternate" title="Français">Français</a>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--countrycode-CH cmp-languagenavigation__item--langcode-de-CH cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/ch/it.html" hreflang="de-CH" lang="de-CH" rel="alternate" title="Italiano">Italiano</a>

    </li>

    </ul>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-de cmp-languagenavigation__item--level-0">
        
    <span class="cmp-languagenavigation__item-title" lang="de">Germany</span>

    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-de cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/de/de.html" hreflang="de" lang="de" rel="alternate" title="Deutsch">Deutsch</a>

    </li>

    </ul>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-fr cmp-languagenavigation__item--level-0">
        
    <span class="cmp-languagenavigation__item-title" lang="fr">France</span>

    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-fr cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/fr/fr.html" hreflang="fr" lang="fr" rel="alternate" title="Français">Français</a>

    </li>

    </ul>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-es cmp-languagenavigation__item--level-0">
        
    <span class="cmp-languagenavigation__item-title" lang="es">Spain</span>

    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-es cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/es/es.html" hreflang="es" lang="es" rel="alternate" title="Español">Español</a>

    </li>

    </ul>

    </li>

    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-it cmp-languagenavigation__item--level-0">
        
    <span class="cmp-languagenavigation__item-title" lang="it">Italy</span>

    <ul class="cmp-languagenavigation__group">
        
    <li class="cmp-languagenavigation__item cmp-languagenavigation__item--langcode-it cmp-languagenavigation__item--level-1">

    <a class="cmp-languagenavigation__item-link" href="/content/we-retail/it/it.html" hreflang="it" lang="it" rel="alternate" title="Italiano">Italiano</a>

    </li>

    </ul>

    </li>

    </ul>
</nav>
```

### JSON {#json}

```
"languagenavigation":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "items":[  
                        {  
                           "children":[  
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":true,
                                 "title":"English",
                                 "locale":"en",
                                 "country":"",
                                 "language":"en",
                                 "url":"/content/we-retail/us/en/equipment.html",
                                 "path":"/content/we-retail/us/en/equipment",
                                 "description":null,
                                 "lastModified":1515760174857
                              },
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Español",
                                 "locale":"es",
                                 "country":"",
                                 "language":"es",
                                 "url":"/content/we-retail/us/es.html",
                                 "path":"/content/we-retail/us/es",
                                 "description":null,
                                 "lastModified":1474673505454
                              }
                           ],
                           "level":0,
                           "active":true,
                           "title":"United States",
                           "locale":"en",
                           "country":"",
                           "language":"en",
                           "url":"/content/we-retail/us/en/equipment.html",
                           "path":"/content/we-retail/us/en/equipment",
                           "description":null,
                           "lastModified":1515760174857
                        },
                        {  
                           "children":[  
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"English",
                                 "locale":"en_CA",
                                 "country":"CA",
                                 "language":"en-CA",
                                 "url":"/content/we-retail/ca/en/equipment.html",
                                 "path":"/content/we-retail/ca/en/equipment",
                                 "description":null,
                                 "lastModified":1477493028617
                              },
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Français",
                                 "locale":"en_CA",
                                 "country":"CA",
                                 "language":"en-CA",
                                 "url":"/content/we-retail/ca/fr.html",
                                 "path":"/content/we-retail/ca/fr",
                                 "description":null,
                                 "lastModified":1474673388792
                              }
                           ],
                           "level":0,
                           "active":false,
                           "title":"Canada",
                           "locale":"en_CA",
                           "country":"CA",
                           "language":"en-CA",
                           "url":"/content/we-retail/ca/en/equipment.html",
                           "path":"/content/we-retail/ca/en/equipment",
                           "description":null,
                           "lastModified":1477493028617
                        },
                        {  
                           "children":[  
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Deutsch",
                                 "locale":"de_CH",
                                 "country":"CH",
                                 "language":"de-CH",
                                 "url":"/content/we-retail/ch/de.html",
                                 "path":"/content/we-retail/ch/de",
                                 "description":null,
                                 "lastModified":1474673744891
                              },
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Français",
                                 "locale":"de_CH",
                                 "country":"CH",
                                 "language":"de-CH",
                                 "url":"/content/we-retail/ch/fr.html",
                                 "path":"/content/we-retail/ch/fr",
                                 "description":null,
                                 "lastModified":1474673356319
                              },
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Italiano",
                                 "locale":"de_CH",
                                 "country":"CH",
                                 "language":"de-CH",
                                 "url":"/content/we-retail/ch/it.html",
                                 "path":"/content/we-retail/ch/it",
                                 "description":null,
                                 "lastModified":1474673460578
                              }
                           ],
                           "level":0,
                           "active":false,
                           "title":"Switzerland",
                           "locale":"de_CH",
                           "country":"CH",
                           "language":"de-CH",
                           "url":"/content/we-retail/ch.html",
                           "path":"/content/we-retail/ch",
                           "description":null,
                           "lastModified":1474673057327
                        },
                        {  
                           "children":[  
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Deutsch",
                                 "locale":"de",
                                 "country":"",
                                 "language":"de",
                                 "url":"/content/we-retail/de/de.html",
                                 "path":"/content/we-retail/de/de",
                                 "description":null,
                                 "lastModified":1474673744681
                              }
                           ],
                           "level":0,
                           "active":false,
                           "title":"Germany",
                           "locale":"de",
                           "country":"",
                           "language":"de",
                           "url":"/content/we-retail/de.html",
                           "path":"/content/we-retail/de",
                           "description":null,
                           "lastModified":1474673019700
                        },
                        {  
                           "children":[  
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Français",
                                 "locale":"fr",
                                 "country":"",
                                 "language":"fr",
                                 "url":"/content/we-retail/fr/fr.html",
                                 "path":"/content/we-retail/fr/fr",
                                 "description":null,
                                 "lastModified":1474673321300
                              }
                           ],
                           "level":0,
                           "active":false,
                           "title":"France",
                           "locale":"fr",
                           "country":"",
                           "language":"fr",
                           "url":"/content/we-retail/fr.html",
                           "path":"/content/we-retail/fr",
                           "description":null,
                           "lastModified":1474672999375
                        },
                        {  
                           "children":[  
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Español",
                                 "locale":"es",
                                 "country":"",
                                 "language":"es",
                                 "url":"/content/we-retail/es/es.html",
                                 "path":"/content/we-retail/es/es",
                                 "description":null,
                                 "lastModified":1474673542068
                              }
                           ],
                           "level":0,
                           "active":false,
                           "title":"Spain",
                           "locale":"es",
                           "country":"",
                           "language":"es",
                           "url":"/content/we-retail/es.html",
                           "path":"/content/we-retail/es",
                           "description":null,
                           "lastModified":1474673075638
                        },
                        {  
                           "children":[  
                              {  
                                 "children":[  

                                 ],
                                 "level":1,
                                 "active":false,
                                 "title":"Italiano",
                                 "locale":"it",
                                 "country":"",
                                 "language":"it",
                                 "url":"/content/we-retail/it/it.html",
                                 "path":"/content/we-retail/it/it",
                                 "description":null,
                                 "lastModified":1474673426215
                              }
                           ],
                           "level":0,
                           "active":false,
                           "title":"Italy",
                           "locale":"it",
                           "country":"",
                           "language":"it",
                           "url":"/content/we-retail/it.html",
                           "path":"/content/we-retail/it",
                           "description":null,
                           "lastModified":1474673037021
                        }
                     ],
                     ":type":"core/wcm/sandbox/components/languagenavigation/v1/languagenavigation"
                  }
```

### 技術的詳細 {#technical-details}

言語ナビゲーションコンポーネントに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation)。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## ダイアログを編集 {#edit-dialog}

編集ダイアログを使用すると、グローバルサイトナビゲーションのルートを定義したり、ナビゲーションの構造をどれだけ深くするかを指定できます。

![](assets/screen_shot_2018-01-12at133353.png)

* **ナビゲーションルート**ナビゲーション構造のルートページを定義します。
   * 「選択ダイアログ **を開く** 」ボタンを使用して、コンテンツ構造を簡単にナビゲートし、ルートを選択します。
* **ナビゲーションルートに対するグローバル言語構造の言語構造の深**さの深さ。

## デザインダイアログ {#design-dialog}

テンプレート作成者は、デザインダイアログを使用して、編集ダイアログで使用できるオプションのデフォルト値を設定できます。

### 「プロパティ」タブ {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **コンテンツ作成者がコンテンツページに言語切り替えコンポーネントを配置したときのナビゲーションルートのナビゲーションルート**デフォルト値
* **コンテンツ作成者がコンテンツページに言語切り替えコンポーネントを配置するときの言語構造の深さ**のデフォルト値

### 「スタイル」タブ {#styles-tab}

言語ナビゲーションコンポーネントでは、AEM [スタイルシステム](authoring.md#component-styling)がサポートされています。