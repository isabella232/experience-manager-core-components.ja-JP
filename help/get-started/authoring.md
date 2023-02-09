---
title: コアコンポーネントを使用したオーサリング
description: AEM では、コンポーネントとは、オーサリングの対象となるページのコンテンツを構成する構造要素のことです。コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 100%

---

# コアコンポーネントを使用したオーサリング

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。

コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。[WKND リファレンスサイト](https://wknd.site)とその説明は、リッチな web サイトエクスペリエンスを実装するためのコアコンポーネントの使用方法を示します。

コアコンポーネントを体験したり、それらの設定オプションの例や、HTML 出力や JSON 出力の例を確認したりするには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_jp)にアクセスしてください。

[AEM プロジェクトアーキタイプ](/help/developing/archetype/overview.md)を使用して AEM プロジェクトにコアコンポーネントを実装するための開発者向けの詳しい概要については、[WKND チュートリアル](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=ja)を参照してください。

>[!NOTE]
>
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](/help/get-started/using.md)。統合されると、[テンプレートエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)で使用できるようになり、事前設定されます。

>[!CAUTION]
>
>コアコンポーネントでは [AEM 6.4 以降](/help/versions.md)が必要です。また、[編集可能テンプレート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)を使用する必要があります。コアコンポーネントはクラシック UI や静的テンプレートでは動作しません。

## コアコンポーネントを使用したオーサリング {#authoring-with-core-components}

作成者には、次のようなコアコンポーネントのメリットがあります。

* 簡単に使用でき、[ページエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=ja)に適切に統合されている

* [WKND リファレンスサイト](https://wknd.site)ならびに[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_jp)で示されている多数の使用例に対応する豊富な機能を備えている

* ページ作成者が[テンプレートエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)でどの機能を使用できるかを[事前設定可能](#pre-configuring-core-components)

* [アクセシビリティガイドライン](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html?lang=ja)に沿って構築されている

* [レスポンシブレイアウト](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html?lang=ja)をサポートするように構築されている

* [容易なローカライゼーション](localization.md)をサポートする設計

コンポーネントは、**ページ編集**&#x200B;の際に、ページエディターのサイドパネルの「[コンポーネント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=ja)」タブから利用できます。

コンポーネントは、フィルタリングや整理を容易に行えるよう、コンポーネントグループと呼ばれるカテゴリに従ってグループ化されます。コンポーネントのグループ名は、[コンポーネントブラウザー](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=ja)にコンポーネントと共に表示されます。また、正しいコンポーネントを簡単に見つけられるように、グループでフィルタリングすることもできます。

>[!NOTE]
>
>コアコンポーネントは、デフォルトでは非表示グループの一部になっているので、コンポーネントブラウザー内には表示されません。
>
>必要なコンポーネントを表示グループに追加するか、カスタマイズすると、作成者が使用できるようになります。

## コアコンポーネントの事前設定 {#pre-configuring-core-components}

以前、基盤コンポーネントの設定は、開発者の仕事でした。これに対し、コアコンポーネントでは、テンプレート作成者がテンプレートエディター経由で様々な機能を設定できるようになりました。

例えば、画像コンポーネントでファイルシステムからの画像アップロードを許可しない場合や、テキストコンポーネントで特定の段落フォーマットのみを許可する場合は、クリックするだけでそれらの機能の有効／無効を切り替えることができます。

詳しくは、[ページテンプレートの作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)を参照してください。

### 編集ダイアログとデザインダイアログ {#edit-and-design-dialogs}

コアコンポーネントでは、テンプレート作成者がテンプレートの一部として使用できるオプションを定義することでコアコンポーネントを事前設定した後、ページ作成者がさらに設定することで実際のページコンテンツを定義できます。これにより、各コンポーネントで、異なる 2 つのダイアログ内にオプションが存在することがあります。

|  | 説明 | 制御対象 | 例 |
|--- |--- |--- |--- |
| **編集ダイアログ** | **ページ作成者**&#x200B;が通常のページ編集中に、配置したコンポーネントに対して変更できるオプション | コンポーネントによって表示されるコンテンツや、そのコンテンツが最終的にページ上でどのように表示されるか。 | コンテンツテキストの書式設定、ページ上の画像の回転 |
| **デザインダイアログ** | **テンプレート作成者**&#x200B;がページテンプレートの設定時に変更できるオプション。 | ページ作成者がコンポーネント編集時に利用できるオプション | 利用可能なテキスト書式設定オプション、利用可能な画像インプレースオプション |

### コンポーネントのスタイル設定 {#component-styling}

ほとんどのコアコンポーネントのスタイルは、AEM スタイルシステムを使用して定義できます。

* テンプレート作成者は、特定のコンポーネントで利用可能なスタイルを、そのコンポーネントのデザインダイアログで定義できます。
* その後、コンテンツ作成者は、コンポーネントを追加してコンテンツを作成する際に、適用するスタイルを選択できます。

詳しくは、[スタイルシステム](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html?lang=ja)のドキュメントを参照してください。

## 開発者リソース {#developer-resources}

コアコンポーネントに関する技術情報については、開発者向けのドキュメントの[コアコンポーネントの開発](/help/developing/overview.md)を参照してください。
