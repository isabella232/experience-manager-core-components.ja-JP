---
title: PDFビューアコンポーネント
description: PDF Viewerコンポーネントを使用すると、PDFドキュメントを表示できます。
translation-type: tm+mt
source-git-commit: b08fc5ec49126f7be19b7433a3d71de877d9e442
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 13%

---


# PDFビューアコンポーネント {#pdf-viewer-component}


コアコンポーネントPDFビューアコンポーネントを使用すると、ページにPDFドキュメントを含めることができます。

## 使用方法 {#usage}

コアコンポーネントPDFビューアコンポーネントは、アセットとして保存されたPDFファイルをページに表示するビューアを埋め込みます。

## バージョンと互換性 {#version-and-compatibility}

PDF Viewerコンポーネントの現在のバージョンはv1です。v1は2020年6月にリリース2.10.0のコアコンポーネントで導入され、このドキュメントで説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

To experience the PDF Viewer Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_pdfviewer).

## 技術的詳細 {#technical-details}

The latest technical documentation about the PDF Viewer Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、コンテンツ作成者はビューアを定義し、訪問者がページに出る際にどのように動作し、表示されるかを定義できます。

### Configuration Tab {#configuration-tab}

「設定」タブでは、作成者は表示するPDFを定義できます。 パスは、AEM内のアセットとして定義することも、別のリソースへの絶対パスとして定義することもできます。

![PDFビューアコンポーネントの編集ダイアログの「設定」タブ](/help/assets/pdf-viewer-edit-configuration.png)

### 「カスタマイズ」タブ {#customize-tab}

「Customize」タブでは、作成者はビューアで読者が使用できるオプションと、ビューアの表示方法を定義できます。

![PDF Viewerコンポーネントの編集ダイアログの「カスタマイズ」タブ](/help/assets/pdf-viewer-edit-customize.png)

使用できるオプションの数は、選択した **タイプ** によって異なります。

* [フルウィンドウ](#full-window) — 表示領域は、ブラウザ全体にレンダリングされます。 これは、ストレージおよび生産性向けのアプリケーションに最適です。
* [サイズコンテナ](#sized-container) — 表示領域は、ブラウザー全体に表示されます。 これは、ストレージおよび生産性向けのアプリケーションに最適です。
* [インライン](#in-line) - Webページ内で1行にレンダリングされるすべてのPDFページ。 これは、アプリを読む場合に最適です。

#### 全ウィンドウ {#full-window}

表示領域は、ブラウザ全体でレンダリングされます。 これは、ストレージおよび生産性向けのアプリケーションに最適です。

![PDF Viewerコンポーネントの編集ダイアログの「カスタマイズ」タブの全ウィンドウオプション](/help/assets/pdf-viewer-edit-customize-full.png)

* **初期設定の表示モード** — ビューアが表示されるページに対する表示幅
   * 全体表示
   * 幅に合わせる
* **フルスクリーン** — 有効にすると、ビューアはビューポートの高さ/幅を最大にします。
* **注釈ツール** — 有効な場合、注釈ツールを使用できます。
* **左側のパネル** — 有効にすると、左側のパネルが表示されます。
* **PDFのダウンロード** — 有効にすると、「ダウンロード」ボタンが表示されます。
* **PDFの印刷** — 有効にすると、「印刷」ボタンが表示されます。
* **ページコントロール** — ページコントロールの動作を切り替えます。
   * ドック
   * ドッキング解除

#### サイズコンテナ {#sized-container}

表示領域は、ブラウザ全体でレンダリングされます。 これは、ストレージおよび生産性向けのアプリケーションに最適です。

![PDF Viewerコンポーネントの編集ダイアログの「タブサイズのコンテナをカスタマイズ」オプション](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **フルスクリーン** — 有効にすると、ビューアはビューポートの高さ/幅を最大にします。
* **PDFのダウンロード** — 有効にすると、「ダウンロード」ボタンが表示されます。
* **PDFの印刷** — 有効にすると、「印刷」ボタンが表示されます。
* **ページコントロール** — ページコントロールの動作を切り替えます。
   * ドック
   * ドッキング解除

#### インライン {#in-line}

Webページ内で1行にレンダリングされるすべてのPDFページ。 これは、アプリを読む場合に最適です。

![PDF Viewerコンポーネントの編集ダイアログの「タブサイズのコンテナをカスタマイズ」オプション](/help/assets/pdf-viewer-edit-customize-inline.png)

* **PDFのダウンロード** — 有効にすると、「ダウンロード」ボタンが表示されます。
* **PDFの印刷** — 有効にすると、「印刷」ボタンが表示されます。

## デザインダイアログ{#design-dialog}

PDF Viewerコンポーネントにはデザインダイアログはありません。
