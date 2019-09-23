---
title: フォームオプションコンポーネント
seo-title: フォームオプションコンポーネント
description: コアコンポーネントのフォームオプションコンポーネントを使用すれば、様々な形式の事前定義済みオプションから選択できます。
seo-description: コアコンポーネントのフォームオプションコンポーネントを使用すれば、様々な形式の事前定義済みオプションから選択できます。
uuid: 7e8714df-75d1-4bb0-b1ee-b7c7450d806a
contentOwner: ユーザー
content-type: reference
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 42289c2b-1671-463a-ac1d-457aa9aefa2a
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# フォームオプションコンポーネント{#form-options-component}

コアコンポーネントのフォームオプションコンポーネントを使用すれば、様々な形式の事前定義済みオプションから選択できます。

## 使用方法 {#usage}

コアコンポーネントのフォームオプションコンポーネントを使用すれば、様々な形式で提供される各種オプションを送信できます。このコンポーネントは、[フォームコンテナコンポーネント](form-container.md)と共に使用するためのものです。

オプションの表示形式、ラベル、個々のオプションは、コンテンツ編集者が[設定ダイアログ](#configure-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、フォームオプションコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v2）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性あり | 互換性あり | 互換性あり |
| [v1](form-options-v1.md) | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

The following is sample taken from We.Retail.[](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)

### スクリーンショット {#screenshot}

![](assets/screen_shot_2018-01-12at113648.png)

### HTML {#html}

```
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-66464844" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-858231075" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-862566768" name="hidden">

</div>
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">

    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container/container">
    
    <div class="options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="cmp-form-options">
        
            <legend class="cmp-form-options__legend">What is your favorite type of toast?</legend>
            <label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="dryToast">
                Plain dry toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="frenchToast">
                French Toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="texasToast">
                Texas Toast
            </label>

    </fieldset>

</div>

</div></form>
```

### JSON {#json}

```
"container":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           "columnCount":12,
                           "gridClassNames":"aem-Grid aem-Grid--12 aem-Grid--default--12",
                           ":items":{  
                              "options_816658469":{  
                                 "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                                 "id":"form-options-269951232",
                                 "title":"What is your favorite type of toast?",
                                 "name":"favToast",
                                 "type":"RADIO",
                                 "items":[  
                                    {  
                                       "value":"dryToast",
                                       "text":"Plain dry toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"frenchToast",
                                       "text":"French Toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"texasToast",
                                       "text":"Texas Toast",
                                       "selected":false,
                                       "disabled":false
                                    }
                                 ],
                                 ":type":"core/wcm/sandbox/components/form/options/v2/options"
                              }
                           },
                           ":itemsOrder":[  
                              "options_816658469"
                           ],
                           ":type":"core/wcm/sandbox/components/form/container/v2/container"
                        }
```

### 技術的詳細 {#technical-details}

The latest technical documentation about the Form Options Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、表示するオプションのタイプ、ラベル、使用可能なオプションをコンテンツ作成者が定義できます。

![](assets/screen_shot_2018-01-12at113153.png)

* **タイプ** - オプションの表示方法
   * **チェックボックス**
   * **ラジオボタン**
   * **ドロップダウン**
   * **複数選択ドロップダウン**
* **タイトル** - オプションのラベルとして表示されるタイトル
* **名前** - フィールドの名前（フォームデータと共に送信されます）
* **オプションの定義元のソース**
   * **ローカル** - コンポーネント内に定義
      * 値を追加するには「**追加**」ボタンを、値を削除するには「**削除**」を、それぞれタップまたはクリックします。
      * **値** - フォームの送信時にそのオプションが選択されている場合に保存される値
      * **テキスト** - フォームに表示されるオプションのラベル
      * **アクティブ** - フォームの読み込み時にオプションが選択済みとしてマークされます
      * **無効** - オプションは選択できませんが、表示されます
      * **リスト** - AEM の他の場所で定義されている静的リストがオプションに使用されます
         * **リスト** - AEM 内の静的リストのパス
            * 参照ボタンを使用してリストリソースを特定します
      * **データソース** - オプションにデータソースが使用されます
         * **データソース** - データソースのリソースタイプ
* **ヘルプメッセージ** - フィールドに入力できる内容をユーザーに伝えるヒント

## デザインダイアログ{#design-dialog}

### 「スタイル」タブ {#styles-tab}

フォームオプションコンポーネントでは、AEM [スタイルシステム](authoring.md#component-styling)をサポートしています。