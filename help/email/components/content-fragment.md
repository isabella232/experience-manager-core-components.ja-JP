---
title: メールコンテンツフラグメントコンポーネント
description: メールコンテンツフラグメントコンポーネントを使用すると、コンテンツ内のコンテンツフラグメントを表示できます。
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 100%

---


# メールコンテンツフラグメントコンポーネント  {#email-content-fragment-component}

メールコンテンツフラグメントコンポーネントを使用すると、コンテンツ内の[コンテンツフラグメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=ja)を表示できます。

## 使用方法 {#usage}

メールコンテンツフラグメントコンポーネントを使用すれば、[コンテンツフラグメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)をメールコンテンツに含めることができます。 コンテンツフラグメントは、一元的に作成して容易に再利用できるマルチチャネル構造コンテンツです。

* フラグメントとそのプロパティは、[設定ダイアログ](#configure-dialog)で選択することができます。
* 特定の画像やグリッドを処理するリソースタイプは、[デザインダイアログ](#design-dialog)で定義することができます。
* 編集オプションを選択すると、メールコアコンポーネントで使用するためにカスタマイズされた[コンテンツフラグメントエディター](#edit-dialog)内で選択したフラグメントが開きます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、メールコンテンツフラグメントコンポーネントの現在のバージョン（2022 年 10 月にメールコアコンポーネントのリリース x で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | 互換性あり |

メールコアコンポーネントのバージョンとリリースについて詳しくは、[メールコアコンポーネントのバージョン](/help/email/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

メールコンテンツフラグメントコンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_email_cf)を参照してください。

## 技術的詳細 {#technical-details}

メールコンテンツフラグメントコンポーネントに関する最新の技術ドキュメントについては、[GitHub を参照してください。](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメントを参照してください。](/help/developing/overview.md)

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、コンテンツ作成者は、どのコンテンツフラグメントとそのフラグメントの要素を含めるかを定義することができます。

### 「プロパティ」タブ {#properties-tab}

![メールコンテンツフラグメントコンポーネント](/help/email/assets/email-content-fragment-edit-properties.png)

* **コンテンツフラグメント**

   * 目的のコンテンツフラグメントへのパス
   * **選択ダイアログ**&#x200B;を使用して、フラグメントを見つけることができます。

* **ディスプレイモード**
   * **単一のテキスト要素** - 複数行テキスト要素を 1 つ選択でき、段落コントロールオプションを有効にします。
* **バリエーション** - 使用するコンテンツフラグメントのバリエーション（デフォルトは&#x200B;**マスター**）

* **ID** - このオプションを使用すると、HTML 内のコンポーネントの一意の ID を制御することができます。
   * これを空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS に影響を与える可能性があります。

### 「段落制御」タブ {#paragraph-control-tab}

![メールコンテンツフラグメントコンポーネント](/help/assets/content-fragment-edit-paragraph.png)

* **段落** - すべての段落、または特定の範囲を選択できます。
   * **すべて** - すべての段落を表示します
   * **範囲**
      * 表示する段落の範囲をセミコロンで区切って指定します
      * たとえば `1;3-5;7;9-*` は、1 番目、3 番目から 5 番目、7 番目、9 番目から最後の段落を含めます
* **見出しを独自の段落として処理**

## 編集ダイアログ {#edit-dialog}

メールコンテンツフラグメントコンポーネントを使用してコンテンツフラグメントを設定してから、コンテンツエディターでコンポーネントを選択すると、「**編集**」オプションが表示されます。

![メールコンテンツフラグメントコンポーネントのツールバー](/help/email/assets/email-content-fragment-edit-toolbar.png)

**編集**&#x200B;ボタンをタップまたはクリックすると、コンテンツフラグメントエディターが開きます。 コンテンツフラグメントエディターの拡張で追加されたボタンから、 **Adobe Campaign の変数を選択**&#x200B;して、コンテンツフラグメントに Adobe Campaign の変数を挿入できるようになりました。

![メール用のコンテンツフラグメントエディター](/help/email/assets/email-content-fragment-editor.png)

コンテンツフラグメントの編集と作成について詳しくは、[フラグメントコンテンツの作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html?lang=ja)を参照してください。

## デザインダイアログ {#design-dialog}

メールメールコンテンツフラグメントコンポーネントにコンテンツフラグメントが設定されている場合、コンテンツエディターでコンテンツフラグメントを選択すると、コンテンツフラグメントエディターを開くためのボタンがツールバーに表示されます。


### 「メイン」タブ {#main-tab}

![メールコンテンツフラグメントコンポーネントのデザインダイアログ](/help/email/assets/email-content-fragment-design.png)

* **内部レスポンシブグリッド**

   * 内部レスポンシブグリッドに使用される Sling リソースタイプ

### 「スタイル」タブ {#styles-tab}

メールエクスペリエンスフラグメントコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
