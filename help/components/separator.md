---
title: 区切り文字コンポーネント
description: 区切り文字コンポーネントは、ページ上のコンポーネント間に区切りを作成します
role: Architect, Developer, Admin, User
exl-id: 79f19368-67fa-4864-93f7-2aa801d13fdb
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 98%

---

# 区切り文字コンポーネント {#separator-component}

コアコンポーネントの区切り文字コンポーネントは、コンテンツを区切るための横罫線を表示します。

## 使用方法 {#usage}

区切り文字コンポーネントを使用すれば、コンテンツ間の区切りとして横罫線を手軽に作成して、ページ上の情報をうまく整理できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、区切り文字コンポーネントの現在のバージョン（2019 年 2 月にコアコンポーネントのリリース 2.3.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 互換性あり<br>[リリース2.17.4](/help/versions.md) および以前 | 互換性あり | 互換性あり |

## コンポーネント出力のサンプル {#sample-component-output}

区切り文字コンポーネントを体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_separator_jp)を参照してください。

### 技術的詳細 {#technical-details}

区切り文字コンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

![区切り文字コンポーネントの編集ダイアログ](/help/assets/separator-edit.png)

* **ID** - このオプションを使用すると、HTML 内および [データレイヤー](/help/developing/data-layer/overview.md)内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

## デザインダイアログ {#design-dialog}

デザインダイアログでは、区切り文字コンポーネントに適用するスタイルをテンプレート作成者が定義できます。

### 「スタイル」タブ {#styles-tab}

区切り文字コンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
