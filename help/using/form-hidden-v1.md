---
title: フォーム非表示コンポーネント（v1）
seo-title: フォーム非表示コンポーネント（v1）
description: コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示することができます。
seo-description: コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示することができます。
uuid: f5005346-def5-4e1f-8f93-e4cfc67a9329
content-type: reference
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: d35f4e71-ec7f-4128-9123-b997dbb5f0cf
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# フォーム非表示コンポーネント（v1）{#form-hidden-component-v}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示することができます。

## 使用方法 {#usage}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを作成して、現在のページに関する情報を AEM に返すことができます。このコンポーネントは、[フォームコンテナコンポーネント](form-container.md)と共に使用するためのものです。

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
>フォーム非表示コンポーネントの現在のバージョンについて詳しくは、[フォーム非表示コンポーネント](form-hidden.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

The following is sample taken from [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](versions.md#release-history-and-compatibility)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツ作成者が非表示フィールドのパラメーターを定義できます。

![](assets/chlimage_1-26.png)

* **名前** - フィールドの名前（フォームデータと共に送信されます）
* **値** - フィールドの値（フォームデータと共に送信されます）
* **識別子** - 識別子は、ページ上で一意である必要があり、スクリプトをこのフォームフィールドにバインドするために使用できます

## デザインダイアログ{#design-dialog}

フォーム非表示コンポーネントにはデザインダイアログはありません。

## 技術的詳細 {#technical-details}

The latest technical documentation about the Form Hidden Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden).

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。
