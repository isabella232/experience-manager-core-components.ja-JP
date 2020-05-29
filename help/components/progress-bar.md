---
title: プログレスバーコンポーネント
description: プログレスバーコンポーネントは、目標に向かう進行状況を視覚的に表します
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 22%

---


# プログレスバーコンポーネント {#progress-bar-component}

コアコンポーネントプログレスバーコンポーネントは、目標に向かう進行状況を視覚的に表します。

## 使用方法 {#usage}

プログレスバーコンポーネントを使用すると、コンテンツ作成者は完了の割合を定義することでプログレスバーを簡単に作成でき、目標に向かって直感的に進行状況を表示できます。

## バージョンと互換性 {#version-and-compatibility}

プログレスバーコンポーネントの現在のバージョンはv1です。2020年5月にリリース2.9.0のコアコンポーネントで導入され、このドキュメントで説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

## コンポーネント出力のサンプル {#sample-component-output}

To experience the Progress Bar Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_progress).

### 技術的詳細 {#technical-details}

The latest technical documentation about the Progress Bar Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

![プログレスバーコンポーネントの編集ダイアログ](/help/assets/progress-bar-edit.png)

* **完了** — 進行状況を割合で示します。
* **ID** — このオプションを使用すると、HTML内および [データレイヤー内のコンポーネントの固有な識別子を制御できます](/help/developing/data-layer/overview.md)。
   * 空白の場合、一意のIDが自動的に生成され、結果のページを調べることで確認できます。
   * IDを指定する場合は、一意性を確認するのは作成者の責任です。
   * IDの変更は、CSS、JS、およびデータレイヤーの追跡に影響を与える可能性があります。

## デザインダイアログ{#design-dialog}

[デザイン]ダイアログでは、テンプレート作成者が[プログレスバー]コンポーネントに適用するスタイルを定義できます。

### 「スタイル」タブ {#styles-tab}

The Progress Bar Component supports the AEM [Style System](/help/get-started/authoring.md#component-styling).
