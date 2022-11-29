---
title: 電子メールページコンポーネント
description: 電子メールページコンポーネント
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 39%

---


# 電子メールページコンポーネント {#email-page-component}

電子メールページコンポーネントは、 [テンプレートエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja) およびを使用すると、Adobe Campaignコンテンツを作成するためにカスタマイズされたテンプレートエディターを使用して、ページヘッダー/フッターおよび構造コンポーネントを組み立てることができます。

## 使用方法 {#usage}

電子メールページコンポーネントは、電子メールコアコンポーネントと編集可能テンプレートを使用して設計されるすべてのページの基礎となります。 電子メールページコンポーネントを使用すれば、他の電子メールコアコンポーネントを使用して、ページのヘッダー、フッターおよび構造をテンプレートとして定義できます。

* の使用 [デザインダイアログ](#design-dialog) カスタムのクライアント側ライブラリは、ページ用に定義できます。
* 電子メールページコンポーネントはページ自体なので、コンポーネントから直接アクセスできる編集ダイアログを持つ他のコンポーネントとは異なり、 [編集ダイアログ](#edit-dialog) 電子メールページコンポーネントのは、ページのプロパティウィンドウです。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、電子メールページコンポーネントの現在のバージョン（2022 年 10 月に電子メールコアコンポーネントのリリース X で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | 互換性あり |

電子メールコアコンポーネントのバージョンとリリースについて詳しくは、ドキュメントを参照してください。 [電子メールコアコンポーネントのバージョン](/help/email/versions.md)

### 技術的詳細 {#technical-details}

ページコンポーネントに関する最新の技術ドキュメント [は GitHub にあります。](https://adobe.com/go/aem_cmp_tech_email_page_v1)

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 編集ダイアログ {#edit-dialog}

ページコンポーネントはページ全体を表しているので、通常は編集ダイアログで設定する内容が、[ページのプロパティ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=ja)ウィンドウにあります。

### 「Cloud Services」タブ {#cloud-services}

電子メールコアコンポーネントがキャンペーンの変数とデータを取得するには、ページがAdobe Campaign設定にリンクされている必要があります。

![電子メールページのプロパティ](/help/email/assets/email-page-properties.png)

の下 **Cloud Service設定** 見出し、ドロップダウンで「 」を選択します。 **設定を追加**.

の下 **Adobe Campaign** 」で、Adobe Campaignとの統合の設定を選択します。

ドキュメントを参照 [電子メールコアコンポーネントの使用](/help/email/using.md) 電子メールコアコンポーネントの設定について詳しくは、

### 「E メール」タブ {#email-tab}

「 E メール」タブでは、E メールの件名やプレーンテキストコンテンツなど、Adobe Campaign経由で送信される E メールのプロパティを、このページのコンテンツに基づいて定義します。

![電子メールページのプロパティ](/help/email/assets/email-page-properties-email.png)

* **件名**  — このページに基づいてAdobe Campaignから送信される E メールの件名
   * 次をクリック： **Adobe Campaign変数を選択** アイコンをクリックして開きます。 [Adobe Campaign変数を選択](/help/email/campaign-variables.md) ダイアログを開き、Adobe Campaignから動的コンテンツを挿入するためのダイアログを開きます。
* **プリヘッダー**
   * 次をクリック： **Adobe Campaign変数を選択** アイコンをクリックして開きます。 [Adobe Campaign変数を選択](/help/email/campaign-variables.md) ダイアログを開き、Adobe Campaignから動的コンテンツを挿入するためのダイアログを開きます。
* **プレーンテキスト** - Adobe Campaignから送信される E メールのプレーンテキストバージョン
   * 次をクリック： **Adobe Campaign変数を選択** アイコンをクリックして開きます。 [Adobe Campaign変数を選択](/help/email/campaign-variables.md) ダイアログを開き、Adobe Campaignから動的コンテンツを挿入するためのダイアログを開きます。
* **参照 URL**

## デザインダイアログ {#design-dialog}

ページコンポーネントはページ全体を表しているので、ページテンプレートを編集する際は、**ページ情報／ページポリシー**&#x200B;でデザインダイアログにアクセスします。

![ページポリシー](/help/assets/page-policy.png)

### 「プロパティ」タブ {#properties-tab}

ページデザインウィンドウを使用すれば、読み込むクライアントライブラリとページの Web リソースライブラリを定義できます。

![電子メールページコンポーネントデザインダイアログ](/help/email/assets/email-page-design.png)

* **クライアントライブラリ** - 読み込むクライアントライブラリカテゴリを定義します。JavaScript が本文の末尾に追加され、CSS がページの先頭に追加されます。
* **クライアントライブラリ JavaScript ページ先頭**  — ページの先頭に読み込む JavaScript クライアントライブラリカテゴリを定義します。
   * ここで定義したカテゴリが「**クライアントライブラリ**」フィールドにも存在する場合は、JavaScript が本文の末尾ではなくページの先頭に読み込まれます。
   * カテゴリが「**クライアントライブラリ**」フィールドにも存在する場合を除き、CSS は読み込まれません。
* **JavaScript ライブラリを非同期で読み込む**  — 有効にすると、カスタム JavaScript ライブラリは非同期で読み込まれます。
* **Web リソースクライアントライブラリ** - favicon などの Web リソースを提供するために使用されるクライアントライブラリカテゴリです。
* **メインコンテンツ要素セレクターにスキップ** - ページのメインコンテンツに直接スキップするアクセシビリティ機能として使用されます。

「**クライアントライブラリ**」と「**クライアントライブラリ JavaScript ページ先頭**」の両方のフィールドにライブラリを次のように設定できます。

* 新しいフィールドを追加するには、 **追加** ボタンをクリックします。
* フィールドを削除するには、削除するフィールドの横にあるごみ箱アイコンをクリックまたはタップします。
* 読み込み順序を変更するには、移動するフィールドの横にあるハンドルをクリックまたはタップしてドラッグします。

クライアント側ライブラリの使用について詳しくは、 [クライアント側ライブラリの使用。](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/clientlibs.html)

### 「スタイル」タブ {#styles-tab}

ページコンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。
