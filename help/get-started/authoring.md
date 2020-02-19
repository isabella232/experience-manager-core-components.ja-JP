---
title: コアコンポーネントを使用したオーサリング
description: AEM では、コンポーネントとは、オーサリングの対象となるページのコンテンツを構成する構造要素のことです。コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# コアコンポーネントを使用したオーサリング

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。

コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。WKNDリファレ [ンスサイトとその説明に](https://wknd.site) 、リッチなWebサイトエクスペリエンスを実装するためのコアコンポーネントの使用方法を示します。

コアコンポーネントを体験したり、それらの設定オプションの例や、HTML 出力や JSON 出力の例を確認したりするには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library)にアクセスしてください。

For a more in-depth, developer-oriented introduction to implementing the Core Components on an AEM project by using the [AEM Project Archetype](/help/developing/archetype/overview.md) check out [the WKND tutorial.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](/help/get-started/using.md)。統合されると、[テンプレートエディター](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)で使用できるようになり、事前設定されます。

>[!CAUTION]
>
>コアコンポーネントでは [AEM 6.3 以降](/help/versions.md)が必要です。また、[編集可能テンプレート](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)を使用する必要があります。コアコンポーネントはクラシック UI や静的テンプレートでは動作しません。

## コアコンポーネントを使用したオーサリング {#authoring-with-core-components}

作成者の場合、次のようなコアコンポーネントのメリットがあります。

* 簡単に使用でき、[ページエディター](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)に適切に統合されている

* [WKNDリファレンスサイトやコンポーネントライブラリで示されている多くの使用例に対応する](https://wknd.site) 、豊富な機能を備 [えています。](https://adobe.com/go/aem_cmp_library)

* ページ作成者が[テンプレートエディター](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)でどの機能を使用できるかを[事前設定可能](#pre-configuring-core-components)

* [アクセシビリティガイドライン](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)に沿って構築されている

* [レスポンシブレイアウト](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)をサポートするように構築されている

* [容易なローカライゼーション](localization.md)をサポートする設計

コンポーネントは、**ページ編集**&#x200B;の際に、ページエディターのサイドパネルの「[コンポーネント](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)」タブから利用できます。

コンポーネントは、フィルタリングや整理を容易におこなえるよう、コンポーネントグループと呼ばれるカテゴリに従ってグループ化されます。コンポーネントのグループ名は、[コンポーネントブラウザー](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)にコンポーネントと共に表示されます。また、正しいコンポーネントを簡単に見つけられるように、グループでフィルタリングすることもできます。

>[!NOTE]
>
>コアコンポーネントは、デフォルトでは非表示グループの一部になっているので、コンポーネントブラウザー内には表示されません。
>
>必要なコンポーネントを表示グループに追加するか、カスタマイズすると、作成者が使用できるようになります。

## コアコンポーネントの事前設定 {#pre-configuring-core-components}

以前、Foundation コンポーネントの設定は、開発者の仕事でした。これに対し、コアコンポーネントでは、テンプレート作成者がテンプレートエディター経由で様々な機能を設定できるようになりました。

例えば、画像コンポーネントでファイルシステムからの画像アップロードを許可しない場合や、テキストコンポーネントで特定の段落フォーマットのみを許可する場合は、クリックするだけでそれらの機能の有効／無効を切り替えることができます。

詳しくは、[ページテンプレートの作成](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)を参照してください。

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

詳しくは、[スタイルシステム](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html)のドキュメントを参照してください。

>[!NOTE]
>
>AEM 6.3 でスタイルシステムの機能を有効にするには、サービスパック 2（6.3.2.0）以降が必要となります。

## 利用可能なコアコンポーネントの一覧 {#list-of-core-components-available}

利用可能なコアコンポーネントの一覧を以下に示します。各コンポーネントは、該当する編集ダイアログやデザインダイアログの機能を詳しく説明したページにリンクされています。

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

* [アコーディオン](/help/components/accordion.md)
* [パンくず](/help/components/breadcrumb.md)
* [ボタン](/help/components/button.md)
* [コンテナ](/help/components/container.md)
* [カルーセル](/help/components/carousel.md)
* [コンテンツフラグメント](/help/components/content-fragment-component.md)
* [コンテンツフラグメントリスト](/help/components/content-fragment-list.md)
* [ダウンロード](/help/components/download.md)
* [埋め込み](/help/components/embed.md)
* [エクスペリエンスフラグメント](/help/components/experience-fragment.md)
* [フォームボタン](/help/components/forms/form-button.md)
* [フォームコンテナ](/help/components/forms/form-container.md)
* [フォーム非表示](/help/components/forms/form-hidden.md)
* [フォームオプション](/help/components/forms/form-options.md)
* [フォームテキスト](/help/components/forms/form-text.md)
* [画像](/help/components/image.md)
* [言語ナビゲーション](/help/components/language-navigation.md)
* [リスト](/help/components/list.md)
* [ナビゲーション](/help/components/navigation.md)
* [ページ](/help/components/page.md)
* [クイック検索](/help/components/quick-search.md)
* [区切り文字](/help/components/separator.md)
* [ソーシャルメディア共有](/help/components/sharing.md)
* [タブ](/help/components/tabs.md)
* [テキスト](/help/components/text.md)
* [タイトル](/help/components/title.md)

>[!CAUTION]
>
>個々のコアコンポーネントの一部のバージョンは、特定のバージョンの AEM とのみ互換性があります。
>
>互換性の情報については、特定のコンポーネントに対する個々のヘルプページ（前の一覧にリンクされています）を参照するか、[コアコンポーネントバージョン](/help/versions.md)ドキュメントで詳細を確認してください。

>[!NOTE]
>
>インスタンスによっては、要件に合わせて明示的に開発されたカスタマイズコンポーネントが存在する場合があります。これらは、ここで説明するいくつかのコンポーネントと同じ名前の場合があります。
>フォームコアコンポーネントは、AEM Forms とは関係ありません。

## 開発者リソース {#developer-resources}

コアコンポーネントに関する技術情報については、開発者向けのドキュメントである[コアコンポーネントの開発](/help/developing/overview.md)を参照してください。
