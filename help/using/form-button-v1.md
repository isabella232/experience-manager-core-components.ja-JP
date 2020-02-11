---
title: フォームボタンコンポーネント（v1）
description: コアコンポーネントのフォーム非表示コンポーネントを使用すれば、フォームに非表示フィールドを含めることができます。
index: n
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# フォームボタンコンポーネント（v1）{#form-button-component-v}

コアコンポーネントのフォームボタンコンポーネントを使用すれば、アクションをトリガーするボタンフィールドをフォームに含めることができます。

## 使用方法 {#usage}

コアコンポーネントのフォームボタンコンポーネントを使用すれば、フォームの送信をトリガーすることが多いボタンフィールドを作成できます。このコンポーネントは、[フォームコンテナコンポーネント](form-container.md)と共に使用するためのものです。

ボタンのプロパティは、コンテンツ編集者が[設定ダイアログ](form-button-v1.md#main-pars_title)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 に付属しているコアコンポーネントのリリース 1.0.0 で最初に導入されたフォームボタンコンポーネント v1 について説明します。

フォームボタンコンポーネント v1 の互換性を次の表に示します。

| AEM のバージョン | フォームボタンコンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、フォームボタンコンポーネント v1 について説明します。
>
>フォームボタンコンポーネントの現在のバージョンについて詳しくは、[フォームボタンコンポーネント](form-button.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retailのサンプルです](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### スクリーンショット {#screenshot}

![](assets/chlimage_1-48.png)

### HTML {#html}

```
<div class="cmp cmp-button aem-GridColumn aem-GridColumn--default--12">
    <div class="cmp cmp-button">
        <button type="BUTTON" class="btn btn-action btn-primary" name="loveToast" value="ILoveToast">
            Click here if you love toast!
        </button>
    </div>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "button": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/button",
                  "name": "loveToast",
                  "jcr:title": "Click here if you love toast!",
                  "type": "submit",
                  "value": "ILoveToast"
                }
              },
              ":itemsOrder": [
                "button"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](versions.md#main-pars_title_236368006)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツ作成者がボタンのパラメーターを定義できます。

![](assets/chlimage_1-49.png)

* **種類**
   * **ボタン**
   * **送信**

* **タイトル** - ボタンに表示されるテキスト
   * 指定しない場合は、デフォルトでボタンの種類が表示されます

* **名前** - ボタンの名前（フォームデータと共に送信されます）
* **値** - ボタンの値（フォームデータと共に送信されます）

## デザインダイアログ{#design-dialog}

フォームボタンコンポーネントにはデザインダイアログはありません。

## 技術的詳細 {#technical-details}

The latest technical documentation about the Form Button Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。
