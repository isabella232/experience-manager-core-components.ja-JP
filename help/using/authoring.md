---
title: コアコンポーネントを使用したオーサリング
seo-title: コアコンポーネントを使用したオーサリング
description: AEM では、コンポーネントとは、オーサリングの対象となるページのコンテンツを構成する構造要素のことです。コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。
seo-description: AEM では、コンポーネントとは、オーサリングの対象となるページのコンテンツを構成する構造要素のことです。コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。
uuid: 4a54cd4c-3d89-4683-8301-bf1e634736e3
content-type: reference
topic-tags: authoring
discoiquuid: 8751e490-d427-44f2-b767-51935afda988
translation-type: tm+mt
source-git-commit: b6fbef1cff2908533df6573cd3a92266857ba93f

---


# コアコンポーネントを使用したオーサリング

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。

コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。[We. Retailリファレンスサイト](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) では、コアコンポーネントの使用方法を紹介しています。

コアコンポーネントを体験したり、それらの設定オプションの例や、HTML 出力や JSON 出力の例を確認したりするには、[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)にアクセスしてください。

AEMプロジェクトにコアコンポーネントを実装するための開発者向けの詳細な紹介は、 [WKNDのチュートリアルをご覧ください。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

>[!NOTE]
>
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](using.md)。Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html).

>[!CAUTION]
>
>コアコンポーネント [にはAEM6.3以降が必要で、](versions.md)[編集可能なテンプレート](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)を使用する必要があります。コアコンポーネントはクラシック UI や静的テンプレートでは動作しません。

## コアコンポーネントを使用したオーサリング {#authoring-with-core-components}

作成者の場合、次のようなコアコンポーネントのメリットがあります。

* [ページエディターと簡単に連携して統合する](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)

* We. Retailに加え、コンポーネントライブラリに [表示される多数のユース](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) ケースに対応する [機能豊富な機能](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)

* [テンプレートエディターを使用してページ作成者が使用できる機能を定義](#pre-configuring-core-components) する [ために事前設定が可能](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

* [アクセシビリティガイドラインに基づいて構築](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* Built to support [responsive layout](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

* ローカリゼーションを容易にする [ために構築されました](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html).

コンポーネントは、フィルタリングや整理を容易におこなえるよう、コンポーネントグループと呼ばれるカテゴリに従ってグループ化されます。The component group name is displayed with the component in the [component browser](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) and it is also possible to filter by group to easily find the right component.

>[!NOTE]
>
>コアコンポーネントは、デフォルトでは非表示グループの一部になっているので、コンポーネントブラウザー内には表示されません。
>
>必要なコンポーネントを表示グループに追加するか、カスタマイズすると、作成者が使用できるようになります。

## コアコンポーネントの事前設定 {#pre-configuring-core-components}

以前、Foundation コンポーネントの設定は、開発者の仕事でした。これに対し、コアコンポーネントでは、テンプレート作成者がテンプレートエディター経由で様々な機能を設定できるようになりました。

例えば、画像コンポーネントでファイルシステムからの画像アップロードを許可しない場合や、テキストコンポーネントで特定の段落フォーマットのみを許可する場合は、クリックするだけでそれらの機能の有効／無効を切り替えることができます。

See [Creating Page Templates](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) for more information.

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

詳しくは [、スタイルシステム](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) のドキュメントを参照してください。

>[!NOTE]
>
>AEM 6.3 でスタイルシステムの機能を有効にするには、サービスパック 2（6.3.2.0）以降が必要となります。

## 利用可能なコアコンポーネントの一覧 {#list-of-core-components-available}

利用可能なコアコンポーネントの一覧を以下に示します。各コンポーネントは、該当する編集ダイアログやデザインダイアログの機能を詳しく説明したページにリンクされています。

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

* [アコーディオン](accordion.md)
* [パンくず](breadcrumb.md)
* [ボタン](button.md)
* [コンテナ](container.md)
* [カルーセル](carousel.md)
* [コンテンツフラグメント](content-fragment-component.md)
* [コンテンツフラグメントリスト](content-fragment-list.md)
* [ダウンロード](download.md)
* [エクスペリエンスフラグメント](experience-fragment.md)
* [フォームボタン](form-button.md)
* [フォームコンテナ](form-container.md)
* [フォーム非表示](form-hidden.md)
* [フォームオプション](form-options.md)
* [フォームテキスト](form-text.md)
* [画像](image.md)
* [言語ナビゲーション](language-navigation.md)
* [リスト](list.md)
* [ナビゲーション](navigation.md)
* [ページ](page.md)
* [クイック検索](quick-search.md)
* [区切り文字](separator.md)
* [ソーシャルメディア共有](sharing.md)
* [タブ](tabs.md)
* [テキスト](text.md)
* [タイトル](title.md)

>[!CAUTION]
>
>個々のコアコンポーネントの一部のバージョンは、特定のバージョンの AEM とのみ互換性があります。
>
>互換性の情報については、特定のコンポーネントに対する個々のヘルプページ（前の一覧にリンクされている）を参照するか、[コアコンポーネントバージョン](versions.md)ドキュメントで詳細を確認してください。

>[!NOTE]
>
>インスタンスによっては、要件に合わせて明示的に開発されたカスタマイズコンポーネントが存在する場合があります。これらは、ここで説明するいくつかのコンポーネントと同じ名前の場合があります。
>フォームコアコンポーネントは、AEM Forms とは関係ありません。

## 開発者リソース {#developer-resources}

コアコンポーネントに関する技術情報については、開発者向けのドキュメントである[コアコンポーネントの開発](developing.md)を参照してください。
