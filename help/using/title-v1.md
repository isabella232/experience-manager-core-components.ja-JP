---
title: タイトルコンポーネント（v1）
seo-title: タイトルコンポーネント（v1）
description: コアコンポーネントのタイトルコンポーネントは、インプレース編集機能を備えたセクション見出しコンポーネントです。
seo-description: コアコンポーネントのタイトルコンポーネントは、インプレース編集機能を備えたセクション見出しコンポーネントです。
uuid: 5c4d276c-f0be-4122-a15e-3f7443d8b209
content-type: reference
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: a028ebef-2957-410c-9bab-a7040c350f2f
index: n
translation-type: ht
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# タイトルコンポーネント（v1）{#title-component-v}

コアコンポーネントのタイトルコンポーネントは、インプレース編集機能を備えたセクション見出しコンポーネントです。

## 使用方法 {#usage}

タイトルコンポーネントは、コンテンツのセクションのタイトルまたは見出しとして使用するためのものです。

使用可能な見出しレベルは、[デザインダイアログ](title-v1.md#main-pars_title_1995166862)でテンプレート作成者が定義できます。コンテンツ編集者は、[編集ダイアログ](title-v1.md#main-pars_title)で、使用可能な見出しレベルから選択できます。利便性の向上のため、見出しテキストの簡単なインプレース編集も可能です。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 に付属しているコアコンポーネントのリリース 1.0.0 で最初に導入されたタイトルコンポーネント v1 について説明します。

タイトルコンポーネント v1 の互換性を次の表に示します。

| AEM のバージョン | タイトルコンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、タイトルコンポーネント v1 について説明します。
>
>タイトルコンポーネントの現在のバージョンについて詳しくは、[タイトルコンポーネント](title.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は、[We.Retail](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html) から引用したサンプルです。

### スクリーンショット {#screenshot}

![](assets/chlimage_1-36.png)

### HTML {#html}

```
<div class="cmp cmp-title aem-GridColumn aem-GridColumn--default--12">
     <h2>Welcome! This is our finest equipment!</h2>
</div>
```

### JSON {#json}

```
"title": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/title",
              "jcr:title": "Welcome! This is our finest equipment!",
              "type": "h2"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](versions.md#main-pars_title_236368006)を参照してください。

## 編集ダイアログ{#edit-dialog}

編集ダイアログでは、コンテンツ作成者がタイトルテキストを定義したり、見出しレベルを選択したりできます。

>[!NOTE]
>
>タイトルの値を空にすると、ページタイトルが表示されます。

![](assets/chlimage_1-91.png)

インプレースエディターを使用して、タイトルコンポーネントのテキストを編集することもできます。

![](assets/chlimage_1-37.png)

## デザインダイアログ{#design-dialog}

デザインダイアログでは、コンテンツ作成者によって使用されたときのタイトルコンポーネントのデフォルト見出しレベルをテンプレート作成者が定義できます。

![](assets/chlimage_1-92.png)

## 技術的詳細 {#technical-details}

タイトルコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title) を参照してください。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。
