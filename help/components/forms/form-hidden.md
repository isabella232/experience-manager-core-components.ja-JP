---
title: フォーム非表示コンポーネント
description: コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示できます。
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# フォーム非表示コンポーネント{#form-hidden-component}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを表示できます。

## 使用方法 {#usage}

コアコンポーネントのフォーム非表示コンポーネントを使用すれば、非表示フィールドを作成して、現在のページに関する情報を AEM に返すことができます。このコンポーネントは、[フォームコンテナコンポーネント](form-container.md)と共に使用するためのものです。

フィールドのプロパティは、コンテンツ編集者が[設定ダイアログ](form-hidden.md)で定義できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、フォーム非表示コンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v2）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | 互換性あり | 互換性あり | 互換性あり | 互換性あり |
| [v1](/help/components/v1/form-hidden-v1.md) | 互換性あり | 互換性あり | 互換性あり | - |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

To experience the Form Hidden Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_form_hidden).

### 技術的詳細 {#technical-details}

フォームの非表示メントコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツ作成者が非表示フィールドのパラメーターを定義できます。

![](/help/assets/chlimage_1-26.png)

* **名前** - フィールドの名前（フォームデータと共に送信されます）
* **値** - フィールドの値（フォームデータと共に送信されます）
* **識別子** - 識別子は、ページ上で一意である必要があり、スクリプトをこのフォームフィールドにバインドするために使用できます

フォーム非表示コンポーネントには通常、表示される属性がありません。そのため、「**名前**」フィールドと「**値**」フィールドの値が割り当てられている場合、エディターのコンポーネントのプレースホルダーにはそれらのフィールド値が表示され、作成者が適切なフォーム非表示コンポーネントを識別できるようになっています。

![](/help/assets/screenshot_2018-10-19at094927.png)

## デザインダイアログ{#design-dialog}

フォーム非表示コンポーネントにはデザインダイアログはありません。
