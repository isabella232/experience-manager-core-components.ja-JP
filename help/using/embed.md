---
title: Embed Component
seo-title: Embed Component
description: The Embed Component enables embedding external content in an AEM content page.
seo-description: The Embed Component enables embedding external content in an AEM content page.
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: d748bf211ec36d12cac016ca9bf707f24db1ce48

---


# Embed Component{#embed-component}

The Core Components Embed Component allows embedding external content in an AEM content page.

## 使用方法 {#usage}

The Core Component Embed Component allows the content author to define selected external content to be embedded within an AEM content page. In addition, there is an option to define free-form HTML to be embedded as well.

* The component's properties can be defined in the [configure dialog](#configure-dialog).
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

The latest technical documentation about the Embed Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

The configure dialog allows the content author to define the external resource to be embedded on the page. First choose which type of resource should be embedded: URL, Embeddable, or HTML.************

### URL {#url}

The simplest embed is the URL. Simply paste the URL of the resource you wish to embed in the URL field. **** The component will attempt to access the resource and if it can be rendered by one of the processors, it will display a confirmation message below the URL field. ****&#x200B;そうでない場合は、フィールドにエラーのマークが付けられます。

埋め込みコンポーネントは、次の種類のリソースに対応したプロセッサー付きで出荷されます。

* Facebook投稿、Instagram [](https://oembed.com/) 、SoundCloud、Twitter、YouTubeなど、oEmbed標準に準拠するリソース
* Pinterest

開発者は、埋め込みコンポーネントの開発者ドキ [ュメントに従って、URLプロセッサーを追加できます。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.08.29.png)

### 埋め込み可能 {#embeddable}

埋め込み可能な変数を使用すると、埋め込みリソースをよりカスタマイズでき、パラメータ化したり、追加情報を含めたりできます。 作成者は、事前設定済みの信頼できる埋め込みデータから選択でき、コンポーネントにはYoutubeが埋め込まれ、すぐに使用できます。

「埋め込 **み可能** 」フィールドは、使用するプロセッサの種類を定義します。 埋め込み可能なYouTubeの場合は、次を定義できます。

* **ビデオID** — 埋め込むリソースのYouTubeからの一意のビデオID。
* **幅** — 埋め込みビデオの幅
* **Height** — 埋め込みビデオの高さ。

その他の埋め込み可能なフィールドも同様で、埋め込みコンポーネントの開発者向けドキ [ュメントに従って開発者が定義することができます。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>埋め込み可能なデータは、デザインダイアログを使用してテンプレ [ートレベルで有効にする](#design-dialog) 、ページの作成者が使用できるようにする必要があります。

### HTML {#html}

埋め込みコンポーネントを使用して、自由形式のHTMLをページに追加できます。

![](assets/screen-shot-2019-09-25-10.20.00.png)

>[!NOTE]
>スクリプトなどの安全でないタグは、入力したHTMLからフィルタされ、結果のページにレンダリングされません。

## デザインダイアログ{#design-dialog}

The design dialog allows the template author to define the options available to the content author who uses the Embed Component and the defaults set when placing the Embed Component.

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **URLを無効にする** — 選択した場合に、コンテ **ンツ作成者のURL** オプションを無効にします。
* **埋め込み可能** — 許可されている埋め込み可 **能なプロセッサーに関係なく、選択時にコンテンツ作成者の「埋め込み可能** 」オプションを無効にします。
* **HTMLを無効にする** — 選択すると、コンテ **ンツ作成者のHTML** オプションが無効になります。
* **Allowed Embeddables** - 「 **Embeddable** 」オプションがアクティブな場合に、コンテンツ作成者が使用できる埋め込み可能なプロセッサーを定義するマルチセレクト。
