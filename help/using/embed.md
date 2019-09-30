---
title: 埋め込みコンポーネント
seo-title: 埋め込みコンポーネント
description: 埋め込みコンポーネントを使用すると、AEMコンテンツページに外部コンテンツを埋め込むことができます。
seo-description: 埋め込みコンポーネントを使用すると、AEMコンテンツページに外部コンテンツを埋め込むことができます。
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 6882a0d8247328c403dc11a25ed9d079aefede69

---


# 埋め込みコンポーネント{#embed-component}

コアコンポーネント埋め込みコンポーネントを使用すると、AEMコンテンツページに外部コンテンツを埋め込むことができます。

## 使用方法 {#usage}

コアコンポーネント埋め込みコンポーネントを使用すると、コンテンツ作成者は選択した外部コンテンツを定義してAEMコンテンツページに埋め込むことができます。 さらに、埋め込む自由形式のHTMLを定義するオプションもあります。

* このコンポーネントのプロパティは、[設定ダイアログ](#configure-dialog)で定義できます。
* コンポーネントをページに追加するときのデフォルト設定は、[デザインダイアログ](#design-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

The current version of the Embed Component is v1, which was introduced with release 2.7.0 of the Core Components in September 2019, and is described in this document.

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

To experience the Embed Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/embed.html).

## 技術的詳細 {#technical-details}

埋め込みコンポーネントに関する最新の技術ドキュメ [ントは、GitHubで入手できます](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed)。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、コンテンツ作成者はページに埋め込む外部リソースを定義できます。 まず、埋め込むリソースの種類を選択します。 **URL**、埋め **込み**、 **HTML**。

### URL {#url}

最も単純な埋め込みはURLです。 埋め込むリソースのURLを「 **URL** 」フィールドに貼り付けます。 コンポーネントはリソースにアクセスしようとします。いずれかのプロセッサでレンダリングできる場合は、 **URLフィールドの下に確認メッセージが表示されます** 。 そうでない場合は、フィールドにエラーのマークが付けられます。

埋め込みコンポーネントは、次の種類のリソースに対応したプロセッサー付きで出荷されます。

* Resources that comply with the oEmbed standard including Facebook Post, Instagram, SoundCloud, Twitter, and YouTube[](https://oembed.com/)
* Pinterest

開発者は、埋め込みコンポーネントの開発者ドキ [ュメントに従って、URLプロセッサーを追加できます。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.08.29.png)

### 埋め込み可能 {#embeddable}

埋め込み可能な変数を使用すると、埋め込みリソースをよりカスタマイズでき、パラメータ化したり、追加情報を含めたりできます。 作成者は、事前設定済みの信頼できる埋め込みデータから選択でき、コンポーネントはYoutubeプロセッサーを標準搭載して出荷されます。

The Embeddable field defines the type of processor you want to use. **** In the case of the YouTube processor you can then define:

* **Video ID - The unique video ID from YouTube of the resource you want to embed**
* **Width - The width of the embedded video**
* **Height - The height of the embedded video**

Other processors would offer similar fields and can be defined by a developer by following the developer documentation of the Embed Component.[](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>Embedded processors must be enabled at the template level via the Design Dialog to be avaialble to the page author.[](#design-dialog)

### HTML {#html}

埋め込みコンポーネントを使用して、自由形式のHTMLをページに追加できます。

![](assets/screen-shot-2019-09-25-10.20.00.png)

>[!NOTE]
>Any unsafe tags such as scripts will be filtered from the entered HTML and will not be rendered on the resulting page.

## デザインダイアログ{#design-dialog}

The design dialog allows the template author to define the options available to the content author who uses the Embed Component and the defaults set when placing the Embed Component.

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **Disable URL - Disables the URL option for the content author when selected******
* **Disable Embeddables - Disables the Embeddable option for the content author when selected, regardless of which embeddable processors are allowed.******
* **Disable HTML** - Disables the **HTML** option for the content author when selected.
* **Allowed Embeddables - Multislect that defines which embeddable processors are avaiable to the content author, provided that the Embeddable option is active.******
