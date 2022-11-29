---
title: 電子メールボタンコンポーネント
description: 電子メールボタンコンポーネントを使用すると、コンテンツ内のボタン項目を設定および表示できます。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 38%

---


# 電子メールボタンコンポーネント {#email-button-component}

電子メールボタンコンポーネントを使用すると、コンテンツ内のボタン項目を設定および表示できます。

## 使用方法 {#usage}

電子メールボタンコンポーネントを使用すると、コンテンツリーダーがクリック可能なボタンをコンテンツに含め、追加のリソースにリンクできます。

* ボタンのプロパティは、 [設定ダイアログ。](#configure-dialog)
* 電子メールボタンコンポーネントのスタイルは、 [デザインダイアログ。](#design-dialog)

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、電子メールボタンコンポーネントの現在のバージョン（2022 年 10 月に電子メールコアコンポーネントのリリース x で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、ドキュメントを参照してください。 [コアコンポーネントのバージョンを電子メールで送信します。](/help/email/versions.md)

## コンポーネント出力のサンプル {#sample-component-output}

電子メールボタンコンポーネントを実際に体験し、その設定オプションやHTMLおよび JSON 出力の例を確認するには、 [コンポーネントライブラリ。](https://adobe.com/go/aem_cmp_library_email_button)

## 技術的詳細 {#technical-details}

電子メールボタンコンポーネントに関する最新の技術ドキュメント [は GitHub にあります。](https://adobe.com/go/aem_cmp_tech_email_button_v1)

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメントです。](/help/developing/overview.md)

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、ボタンと、その動作およびコンテンツの読者に対する表示をコンテンツ作成者が定義できます。

### 「プロパティ」タブ {#properties-tab}

![ボタンコンポーネントの編集ダイアログの「プロパティ」タブ](/help/email/assets/email-button-edit-properties.png)

* **テキスト** - ボタンに表示するテキスト
   * キャンペーンアイコンをクリックして、 [Adobe Campaign変数を選択](/help/email/campaign-variables.md) ダイアログを開き、Adobe Campaignから動的コンテンツを挿入するためのダイアログを開きます。
* **リンク** - AEM 内のコンテンツページ、外部リソース、アンカーへのリンク
   * **選択ダイアログ**&#x200B;を使用して、AEM 内のパスを選択します。
   * キャンペーンアイコンをクリックして、 [Adobe Campaign変数を選択](/help/email/campaign-variables.md) ダイアログを開き、Adobe Campaignから動的コンテンツを挿入するためのダイアログを開きます。
* **アイコン** - ボタンにアイコンを表示するための識別子
* **ID**  — このオプションを使用すると、HTML内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成され、結果のコンテンツを調べることで見つかります。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS に影響を与える可能性があります。
* **リンクを新しいタブで開く** - オンにすると、リンクは新しいブラウザータブで開きます。

### 「アクセシビリティ」タブ {#accessibility-tab}

![ボタンコンポーネントの編集ダイアログの「アクセシビリティ」タブ](/help/email/assets/email-button-edit-accessibility.png)

「**アクセシビリティ**」タブでは、コンポーネントの「[ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)」ラベルの値を設定できます。

* **ラベル** - コンポーネントの ARIA ラベル属性の値

### 「スタイル」タブ {#styles-tab-edit}

電子メールボタンコンポーネントは、AEM [スタイルシステム。](/help/get-started/authoring.md#component-styling).

ドロップダウンを使用して、コンポーネントに適用するスタイルを選択します。編集ダイアログでの選択項目は、コンポーネントツールバーから選択した項目と同じ効果があります。

スタイルは、内のこのコンポーネントに対して設定する必要があります [デザインダイアログ](#design-dialog) 」をクリックします。

## デザインダイアログ {#design-dialog}

### 「スタイル」タブ {#styles-tab}

電子メールボタンコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling).
