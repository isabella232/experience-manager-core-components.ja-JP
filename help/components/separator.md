---
title: 区切り文字コンポーネント
description: 区切り文字コンポーネントは、ページ上のコンポーネント間に区切りを作成します
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 74%

---


# 区切り文字コンポーネント {#separator-component}

コアコンポーネントの区切り文字コンポーネントは、コンテンツを区切るための横罫線を表示します。

## 使用方法 {#usage}

区切り文字コンポーネントを使用すれば、コンテンツ作成者はコンテンツ間の区切りとして横罫線を手軽に作成して、ページ上の情報をうまく整理できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、区切り文字コンポーネントの現在のバージョン（2019 年 2 月にコアコンポーネントのリリース 2.3.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

## コンポーネント出力のサンプル {#sample-component-output}

区切り文字コンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_separator_jp)を参照してください。

### 技術的詳細 {#technical-details}

区切り文字コンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

![セパレータコンポーネントの編集ダイアログ](/help/assets/separator-edit.png)

* **ID** — このオプションを使用すると、HTML内および [データレイヤー内のコンポーネントの固有な識別子を制御できます](/help/developing/data-layer/overview.md)。
   * 空白の場合、一意のIDが自動的に生成され、結果のページを調べることで確認できます。
   * IDを指定する場合は、一意性を確認するのは作成者の責任です。
   * IDの変更は、CSS、JS、およびデータレイヤーの追跡に影響を与える可能性があります。

## デザインダイアログ{#design-dialog}

デザインダイアログでは、区切り文字コンポーネントに適用するスタイルをテンプレート作成者が定義できます。

### 「スタイル」タブ {#styles-tab}

区切り文字コンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
