---
title: メールボタンコンポーネント
description: メールボタンコンポーネントを使用すると、コンテンツ内のボタン項目を設定および表示できます。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 100%

---


# メールボタンコンポーネント {#email-button-component}

メールボタンコンポーネントを使用すると、コンテンツ内のボタン項目を設定および表示できます。

## 使用方法 {#usage}

メールボタンコンポーネントを使用すると、コンテンツリーダーがクリック可能なボタンをコンテンツに含め、追加のリソースにリンクできます。

* ボタンのプロパティは、[設定ダイアログ](#configure-dialog)で選択できます。
* メールボタンコンポーネントのスタイルは、[デザインダイアログ](#design-dialog)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、メールボタンコンポーネントの現在のバージョン（2022年10月にメールコアコンポーネントのリリース x で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[メールコアコンポーネントのバージョン](/help/email/versions.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

メールボタンコンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_email_button)を参照してください。

## 技術的詳細 {#technical-details}

メールボタンコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_email_button_v1) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、ボタンと、その動作およびコンテンツの読者に対する表示をコンテンツ作成者が定義できます。

### 「プロパティ」タブ {#properties-tab}

![ボタンコンポーネントの編集ダイアログの「プロパティ」タブ](/help/email/assets/email-button-edit-properties.png)

* **テキスト** - ボタンに表示するテキスト
   * Campaign アイコンをクリックして、[Adobe Campaign 変数を選択](/help/email/campaign-variables.md)ダイアログを開き、Adobe Campaign 内の動的コンテンツを挿入できます。
* **リンク** - AEM 内のコンテンツページ、外部リソース、アンカーへのリンク
   * **選択ダイアログ**&#x200B;を使用して、AEM 内のパスを選択します。
   * Campaign アイコンをクリックして、[Adobe Campaign 変数を選択](/help/email/campaign-variables.md)ダイアログを開き、Adobe Campaign 内の動的コンテンツを挿入できます。
* **アイコン** - ボタンにアイコンを表示するための識別子
* **ID** - このオプションを使用すると、HTML 内のコンポーネントの一意の ID を制御できます。
   * これを空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS に影響を与える可能性があります。
* **リンクを新しいタブで開く** - オンにすると、リンクは新しいブラウザータブで開きます。

### 「アクセシビリティ」タブ {#accessibility-tab}

![ボタンコンポーネントの編集ダイアログの「アクセシビリティ」タブ](/help/email/assets/email-button-edit-accessibility.png)

「**アクセシビリティ**」タブでは、コンポーネントの「[ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)」ラベルの値を設定できます。

* **ラベル** - コンポーネントの ARIA ラベル属性の値

### 「スタイル」タブ {#styles-tab-edit}

メールボタンコンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

ドロップダウンを使用して、コンポーネントに適用するスタイルを選択します。編集ダイアログでの選択項目は、コンポーネントツールバーから選択した項目と同じ効果があります。

このタブを使用するには、[デザインダイアログ](#design-dialog)でこのコンポーネントのスタイルを設定する必要があります。

## デザインダイアログ {#design-dialog}

### 「スタイル」タブ {#styles-tab}

メールボタンコンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
