---
title: プログレスバーコンポーネント
description: プログレスバーコンポーネントは、目標に向かう進行状況を視覚的に表します
translation-type: tm+mt
source-git-commit: cba1d898d7789af7f4045ef9aa052b4da6a6b33a
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 97%

---


# プログレスバーコンポーネント {#progress-bar-component}

コアコンポーネントのプログレスバーコンポーネントは、目標に向かう進行状況を視覚的に表します

## 使用方法 {#usage}

プログレスバーコンポーネントでは、コンテンツ作成者は完了のパーセンテージを定義することでプログレスバーを簡単に作成でき、目標に向かう進行状況を直観的に表示できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、プログレスバーコンポーネントの現在のバージョン（2020 年 5 月にコアコンポーネントのリリース 2.9.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

## コンポーネント出力のサンプル {#sample-component-output}

プログレスバーコンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_progressbar)を参照してください。

### 技術的詳細 {#technical-details}

プログレスバーコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

![プログレスバーコンポーネントの編集ダイアログ](/help/assets/progress-bar-edit.png)

* **完了** - 進行状況をパーセンテージで示します。
* **ID** - このオプションを使用すると、HTML 内および [データレイヤー](/help/developing/data-layer/overview.md)内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

## デザインダイアログ{#design-dialog}

プログレスバーダイアログでは、区切り文字コンポーネントに適用するスタイルをテンプレート作成者が定義できます。

### 「スタイル」タブ {#styles-tab}

プログレスバーコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
