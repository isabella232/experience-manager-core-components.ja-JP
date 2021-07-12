---
title: フォームテキストコンポーネント（v1）
description: コアコンポーネントのフォームテキストコンポーネントを使用すれば、送信するフォームテキストを入力できます。
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 100%

---

# フォームテキストコンポーネント（v1） {#form-text-component-v}

コアコンポーネントのフォームテキストコンポーネントを使用すれば、送信するフォームテキストを入力できます。

## 使用方法 {#usage}

フォームテキストコンポーネントを使用すれば、各種テキストを送信できます。このコンポーネントは、[フォームコンテナコンポーネント](form-container-v1.md)と共に使用するためのものです。

テキスト検証のタイプ、ラベル、ヘルプメッセージは、コンテンツ編集者が[設定ダイアログ](#configure-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 に付属しているコアコンポーネントのリリース 1.0.0 で最初に導入されたフォームテキストコンポーネント v1 について説明します。

フォームテキストコンポーネント v1 の互換性を次の表に示します。

| AEM のバージョン | フォームテキストコンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、フォームテキストコンポーネント v1 について説明します。
>
>フォームテキストコンポーネントの現在のバージョンについて詳しくは、[フォームテキストコンポーネント](/help/components/forms/form-text.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retail](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html) から取得したサンプルです。

### スクリーンショット {#screenshot}

![](/help/assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
     <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
     <div class="cmp cmp-form-field aem-GridColumn aem-GridColumn--default--12">
   <div class="form-group">
       <label for="form-text-978484744">How many pieces of toast would you like?</label>
          <input type="number" id="form-text-978484744" name="pieces">
   </div>
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
                "text": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/text",
                  "name": "piecesOfToast",
                  "jcr:title": "How many pieces of toast would you like?",
                  "type": "number",
                  "rows": "2"
                }
              },
              ":itemsOrder": [
                "text"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](/help/versions.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、入力するテキストの種類とデフォルト値およびラベルをコンテンツ作成者が定義できます。

### メイン {#main}

![](/help/assets/chlimage_1-23.png)

* **制約** - 入力するテキストの種類で、これを基準にテキストが検証されます

   * **テキスト**
   * **テキスト領域**
   * **電子メール**
   * **電話番号**
   * **日付**
   * **番号**
   * **パスワード**

* **テキスト行数** - テキスト領域に表示する行数（「**制約**」が&#x200B;**テキスト領域**&#x200B;に設定されている場合にのみ表示）

* **ラベル** - フィールドに表示するラベル
* **ラベルを非表示にします** - ラベルがアクセシビリティのためにのみ必要で、フィールドに関するその他の視覚的情報には影響しない場合に必要です
* **エレメント名** - フォームデータと共に送信されるフィールドの名前
* **値** - フィールドに事前入力されるデフォルト値

###  について {#about}

![](/help/assets/chlimage_1-24.png)

* **ヘルプメッセージ** - フィールドに入力できる内容をユーザーに伝えるヒント
* **ヘルプメッセージをプレースホルダーとして表示** - フォーム入力が空でフォーカスされていない場合、フォーム入力内にヘルプメッセージを表示するかどうか

### 制約 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **制約メッセージ**

   * 値が適切な型でない場合に、フォーム送信時にツールチップとして表示されるメッセージ
   * 制約タイプが&#x200B;**テキスト**&#x200B;および&#x200B;**テキスト領域**&#x200B;の場合は表示されません

* **必須** - 選択した場合、ユーザーはフォームを送信する前に値に入力する必要があります
* **読み取り専用にする** - 選択した場合、ユーザーはフィールドの値を変更できません

## デザインダイアログ {#design-dialog}

フォームテキストコンポーネントにはデザインダイアログはありません。

## 技術的詳細 {#technical-details}

フォームテキストコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text) を参照してください。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。
