---
title: ボタンコンポーネント
description: コアコンポーネントのボタンコンポーネントを使用すると、ボタンを作成および表示することができます。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

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

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 互換性あり | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

ボタンコンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_button)を参照してください。

## 技術的詳細 {#technical-details}

The latest technical documentation about the Button Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_button_v1).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、ボタンそのものと、ページの訪問者に対するボタンの動作および表示をコンテンツ作成者が定義できます。

### 「プロパティ」タブ {#properties-tab}

![](/help/assets/screen-shot-2019-08-29-12.19.32.png)

* **テキスト** - ボタンに表示するテキスト
* **リンク** - AEM 内のコンテンツページ、外部リソース、アンカーへのリンク
   * **選択ダイアログ**&#x200B;を使用して、AEM 内のパスを選択します
* **アイコン** - ボタンにアイコンを表示するための識別子

### 「アクセシビリティ」タブ {#accessibility-tab}

![](/help/assets/screen-shot-2019-08-29-12.19.43.png)

「**アクセシビリティ**」タブでは、コンポーネントの「[ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)」ラベルの値を設定できます。

* **ラベル** - コンポーネントの ARIA ラベル属性の値

## デザインダイアログ{#design-dialog}

### 「スタイル」タブ {#styles-tab}

画像コンポーネントは AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートします。
