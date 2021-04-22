---
title: パンくずコンポーネント（v1）
description: コアコンポーネントのパンくずコンポーネントはナビゲーションコンポーネントです。コンテンツ階層におけるページの場所に基づいてリンクのパンくずリストを作成します。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
translation-type: ht
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: ht
source-wordcount: '546'
ht-degree: 100%

---

# パンくずコンポーネント（v1）{#breadcrumb-component-v}

コアコンポーネントのパンくずコンポーネントはナビゲーションコンポーネントです。コンテンツ階層におけるページの場所に基づいてリンクのパンくずリストを作成します。

## 使用方法 {#usage}

パンくずコンポーネントには、サイト階層における現在のページの位置が表示され、ページの訪問者は現在の場所からページ階層内を移動することができます。多くの場合、パンくずコンポーネントはページヘッダーやフッターに統合されています。

デフォルトのナビゲーションレベルや、現在のページまたは非表示のページを表示する機能などの使用可能なオプションは、テンプレート作成者が[デザインダイアログ](#design-dialog)で定義できます。次に、非表示のページを表示するかどうかやコンポーネントの実際のナビゲーションレベルをコンテンツ編集者が[編集ダイアログ](#edit-dialog)で選択できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 に付属しているコアコンポーネントのリリース 1.0.0 で最初に導入されたパンくずコンポーネント v1 について説明します。

パンくずコンポーネント v1 の互換性を次の表に示します。

| AEM のバージョン | パンくずコンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、パンくずコンポーネント v1 について説明します。
>パンくずコンポーネントの現在のバージョンについて詳しくは、[パンくずコンポーネント](/help/components/breadcrumb.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retail](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html) から取得したサンプルです。

### スクリーンショット {#screenshot}

![](/help/assets/chlimage_1-33.png)

### HTML {#html}

```
<div class="cmp cmp-breadcrumb aem-GridColumn aem-GridColumn--default--12">

<ol class="breadcrumb">
    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us.html">
            United States
        </a>
    </li>

    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us/en.html">
            English
        </a>
    </li>

    <li class="breadcrumb-item active">
        
            Experience
        
    </li>
</ol>
 
</div>
```

### JSON {#json}

```
"breadcrumb": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/breadcrumb"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](/help/versions.md)を参照してください。

## 編集ダイアログ {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がパンくずリスト内の非表示ページとアクティブなページ、および表示する階層の深さを無効化できます。

![](/help/assets/chlimage_1-34.png)

* **開始するナビゲーションレベル** - 階層内でパンくずコンポーネントが現在のページへの移動を開始する位置。例えば、We.Retail では次のようになります。

   * 「1」の場合は `/content/we-retail` で開始
   * 「2」の場合は `/content/we-retail/<country>` で開始

* **非表示のページを表示** - パンくずリストで非表示とマークされているページを表示します（デフォルトでは表示されません）
* **現在のページを非表示** - パンくずリストの現在のページを非表示にします（デフォルトでは表示されます）

## デザインダイアログ {#design-dialog}

デザインダイアログでは、テンプレート作成者が、パンくずリスト内の非表示ページとアクティブページおよび表示する階層の深さを無効化するオプションのデフォルト値を定義できます。

![](/help/assets/chlimage_1-35.png)

* **開始するナビゲーションレベル** - パンくずコンポーネントをページに追加したときに階層内でパンくずコンポーネントが現在のページへの移動を開始する位置のデフォルト値を定義します。
* **非表示のページを表示** - パンくずコンポーネントをページに追加したときに使用される「**非表示のページを表示**」オプションのデフォルト値を定義します。

   * 作成者用のオプションは有効または無効にはなりません。デフォルト値のみ設定されます。

* **現在のページを非表示** - パンくずコンポーネントをページに追加したときに使用される「**現在のページを非表示**」オプションのデフォルト値を定義します。

   * 作成者用のオプションは有効または無効にはなりません。デフォルト値のみ設定されます。

## 技術的詳細 {#technical-details}

パンくずコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb) を参照してください。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。
