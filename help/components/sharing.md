---
title: ソーシャル共有コンポーネント
description: コアコンポーネントのソーシャル共有コンポーネントは、Facebook および Pinterest の共有ウィジェットです。
translation-type: ht
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: ht
source-wordcount: '429'
ht-degree: 100%

---


# ソーシャル共有コンポーネント{#social-sharing-component}

コアコンポーネントのソーシャル共有コンポーネントは、Facebook および Pinterest の共有ウィジェットです。

## 使用方法 {#usage}

ソーシャル共有コンポーネントでは、ページに Facebook および Pinterest の共有リンクを追加します。これは多くの場合、ページのヘッダーまたはフッターに含まれています。

他のコンポーネントとは異なり、ソーシャル共有コンポーネントの設定は、テンプレート作成者の場合は[最初のページのプロパティ](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/templates.html)、コンテンツ作成者の場合は[ページのプロパティ](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)でおこないます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、ソーシャル共有コンポーネントの現在のバージョン（AEM 6.3 とともにコアコンポーネントのリリース 1.0.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョンおよびコンポーネントの各バージョンと互換性のある AEM バージョンを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

ソーシャル共有コンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_sharing_jp)を参照してください。

### 技術的詳細 {#technical-details}

コンポーネント共有に関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 編集ダイアログ{#edit-dialog}

![共有コンポーネントの編集ダイアログ](/help/assets/sharing-edit.png)

* **ID** - このオプションを使用すると、HTML 内および [データレイヤー](/help/developing/data-layer/overview.md)内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

共有には特別なページヘッダーが必要なので、共有はすべてページレベルで有効にする必要があります。そのため、コンテンツ作成者の場合、共有コンポーネントの編集オプションは、「共有」タブの[ページのプロパティ](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)で使用できます。

## デザインダイアログ{#design-dialog}

共有には特別なページヘッダーが必要なので、共有はすべてページレベルで有効にする必要があります。そのため、テンプレート作成者の場合、共有コンポーネントのデザインオプションは、[最初のページのプロパティ](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/templates.html)で使用できます。
