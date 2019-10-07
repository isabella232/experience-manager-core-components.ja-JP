---
title: 埋め込みコンポーネント
seo-title: 埋め込みコンポーネント
description: 埋め込みコンポーネントを使用すると、AEMコンテンツページに外部コンテンツを埋め込むことができます。
seo-description: 埋め込みコンポーネントを使用すると、AEMコンテンツページに外部コンテンツを埋め込むことができます。
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: e4fdefd392281f4f9101b28a15846c922e3a52c1

---


# 埋め込みコンポーネント{#embed-component}

コアコンポーネント埋め込みコンポーネントを使用すると、AEMコンテンツページに外部コンテンツを埋め込むことができます。

## 使用方法 {#usage}

コアコンポーネント埋め込みコンポーネントを使用すると、コンテンツ作成者は選択した外部コンテンツを定義してAEMコンテンツページに埋め込むことができます。 さらに、埋め込む自由形式のHTMLを定義するオプションもあります。

* The component's properties can be defined in the [configure dialog](#configure-dialog).
* コンポーネントをページに追加するときのデフォルト設定は、[デザインダイアログ](#design-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

埋め込みコンポーネントの現在のバージョンはv1で、2019年9月にリリース2.7.0のコアコンポーネントで導入され、このドキュメントで説明されています。

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

設定ダイアログを使用すると、コンテンツ作成者はページに埋め込む外部リソースを定義できます。 まず、埋め込むリソースの種類を選択します。

* [URL](#url)
* [埋め込み可能](#embeddable)
* [HTML](#html)

### URL {#url}

最も単純な埋め込みはURLです。 埋め込むリソースのURLを「 **URL** 」フィールドに貼り付けます。 コンポーネントはリソースにアクセスしようとします。いずれかのプロセッサでレンダリングできる場合は、 **URLフィールドの下に確認メッセージが表示されます** 。 そうでない場合は、フィールドにエラーのマークが付けられます。

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

#### セキュリティ {#security}

作成者が入力できるHTMLマークアップは、セキュリティ上の理由からフィルタリングされ、作成者が管理者権限を取得できるなど、クロスサイトスクリプティング攻撃を回避します。

一般に、すべてのスクリプトと `style` 要素、およびすべての属 `on*` 性が `style` 出力から削除されます。

ただし、埋め込みコンポーネントはAEMのグローバルHTML AntiSamiフィルタリングルールセットに従うので、ルールはそれより複雑です。これは、を参照してくださ `/libs/cq/xssprotection/config.xml`い。 これは、必要に応じて開発者がプロジェクト固有の設定に重ねて表示できます。

>[!NOTE]
>AntiSamyルールはオーバーレイによって設定できますが、こ `/libs/cq/xssprotection/config.xml`れらの変更は、埋め込みコアコンポーネントだけでなく、すべてのHTLおよびJSP動作に影響を与えます。

## デザインダイアログ{#design-dialog}

デザインダイアログを使用すると、テンプレート作成者は、埋め込みコンポーネントを使用するコンテンツ作成者が使用できるオプションを定義でき、埋め込みコンポーネントを配置する際に設定されるデフォルトを定義できます。

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **URLを無効にする** — 選択した場合に、コンテ **ンツ作成者のURL** オプションを無効にします。
* **埋め込み可能** — 許可されている埋め込み可 **能なプロセッサーに関係なく、選択時にコンテンツ作成者の「埋め込み可能** 」オプションを無効にします。
* **HTMLを無効にする** — 選択すると、コンテ **ンツ作成者のHTML** オプションが無効になります。
* **Allowed Embeddables** - 「 **Embeddable** 」オプションがアクティブな場合に、コンテンツ作成者が使用できる埋め込み可能なプロセッサーを定義するマルチセレクト。
