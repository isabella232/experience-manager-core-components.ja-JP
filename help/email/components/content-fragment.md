---
title: メールコンテンツフラグメントコンポーネント
description: 電子メールコンテンツフラグメントコンポーネントを使用すると、コンテンツフラグメントをコンテンツに表示できます。
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 28%

---


# メールコンテンツフラグメントコンポーネント {#email-content-fragment-component}

電子メールコンテンツフラグメントコンポーネントを使用すると、 [コンテンツフラグメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=ja) 」と入力します。

## 使用方法 {#usage}

メールコンテンツフラグメントコンポーネントを使用すれば、 [コンテンツフラグメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) を電子メールコンテンツに追加します。 コンテンツフラグメントは、一元的に作成して容易に再利用できるマルチチャネル構造コンテンツです。

* フラグメントとそのプロパティは、 [設定ダイアログ。](#configure-dialog)
* 特定の画像やグリッドを処理するリソースタイプは、 [デザインダイアログ。](#design-dialog)
* 編集オプションを選択すると、選択したフラグメントが [コンテンツフラグメントエディター](#edit-dialog) 電子メールコアコンポーネントで使用するようにカスタマイズされています。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、電子メールコンテンツフラグメントコンポーネントの現在のバージョン（2022 年 10 月に電子メールコアコンポーネントのリリース X で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | 互換性あり |

電子メールコアコンポーネントのバージョンとリリースについて詳しくは、ドキュメントを参照してください。 [コアコンポーネントのバージョンを電子メールで送信します。](/help/email/versions.md)

## コンポーネント出力のサンプル {#sample-component-output}

電子メールコンテンツフラグメントコンポーネントを実際に体験し、その設定オプションやHTMLおよび JSON 出力の例を確認するには、 [コンポーネントライブラリ。](https://adobe.com/go/aem_cmp_library_email_cf)

## 技術的詳細 {#technical-details}

電子メールコンテンツフラグメントコンポーネントに関する最新の技術ドキュメント [は GitHub にあります。](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメントです。](/help/developing/overview.md)

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツフラグメントと、そのフラグメントを組み込む要素をコンテンツ作成者が定義できます。

### 「プロパティ」タブ {#properties-tab}

![メールコンテンツフラグメントコンポーネント](/help/email/assets/email-content-fragment-edit-properties.png)

* **コンテンツフラグメント**

   * 目的のコンテンツフラグメントへのパス
   * **選択ダイアログ**&#x200B;を使用して、フラグメントを見つけることができます。

* **ディスプレイモード**
   * **単一のテキスト要素** - 複数行テキスト要素を 1 つ選択でき、段落コントロールオプションを有効にします。
* **バリエーション** - 使用するコンテンツフラグメントのバリエーション（デフォルトは&#x200B;**マスター**）

* **ID**  — このオプションを使用すると、HTML内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成され、結果のコンテンツを調べることで見つかります。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS に影響を与える可能性があります。

### 「段落制御」タブ {#paragraph-control-tab}

![メールコンテンツフラグメントコンポーネント](/help/assets/content-fragment-edit-paragraph.png)

* **段落** - すべての段落、または特定の範囲を選択できます。
   * **すべて** - すべての段落を表示します
   * **範囲**
      * 表示する段落の範囲をセミコロンで区切って指定します
      * 例： `1;3-5;7;9-*` 第 1 段落、第 3 段落から第 5 段落まで、第 7 段落、第 9 段落から最終段落までを含める
* **見出しを独自の段落として処理**

## 編集ダイアログ {#edit-dialog}

電子メールコンテンツフラグメントコンポーネントを使用してコンテンツフラグメントを設定すると、コンテンツエディターでコンポーネントを選択すると、 **編集** オプション。

![メールコンテンツフラグメントコンポーネントのツールバー](/help/email/assets/email-content-fragment-edit-toolbar.png)

をタップまたはクリックして、 **編集** ボタンをクリックすると、コンテンツフラグメントエディターが開きます。 コンテンツフラグメントエディターが拡張され、 **Adobe Campaign変数を選択** を使用して、Adobe Campaign変数をコンテンツフラグメントに挿入します。

![E メール用のコンテンツフラグメントエディター](/help/email/assets/email-content-fragment-editor.png)

コンテンツフラグメントの編集とオーサリングについて詳しくは、 [フラグメントコンテンツのオーサリング](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## デザインダイアログ {#design-dialog}

メールコンテンツフラグメントコンポーネントにコンテンツフラグメントが設定されている場合、コンテンツエディターでコンテンツフラグメントを選択すると、ツールバーにコンテンツフラグメントエディターを開くボタンが表示されます。


### 「メイン」タブ {#main-tab}

![メールコンテンツフラグメントコンポーネントのデザインダイアログ](/help/email/assets/email-content-fragment-design.png)

* **内部レスポンシブグリッド**

   * 内部レスポンシブグリッドに使用される Sling リソースタイプ

### 「スタイル」タブ {#styles-tab}

電子メールエクスペリエンスフラグメントコンポーネントは、AEM [スタイルシステム。](/help/get-started/authoring.md#component-styling)
