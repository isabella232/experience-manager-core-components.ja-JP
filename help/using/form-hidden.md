---
title: フォーム非表示コンポーネント
seo-title: フォーム非表示コンポーネント
description: 'null'
seo-description: コアコンポーネントフォーム非表示コンポーネントでは、非表示フィールドを表示できます。
uuid: 63a1b381- f45c-4241- b743- dea8abd45e11
contentOwner: ユーザーは、
content-type: リファレンス
topic-tags: コアコンポーネント
discoiquuid: 36e49035-7641-4bad-8a61-723060032903
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


# フォーム非表示コンポーネント{#form-hidden-component}

コアコンポーネントフォーム非表示コンポーネントでは、非表示フィールドを表示できます。

## 使用方法 {#usage}

コアコンポーネントフォーム非表示コンポーネントでは、現在のページに関する情報をAEMに渡すための非表示フィールドを作成できます。また [、フォームコンテナコンポーネントとともに使用することを意図](form-container.md)しています。

フィールドプロパティは [、設定ダイアログのコンテンツエディターで定義](form-hidden.md)できます。

## バージョンと互換性 {#version-and-compatibility}

フォーム非表示コンポーネントの現在のバージョンはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](form-hidden-v1.md) | 互換性 | 互換性 | 互換性 |

コアコンポーネントバージョンとリリースについて詳しくは、ドキュメント [コアコンポーネントバージョン](versions.md)を参照してください。

## サンプルコンポーネントの出力 {#sample-component-output}

以下は、We. Retailから [取得されたサンプル](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)です。

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
  <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
   <div class="visible aem-GridColumn aem-GridColumn--default--12">
    <input type="hidden" id="ghostToast" name="Invisible Toast" value="ghostToast">
   </div>
 </form>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "hidden": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/hidden",
                  "name": "Invisible Toast",
                  "id": "ghostToast",
                  "value": "ghostToast"
                }
              },
              ":itemsOrder": [
                "hidden"
              ],
              ":type": "weretail/components/form/container"
            }
```

### 技術的詳細 {#technical-details}

フォーム非表示コンポーネントに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden)。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## ダイアログの設定 {#configure-dialog}

設定ダイアログでは、コンテンツ作成者が非表示フィールドのパラメーターを定義できます。

![](assets/chlimage_1-26.png)

* **名前**:フォームデータと共に送信されるフィールドの名前
* **値**:フォームデータと共に送信されるフィールドの値
* **識別子**:識別子はページ上で一意であり、スクリプトをこのフォームフィールドに連結するために使用できます

Because the Form Hidden component normally has no visible attributes, the component&#39;s placeholder in the editor displays the **Name** and **Value** field values if they are assigned in order to help the author identify the appropriate Form Hidden component.

![](assets/screenshot_2018-10-19at094927.png)

## デザインダイアログ {#design-dialog}

フォーム非表示コンポーネントのデザインダイアログはありません。