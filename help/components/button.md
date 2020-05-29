---
title: ボタンコンポーネント
description: コアコンポーネントのボタンコンポーネントを使用すると、ボタンを作成および表示することができます。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 79%

---


# ボタンコンポーネント{#button-component}

コアコンポーネントのボタンコンポーネントを使用すると、ページ上にボタンアイテムを設定および表示することができます。

## 使用方法 {#usage}

コアコンポーネントのボタンコンポーネントを使用すると、ページにボタンを含めることができます。

* ボタンのプロパティは、[設定ダイアログ](#configure-dialog)で選択できます。
* ボタンコンポーネントのスタイルは、[デザインダイアログ](#design-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、ボタンコンポーネントの現在のバージョン（2019 年 6 月にコアコンポーネントのリリース 2.5.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

ボタンコンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_button_jp)を参照してください。

## 技術的詳細 {#technical-details}

ボタンコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_button_v1_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、ボタンそのものと、ページの訪問者に対するボタンの動作および表示をコンテンツ作成者が定義できます。

### 「プロパティ」タブ {#properties-tab}

![ボタンコンポーネントの編集ダイアログの「プロパティ」タブ](/help/assets/button-edit-properties.png)

* **テキスト** - ボタンに表示するテキスト
* **リンク** - AEM 内のコンテンツページ、外部リソース、アンカーへのリンク
   * **選択ダイアログ**&#x200B;を使用して、AEM 内のパスを選択します。
* **アイコン** - ボタンにアイコンを表示するための識別子
* **ID** — このオプションを使用すると、HTML内および [データレイヤー内のコンポーネントの固有な識別子を制御できます](/help/developing/data-layer/overview.md)。
   * 空白の場合、一意のIDが自動的に生成され、結果のページを調べることで確認できます。
   * IDを指定する場合は、一意性を確認するのは作成者の責任です。
   * IDの変更は、CSS、JS、およびデータレイヤーの追跡に影響を与える可能性があります。

### 「アクセシビリティ」タブ {#accessibility-tab}

![ボタンコンポーネントの編集ダイアログの「アクセシビリティ」タブ](/help/assets/button-edit-accessibility.png)

「**アクセシビリティ**」タブでは、コンポーネントの「[ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)」ラベルの値を設定できます。

* **ラベル** - コンポーネントの ARIA ラベル属性の値

## デザインダイアログ{#design-dialog}

### 「スタイル」タブ {#styles-tab}

画像コンポーネントは AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートします。
