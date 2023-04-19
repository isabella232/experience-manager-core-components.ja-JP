---
title: メールページコンポーネント
description: メールページコンポーネント
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: c16dd8696e89f89c7b178ece11f57a565d73588b
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 100%

---


# メールページコンポーネント {#email-page-component}

メールページコンポーネントは、[テンプレートエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)と連携するように設計された拡張可能なページコンポーネントです。このコンポーネントを使用すれば、Adobe Campaign コンテンツの作成用にカスタマイズされたテンプレートエディターでページのヘッダー／フッターおよび構造要素を組み立てることができます。

## 使用方法 {#usage}

メールページコンポーネントは、メールコアコンポーネントと編集可能なテンプレートを使用して設計されるあらゆるページの基礎となるものです。メールページコンポーネントを使用すれば、ページのヘッダー、フッター、構造を、他のメールコアコンポーネントを使用する際のテンプレートとして定義できます。

* [デザインダイアログ](#design-dialog)を使用すれば、ページ用にカスタムのクライアントサイドライブラリを定義できます。
* コンポーネントから編集ダイアログに直接アクセスできる他のコンポーネントとは異なり、メールページコンポーネントはページそのものなので、メールページコンポーネントの[編集ダイアログ](#edit-dialog)が、ページプロパティウィンドウになります。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、メールページコンポーネントの現在のバージョン（2022年10月にメールコアコンポーネントのリリース X で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | - |

メールコアコンポーネントのバージョンとリリースについて詳しくは、[メールコアコンポーネントのバージョン](/help/email/versions.md)を参照してください。

### 技術的詳細 {#technical-details}

ページコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_email_page_v1) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 編集ダイアログ {#edit-dialog}

ページコンポーネントはページ全体を表しているので、通常は編集ダイアログで設定する内容が、[ページのプロパティ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=ja)ウィンドウにあります。

### 「クラウドサービス」タブ {#cloud-services}

メールコアコンポーネントがキャンペーンの変数とデータを取得するには、ページが Adobe Campaign 設定にリンクされている必要があります。

![メールページのプロパティ](/help/email/assets/email-page-properties.png)

「**クラウドサービス設定**」見出しの下のドロップダウンで、「**設定を追加**」を選択します。

「**Adobe Campaign**」見出しの下で、Adobe Campaign との統合の設定を選択します。

メールコアコンポーネントの設定について詳しくは、[メールコアコンポーネントの使用](/help/email/using.md)ドキュメントを参照してください。

### 「メール」タブ {#email-tab}

「メール」タブでは、メールの件名やプレーンテキストコンテンツなど、Adobe Campaign 経由で送信されるメールのプロパティを、このページのコンテンツに基づいて定義します。

![メールページのプロパティ](/help/email/assets/email-page-properties-email.png)

* **件名** - このページに基づいて Adobe Campaign から送信されるメールの件名
   * 「**Adobe Campaign 変数を選択**」アイコンをクリックして [Adobe Campaign 変数を選択](/help/email/campaign-variables.md)ダイアログを開き、Adobe Campaign から動的コンテンツを挿入します。
* **プリヘッダー**
   * 「**Adobe Campaign 変数を選択**」アイコンをクリックして [Adobe Campaign 変数を選択](/help/email/campaign-variables.md)ダイアログを開き、Adobe Campaign から動的コンテンツを挿入します。
* **テキスト** - Adobe Campaign から送信されるメールのプレーンテキストバージョン
   * 「**Adobe Campaign 変数を選択**」アイコンをクリックして [Adobe Campaign 変数を選択](/help/email/campaign-variables.md)ダイアログを開き、Adobe Campaign から動的コンテンツを挿入します。
* **参照 URL**

## デザインダイアログ {#design-dialog}

ページコンポーネントはページ全体を表しているので、ページテンプレートを編集する際は、**ページ情報／ページポリシー**&#x200B;でデザインダイアログにアクセスします。

![ページポリシー](/help/assets/page-policy.png)

### 「プロパティ」タブ {#properties-tab}

ページデザインウィンドウを使用すれば、読み込むクライアントライブラリとページの Web リソースライブラリを定義できます。

![メールページコンポーネントデザインのダイアログ](/help/email/assets/email-page-design.png)

* **クライアントライブラリ** - 読み込むクライアントライブラリカテゴリを定義します。JavaScript が本文の末尾に追加され、CSS がページの先頭に追加されます。
* **クライアントライブラリ JavaScript ページ先頭** - ページの先頭に読み込む JavaScript クライアントライブラリカテゴリを定義します。
   * ここで定義したカテゴリが「**クライアントライブラリ**」フィールドにも存在する場合は、JavaScript が本文の末尾ではなくページの先頭に読み込まれます。
   * カテゴリが「**クライアントライブラリ**」フィールドにも存在する場合を除き、CSS は読み込まれません。
* **JavaScript ライブラリを非同期で読み込む** - 有効にすると、カスタムJavaScriptライブラリが非同期で読み込まれます。
* **Web リソースクライアントライブラリ** - favicon などの Web リソースを提供するために使用されるクライアントライブラリカテゴリです。
* **メインコンテンツ要素セレクターにスキップ** - ページのメインコンテンツに直接スキップするアクセシビリティ機能として使用されます。

「**クライアントライブラリ**」と「**クライアントライブラリ JavaScript ページ先頭**」の両方のフィールドにライブラリを次のように設定できます。

* 新しいフィールドを追加するには、フィールドの下にある「**追加**」ボタンをクリックまたはタップします。
* フィールドを削除するには、削除するフィードの横にあるごみ箱アイコンをクリックまたはタップします。
* 読み込み順序を変更するには、移動するフィールドの横にあるハンドルをクリックまたはタップしてドラッグします。

クライアントサイドライブラリの使用について詳しくは、[クライアントサイドライブラリの使用](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/clientlibs.html)を参照してください。

### 「スタイル」タブ {#styles-tab}

ページコンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
