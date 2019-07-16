---
title: フォーム非表示コンポーネント
seo-title: フォーム非表示コンポーネント
description: 'null'
seo-description: コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示することができます。
uuid: 63a1b381-f45c-4241-b743-dea8abd45e11
contentOwner: ユーザー
content-type: reference
topic-tags: core-components
discoiquuid: 36e49035-7641-4bad-8a61-723060032903
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
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# フォーム非表示コンポーネント{#form-hidden-component}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示することができます。

## 使用方法 {#usage}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを作成して、現在のページに関する情報を AEM に返すことができます。このコンポーネントは、[フォームコンテナコンポーネント](form-container.md)と共に使用するためのものです。

フィールドのプロパティは、コンテンツ編集者が[設定ダイアログ](form-hidden.md)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、フォーム非表示コンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v2）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性あり | 互換性あり | 互換性あり |
| [v1](form-hidden-v1.md) | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は、[We.Retail](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/we-retail.html) から引用したサンプルです。

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

フォーム非表示コンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツ作成者が非表示フィールドのパラメーターを定義できます。

![](assets/chlimage_1-26.png)

* **名前** - フィールドの名前（フォームデータと共に送信されます）
* **値** - フィールドの値（フォームデータと共に送信されます）
* **識別子** - 識別子は、ページ上で一意である必要があり、スクリプトをこのフォームフィールドにバインドするために使用できます

フォーム非表示コンポーネントには通常、表示される属性がありません。そのため、「**名前**」フィールドと「**値**」フィールドの値が割り当てられている場合、エディターのコンポーネントのプレースホルダーにはそれらのフィールド値が表示され、作成者が適切なフォーム非表示コンポーネントを識別できるようになっています。

![](assets/screenshot_2018-10-19at094927.png)

## デザインダイアログ{#design-dialog}

フォーム非表示コンポーネントにはデザインダイアログはありません。