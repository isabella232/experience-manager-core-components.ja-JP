---
title: フォームオプションコンポーネント（v1）
description: コアコンポーネントのフォームオプションコンポーネントを使用すれば、様々な形式の事前定義済みオプションから選択できます。
index: n
translation-type: ht
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# フォームオプションコンポーネント（v1）{#form-options-component-v}

コアコンポーネントのフォームオプションコンポーネントを使用すれば、様々な形式の事前定義済みオプションから選択できます。

## 使用方法 {#usage}

コアコンポーネントのフォームオプションコンポーネントを使用すれば、様々な形式で提供される各種オプションを送信できます。このコンポーネントは、[フォームコンテナコンポーネント](form-container-v1.md)と共に使用するためのものです。

オプションの表示形式、ラベル、個々のオプションは、コンテンツ編集者が[設定ダイアログ](#configure-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 に付属しているコアコンポーネントのリリース 1.0.0 で最初に導入されたフォームオプションコンポーネント v1 について説明します。

フォームオプションコンポーネント v1 の互換性を次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 互換性あり | 互換性あり |
| v1 | 互換性あり | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、フォームオプションコンポーネント v1 について説明します。
>
>フォームオプションコンポーネントの現在のバージョンについて詳しくは、[フォームオプションコンポーネント](/help/components/forms/form-options.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retail](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html) から取得したサンプルです。

### スクリーンショット {#screenshot}

![](/help/assets/chlimage_1-89.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="cmp cmp-options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="form-group checkbox">
        <legend>What is your favorite type of toast?</legend>
        
        <div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="dry">
              Plain dry toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="french">
              French toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="texas">
              Texas toast
            </label>
        </div>

    </fieldset>
    
</div>
    
</form></div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "options": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/options",
                  "name": "toastTypes",
                  "jcr:title": "What is your favorite type of toast?",
                  "source": "local",
                  "type": "checkbox"
                }
              },
              ":itemsOrder": [
                "options"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](/help/versions.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、表示するオプションのタイプ、ラベル、使用可能なオプションをコンテンツ作成者が定義できます。

![](/help/assets/chlimage_1-90.png)

* **タイプ** - オプションの表示方法

   * **チェックボックス**
   * **ラジオボタン**
   * **ドロップダウン**
   * **複数選択ドロップダウン**

* **タイトル** - オプションのラベルとして表示されるタイトル
* **名前** - フィールドの名前（フォームデータと共に送信されます）
* **ソース** - オプションの定義場所

   * **ローカル** - コンポーネント内に定義
      * 値を追加するには「**追加**」ボタンを、値を削除するには「**削除**」を、それぞれタップまたはクリックします。
      * **値** - フォームの送信時にそのオプションが選択されている場合に保存された値
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

フォームオプションコンポーネントにはデザインダイアログはありません。

## 技術的詳細 {#technical-details}

フォームの非表示コンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options) を参照してください。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。
