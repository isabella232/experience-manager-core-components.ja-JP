---
title: フォーム非表示コンポーネント（v1）
seo-title: フォーム非表示コンポーネント（v1）
description: コアコンポーネントフォーム非表示コンポーネントでは、非表示フィールドを表示できます。
seo-description: コアコンポーネントフォーム非表示コンポーネントでは、非表示フィールドを表示できます。
uuid: f5005346- def5-4e1f-8f93- e4cfc67a9329
content-type: リファレンス
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: d35f4e71- ec7f-4128-9123- b997dbb5f0cf
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# フォーム非表示コンポーネント（v1）{#form-hidden-component-v}

コアコンポーネントフォーム非表示コンポーネントでは、非表示フィールドを表示できます。

## 使用方法 {#usage}

コアコンポーネントフォーム非表示コンポーネントでは、現在のページに関する情報をAEMに渡すための非表示フィールドを作成できます。また [、フォームコンテナコンポーネントとともに使用することを意図](form-container.md)しています。

フィールドプロパティは [、設定ダイアログのコンテンツエディターで定義](#configure-dialog)できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、フォーム非表示コンポーネントのv1について説明します。これには、元々、コアコンポーネントのリリース1.0.0とAEM6.3とのリリースが導入されています。

次の表に、Form Hidden Componentのv1との互換性を示します。

| AEM のバージョン | フォーム非表示コンポーネントv1 |
|--- |--- |
| 6.3 | 互換性 |
| 6.4 | 互換性 |

>[!CAUTION]
>
>このドキュメントでは、フォーム非表示コンポーネントのv1について説明します。
>
>フォーム非表示コンポーネントの現在のバージョンの詳細については [、「フォーム非表示コンポーネント](form-hidden.md) 」ドキュメントを参照してください。

## サンプルコンポーネントの出力 {#sample-component-output}

以下は、We. Retailから [取得されたサンプル](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)です。

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
>コアコンポーネントからのJSONエクスポートには、コアコンポーネントのリリース1.1.0が必要です。詳しくは [、コアコンポーネントv1](versions.md#release-history-and-compatibility) の互換性情報を参照してください。

## ダイアログの設定 {#configure-dialog}

設定ダイアログでは、コンテンツ作成者が非表示フィールドのパラメーターを定義できます。

![](assets/chlimage_1-26.png)

* **名前** -フォームデータと共に送信されるフィールドの名前
* **Value** -フォームデータと共に送信されるフィールドの値
* **識別子** -識別子はページ上で一意である必要があり、スクリプトをこのフォームフィールドに連結するために使用できます

## デザインダイアログ {#design-dialog}

フォーム非表示コンポーネントのデザインダイアログはありません。

## 技術的詳細 {#technical-details}

フォーム非表示コンポーネントに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)。

コアコンポーネントプロジェクト全体をGitHubからダウンロードできます。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。
