---
title: フォーム非表示コンポーネント（v1）
description: コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示できます。
index: n
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 100%

---


# フォーム非表示コンポーネント（v1）{#form-hidden-component-v}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示できます。

## 使用方法 {#usage}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを作成して、現在のページに関する情報を AEM に返すことができます。このコンポーネントは、[フォームコンテナコンポーネント](form-container-v1.md)と共に使用するためのものです。

フィールドのプロパティは、コンテンツ編集者が[設定ダイアログ](#configure-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 に付属しているコアコンポーネントのリリース 1.0.0 で最初に導入されたフォーム非表示コンポーネント v1 について説明します。

フォーム非表示コンポーネント v1 の互換性を次の表に示します。

| AEM のバージョン | フォーム非表示コンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、フォーム非表示コンポーネント v1 について説明します。
>
>フォーム非表示コンポーネントの現在のバージョンについて詳しくは、[フォーム非表示コンポーネント](/help/components/forms/form-hidden.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retail](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html) から取得したサンプルです。

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

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](/help/versions.md#release-history-and-compatibility)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツ作成者が非表示フィールドのパラメーターを定義できます。

![](/help/assets/chlimage_1-26.png)

* **名前** - フィールドの名前（フォームデータと共に送信されます）
* **値** - フィールドの値（フォームデータと共に送信されます）
* **識別子** - 識別子は、ページ上で一意である必要があり、スクリプトをこのフォームフィールドにバインドするために使用できます

## デザインダイアログ{#design-dialog}

フォーム非表示コンポーネントにはデザインダイアログはありません。

## 技術的詳細 {#technical-details}

フォームの非表示メントコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden) を参照してください。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。
