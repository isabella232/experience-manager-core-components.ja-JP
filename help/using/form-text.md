---
title: フォームテキストコンポーネント
seo-title: フォームテキストコンポーネント
description: 'null'
seo-description: コアコンポーネントのフォームテキストコンポーネントを使用すれば、送信するフォームテキストを入力できます。
uuid: f2418d55-0b59-4c7c-a541-d12dda4db4cf
contentOwner: ユーザー
content-type: reference
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 3a970c4b-806b-4a0a-b6b8-b3dca4e9f136
disttype: dist5
gnavtheme: light
groupsectionnavitems: ' no'
hidemerchandisingbar: inherit
hidepromocomponent: inherit
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# フォームテキストコンポーネント{#form-text-component}

コアコンポーネントのフォームテキストコンポーネントを使用すれば、送信するフォームテキストを入力できます。

## 使用方法 {#usage}

フォームテキストコンポーネントを使用すれば、各種テキストを送信できます。このコンポーネントは、[フォームコンテナコンポーネント](form-container.md)と共に使用するためのものです。テキスト検証のタイプ、ラベル、ヘルプメッセージは、コンテンツ編集者が[設定ダイアログ](#configure-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、フォームテキストコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v2）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性あり | 互換性あり | 互換性あり |
| [v1](form-text-v1.md) | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retailのサンプルです](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### スクリーンショット {#screenshot}

![](assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="text aem-GridColumn aem-GridColumn--default--12">
   <div class="cmp-form-text">
      <label for="form-text-2146967">How many pieces of toast would you like?
      </label>
   <input class="cmp-form-text__text" type="number" id="form-text-2146967" name="pieces">
   </div>
</div>
```

### JSON {#json}

```
"text":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "id":"form-text-2146967",
                     "title":"How many pieces of toast would you like?",
                     "name":"pieces",
                     "value":"",
                     "helpMessage":"",
                     "type":"number",
                     "readOnly":false,
                     "required":false,
                     "requiredMessage":"",
                     "constraintMessage":"",
                     "rows":2,
                     "defaultValue":"",
                     ":type":"core/wcm/components/form/text/v2/text"
                  }
```

### 技術的詳細 {#technical-details}

フォームテキストコンポーネントに関する最新の技術ドキュメ [ントは、GitHubで入手できます](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text)。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、入力するテキストの種類とデフォルト値およびラベルをコンテンツ作成者が定義できます。

### 「メイン」タブ {#main-tab}

![](assets/chlimage_1-23.png)

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
* **ラベルを非表示** - ラベルがアクセシビリティのためにのみ必要で、フィールドに関するその他の視覚的情報には影響しない場合に必要です
* **要素名** - フォームデータと共に送信されるフィールドの名前
* **値** - フィールドに事前入力されるデフォルト値

### 「情報」タブ {#about-tab}

![](assets/chlimage_1-24.png)

* **ヘルプメッセージ** - フィールドに入力できる内容をユーザーに伝えるヒント
* **ヘルプメッセージをプレースホルダーとして表示** - フォーム入力が空でフォーカスされていない場合、フォーム入力内にヘルプメッセージを表示する

### 「制約」タブ{#constraints-tab}

![](assets/chlimage_1-25.png)

* **制約メッセージ**
   * 値が適切な型でない場合に、フォーム送信時にツールチップとして表示されるメッセージ
   * 制約タイプが&#x200B;**テキスト**&#x200B;および&#x200B;**テキスト領域**&#x200B;の場合は表示されません
* **必須** - 選択した場合、ユーザーはフォームを送信する前に値に入力する必要があります
* **読み取り専用にする** - 選択した場合、ユーザーはフィールドの値を変更できません

## デザインダイアログ{#design-dialog}

フォームテキストコンポーネントにはデザインダイアログはありません。