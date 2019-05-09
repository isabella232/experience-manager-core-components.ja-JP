---
title: フォームボタンコンポーネント
seo-title: フォームボタンコンポーネント
description: 'null'
seo-description: コアコンポーネントフォーム非表示コンポーネントを使用すると、フォームに非表示フィールドを含めることができます。
uuid: 22c53cd0- d0bc-4e5d-89f3-5ac4f61a9100
contentOwner: ユーザーは、
content-type: リファレンス
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: a6e2974a-243f-40ab-903c- c7d3e8615bcc
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


# フォームボタンコンポーネント{#form-button-component}

コアコンポーネントフォームのボタンコンポーネントを使用すると、ページ上のアクションをトリガーするボタンを含めることができます。

## 使用方法 {#usage}

Core Component Form Buttonコンポーネントを使用すると、ボタンフィールドを作成できます。多くの場合、フォームの送信をトリガーし、 [フォームコンテナコンポーネントとともに使用することを意図](form-container.md)しています。

ボタンのプロパティは [、設定ダイアログのコンテンツエディターで定義](form-button.md)できます。

## バージョンと互換性 {#version-and-compatibility}

フォームボタンコンポーネントの現在のバージョンはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](form-button-v1.md) | 互換性 | 互換性 | 互換性 |

コアコンポーネントバージョンとリリースについて詳しくは、ドキュメント [コアコンポーネントバージョン](versions.md)を参照してください。

## サンプルコンポーネントの出力 {#sample-component-output}

以下は、We. Retailから [取得されたサンプル](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)です。

### スクリーンショット {#screenshot}

![](assets/screen_shot_2018-01-12at120021.png)

### HTML {#html}

```
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="button aem-GridColumn aem-GridColumn--default--12">
<button type="BUTTON" class="cmp-form-button" name="loveToast" value="ILoveToast">Click here if you love toast!</button>
</div>

</form>
</div>
```

### JSON {#json}

```
"button":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           ":type":"core/wcm/sandbox/components/form/button/v2/button",
                           "name":"loveToast",
                           "jcr:title":"Click here if you love toast!",
                           "type":"button",
                           "value":"ILoveToast"
                        }
```

### 技術的詳細 {#technical-details}

フォームボタンコンポーネント [に関する最新の技術ドキュメントは、GitHubで確認](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button)できます。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## ダイアログの設定 {#configure-dialog}

設定ダイアログでは、コンテンツ作成者がボタンのパラメーターを定義できます。

### 「プロパティ」タブ {#properties-tab}

![](assets/screen_shot_2018-01-12at120433.png)

* **種類**

   * **ボタン**
   * **送信**

* **タイトル** -ボタンに表示されるテキスト

   * 何も指定しなかった場合、ボタンの種類がデフォルトに設定されます

* **名前** -フォームデータとともに送信されるボタンの名前
* **値** -フォームデータと共に送信されるボタンの値

## デザインダイアログ {#design-dialog}

### 「スタイル」タブ {#styles-tab}

フォームボタンコンポーネントでは、AEM [スタイルシステム](authoring.md#component-styling)がサポートされています。