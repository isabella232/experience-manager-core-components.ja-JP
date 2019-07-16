---
title: コアコンポーネントを使用したオーサリング
seo-title: コアコンポーネントを使用したオーサリング
description: AEM では、コンポーネントとは、オーサリングの対象となるページのコンテンツを構成する構造要素のことです。コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。
seo-description: AEM では、コンポーネントとは、オーサリングの対象となるページのコンテンツを構成する構造要素のことです。コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。
uuid: 4a54cd4c-3d89-4683-8301-bf1e634736e3
content-type: reference
topic-tags: authoring
discoiquuid: 8751e490-d427-44f2-b767-51935afda988
translation-type: ht
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# コアコンポーネントを使用したオーサリング

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。ここでは、ページを作成するために必要なコンテンツタイプを提供する、コアコンポーネントについて説明します。

コアコンポーネントは、柔軟で機能豊富なオーサリング機能を提供します。[We.Retail リファレンスサイト](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/we-retail.html)は、コアコンポーネントの使用方法を示しています。

コアコンポーネントを体験したり、それらの設定オプションの例や、HTML 出力や JSON 出力の例を確認したりするには、[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)にアクセスしてください。

>[!NOTE]
>
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](using.md)。統合が完了したら、[テンプレートエディター](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/templates.html)経由でコアコンポーネントを利用可能にしたり、事前設定したりできます。

>[!CAUTION]
>
>コアコンポーネントを使用するには、[AEM 6.3 以上が必要になる](versions.md)ほか、[編集可能テンプレート](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/templates.html)を使用する必要もあります。コアコンポーネントはクラシック UI や静的テンプレートでは動作しません。

## コアコンポーネントを使用したオーサリング {#authoring-with-core-components}

作成者の場合、次のようなコアコンポーネントのメリットがあります。

* 簡単に使用でき、[ページエディター](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/editing-content.html)にうまく統合されている

* 豊富な機能で [We.Retail](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/we-retail.html) や[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)で示したような様々なユースケースに対応できる

* [事前設定可能](#pre-configuring-core-components)。[テンプレートエディター](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/templates.html)で、ページ作成者が使用できる機能を定義できる

* [アクセシビリティガイドライン](https://helpx.adobe.com/jp/experience-manager/6-5/managing/using/web-accessibility.html)に沿って構築されている

* [レスポンシブレイアウト](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/responsive-layout.html)対応の設計

コンポーネントは、[ページ編集](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/editing-content.html)の際に、ページエディターのサイドパネルの「**コンポーネント**」タブから利用できます。

コンポーネントは、フィルタリングや整理を容易におこなえるよう、コンポーネントグループと呼ばれるカテゴリに従ってグループ化されます。コンポーネントのグループ名は、コンポーネントとともに[コンポーネントブラウザー](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/editing-content.html)に表示されます。また、正しいコンポーネントを簡単に見つけられるように、グループでフィルタリングすることもできます。

>[!NOTE]
>
>コアコンポーネントは、デフォルトでは非表示グループの一部になっているので、コンポーネントブラウザー内には表示されません。
>
>必要なコンポーネントを表示グループに追加するか、カスタマイズすると、作成者が使用できるようになります。

## コアコンポーネントの事前設定 {#pre-configuring-core-components}

以前、Foundation コンポーネントの設定は、開発者の仕事でした。これに対し、コアコンポーネントでは、テンプレート作成者がテンプレートエディター経由で様々な機能を設定できるようになりました。

例えば、画像コンポーネントでファイルシステムからの画像アップロードを許可しない場合や、テキストコンポーネントで特定の段落フォーマットのみを許可する場合は、クリックするだけでそれらの機能の有効／無効を切り替えることができます。

詳しくは、[ページテンプレートの作成](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/templates.html)を参照してください。

### 編集ダイアログとデザインダイアログ {#edit-and-design-dialogs}

コアコンポーネントでは、テンプレート作成者がテンプレートの一部として使用できるオプションを定義することでコアコンポーネントを事前設定した後、ページ作成者がさらに設定することで実際のページコンテンツを定義できます。これにより、各コンポーネントで、異なる 2 つのダイアログ内にオプションが存在することがあります。

|  | 説明 | 制御対象 | 例 |
|--- |--- |--- |--- |
| **編集ダイアログ** | **ページ作成者** が通常のページ編集中に、配置したコンポーネントに対して変更できるオプション | コンポーネントによって表示されるコンテンツや、そのコンテンツが最終的にページ上でどのように表示されるか。 | コンテンツテキストの書式設定、ページ上の画像の回転 |
| **デザインダイアログ** | **テンプレート作成者** がページテンプレートの設定時に変更できるオプション。 | ページ作成者がコンポーネント編集時に利用できるオプション | 利用可能なテキスト書式設定オプション、利用可能な画像インプレースオプション |

### コンポーネントのスタイル設定 {#component-styling}

ほとんどのコアコンポーネントのスタイルは、AEM スタイルシステムを使用して定義できます。

* テンプレート作成者は、特定のコンポーネントで利用可能なスタイルを、そのコンポーネントのデザインダイアログで定義できます。
* その後、コンテンツ作成者は、コンポーネントを追加してコンテンツを作成する際に、適用するスタイルを選択できます。

詳しくは、[スタイルシステム](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/style-system.html)ドキュメントを参照してください。

>[!NOTE]
>
>AEM 6.3 でスタイルシステムの機能を有効にするには、サービスパック 2（6.3.2.0）以降が必要となります。

## 利用可能なコアコンポーネントの一覧 {#list-of-core-components-available}

利用可能なコアコンポーネントの一覧を以下に示します。各コンポーネントは、該当する編集ダイアログやデザインダイアログの機能を詳しく説明したページにリンクされています。

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

* [パンくず](breadcrumb.md)
* [フォームボタン](form-button.md)
* [カルーセル](carousel.md)
* [フォームコンテナ](form-container.md)
* [コンテンツフラグメント](content-fragment-component.md)
* [コンテンツフラグメントリスト](content-fragment-list.md)
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
* [ティーザー](teaser.md)
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
