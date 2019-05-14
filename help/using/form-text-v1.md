---
title: フォームテキストコンポーネント（v1）
seo-title: フォームテキストコンポーネント（v1）
description: 'null'
seo-description: Core Component Form Textコンポーネントを使用すると、フォームテキストのエントリを送信できます。
uuid: 30123aba-57a8-4ed4-93cb-6a3d2edff9a7
content-type: リファレンス
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: bd4e9930-4d81-49ae- a3d1-9a8740418ae
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# フォームテキストコンポーネント（v1）{#form-text-component-v}

Core Component Form Textコンポーネントを使用すると、フォームテキストのエントリを送信できます。

## 使用方法 {#usage}

Form Text Componentを使用すると、様々なタイプのテキストを送信でき、 [フォームコンテナコンポーネントとともに使用](form-container.md)することができます。

テキスト検証、ラベルおよびヘルプメッセージのタイプは [、設定ダイアログのコンテンツエディターで定義](form-text-v1.md#main-pars_title)できます。

## バージョンと互換性 {#version-and-compatibility}

本書では、元々、コアコンポーネントのリリース1.0.0とAEM6.3で導入された、フォームテキストコンポーネントのv1について説明します。

次の表に、Form Text Componentのv1との互換性を示します。

| AEM のバージョン | フォームテキストコンポーネントv1 |
|--- |--- |
| 6.3 | 互換性 |
| 6.4 | 互換性 |

>[!CAUTION]
>
>本書では、フォームテキストコンポーネントのv1について説明します。
>
>フォームテキストコンポーネントの現在のバージョンの詳細については [、&quot;Form Text Component](form-text.md) 」ドキュメントを参照してください。

## サンプルコンポーネントの出力 {#sample-component-output}

以下は、We. Retailから [取得されたサンプル](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)です。

### スクリーンショット {#screenshot}

![](assets/chlimage_1-22.png)

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
>コアコンポーネントからのJSONエクスポートには、コアコンポーネントのリリース1.1.0が必要です。詳しくは [、コアコンポーネントv1](versions.md#main-pars_title_236368006) の互換性情報を参照してください。

## ダイアログの設定 {#configure-dialog}

設定ダイアログでは、コンテンツ作成者が入力するテキストの種類とデフォルト値およびラベルを定義できます。

### メイン {#main}

![](assets/chlimage_1-23.png)

* **制約** -入力するテキストの種類

   * **テキスト**
   * **テキスト領域**
   * **電子メール**
   * **電話番号**
   * 日付****
   * **番号**
   * **パスワード**

* **テキスト行** -テキスト領域に表示する行数（ **制約** がテキスト領域に **設定されている場合のみ表示**）

* **ラベル** -フィールドに表示するラベル
* **ラベルが表示されないようにする** -ラベルがアクセシビリティの目的でのみ必要で、フィールドに関する追加情報を表示しない場合は必須
* **要素名** -フォームデータと共に送信されるフィールドの名前
* **値** -フィールドに事前入力されているデフォルト値

### バージョン情報 {#about}

![](assets/chlimage_1-24.png)

* **ヘルプメッセージ** -フィールドに入力できるユーザーへのヒント
* **ヘルプメッセージをプレースホルダー** として表示-空であり、フォーカスがないときにフォーム入力内にヘルプメッセージを表示するには

### 制限事項 {#constraints}

![](assets/chlimage_1-25.png)

* **制約メッセージ**

   * 値が適切な型でない場合に、フォーム送信時にツールチップとして表示されるメッセージ
   * **テキスト** および **テキスト領域** 制約タイプに対しては表示されません

* **必須** -選択した場合、ユーザーがフォームを送信する前に値を入力する必要がある
* **読み取り専用** にする-選択した場合、フィールドの値を変更できません

## デザインダイアログ {#design-dialog}

フォームテキストコンポーネントのデザインダイアログはありません。

## 技術的詳細 {#technical-details}

フォームテキストコンポーネント [に関する最新の技術ドキュメントは、GitHubで入手](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)できます。

コアコンポーネントプロジェクト全体をGitHubからダウンロードできます。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。
