---
title: コアコンポーネントを使用したオーサリング
seo-title: コアコンポーネントを使用したオーサリング
description: AEMでは、コンポーネントは作成するページのコンテンツを構成する構造要素であり、コアコンポーネントは柔軟で機能豊富なオーサリング機能です。
seo-description: AEMでは、コンポーネントは作成するページのコンテンツを構成する構造要素であり、コアコンポーネントは柔軟で機能豊富なオーサリング機能です。
uuid: 4a54cd4c-3d89-4683-8301- bf1e634736e3
content-type: リファレンス
topic-tags: オーサリング
discoiquuid: 8751e490- d427-44f2- b767-51935afda988
translation-type: tm+mt
source-git-commit: 600aefa49d6247c290b8fb9f6acf5548126b3f61

---


# コアコンポーネントを使用したオーサリング

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。ここでは、ページ作成に重要なコンテンツタイプを提供するコアコンポーネントについて説明します。

コアコンポーネントを使用すると、柔軟で機能豊富なオーサリング機能を提供できます。[We. Retailリファレンスサイト](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) では、コアコンポーネントの使用方法を紹介しています。

>[!NOTE]
>
>コアコンポーネントは、作成者がすぐに使用できないので、 [開発チームはまず環境に統合する必要](using.md)があります。統合が統合されると [、テンプレートエディター](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) または [デザインモードで使用可能になり、事前設定](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html)されることがあります。

>[!CAUTION]
>
>コアコンポーネント [にはAEM6.3以降が必要](versions.md) で、クラシックUIは使用できません。

## コアコンポーネントを使用したオーサリング {#authoring-with-core-components}

コアコンポーネントを理解するには [、コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html)を調べて、コアコンポーネントを表示し、使用例を提供します。

作成者として、以下のようなコアコンポーネントの利点がいくつかあります。

* [ページエディターと簡単に連携して統合する](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)
* We. Retailに示されている [多くのユースケースに対応する機能豊富な機能](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)
* [ページ作成者が使用できる機能を定義](#pre-configuring-core-components) するために事前設定
   * テンプレート [エディター](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) を使用 [した編集可能なテンプレート](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html)
   * 静的 [テンプレート](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html) の [デザインモードを使用](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-static.html)

* [アクセシビリティガイドラインに基づいて構築](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* レスポンシブレイアウトをサポート [するように設計されています](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

コンポーネントは、ページを編集するときに、ページエディターのサイドパネルの **「コンポーネント** 」タブ [で使用](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)できます。

コンポーネントは、コンポーネントグループと呼ばれるカテゴリによってグループ化され、コンポーネントを容易に整理およびフィルタリングできます。コンポーネントのグループ名は [コンポーネントブラウザー](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) のコンポーネントと共に表示され、また、適切なコンポーネントを簡単に見つけるためにグループごとにフィルタリングできます。

>[!NOTE]
>
>コアコンポーネントは、非表示のグループのデフォルトの部分であり、コンポーネントブラウザー内では表示されません。
>
>必要なコンポーネントを表示グループに追加するか、作成者が使用できるようにカスタマイズします。

## コアコンポーネントの事前設定 {#pre-configuring-core-components}

Foundationコンポーネントの設定は、開発者のジョブでした。ただし、コアコンポーネントのテンプレート作成者は、テンプレートエディターまたはデザインモードで多数の機能を設定できるようになりました。

例えば、画像コンポーネントでファイルシステムからの画像アップロードを許可しない場合や、テキストコンポーネントで特定の段落フォーマットのみを許可する場合は、単純なクリックでこれらの機能を有効または無効にすることができます。

詳しくは、ページテンプレート [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) の作成を参照してください。

### ダイアログの編集とデザイン {#edit-and-design-dialogs}

コアコンポーネントをテンプレート作成者が事前設定して、テンプレートの一部として許可されるオプションを定義し、ページ作成者が実際のページコンテンツを定義するように設定しているので、各コンポーネントには2つの異なるダイアログにオプションを設定できます。

|  | 説明 | コントロールの内容 | 例 |
|--- |--- |--- |--- |
| **ダイアログを編集** | 配置されたコンポーネントの通常のページ編集中 **にページ作成者** が変更できるオプション | コンポーネントによって表示されるコンテンツと、最終的にページに表示されるコンテンツです。 | コンテンツテキストの形式設定、ページ上での画像の回転 |
| **デザインダイアログ** | テンプレート作成者が **ページテンプレートを設定するときに変更** できるオプションです。 | コンポーネントの編集時にページ作成者が利用できるオプション | 使用可能なテキストの書式設定オプション、つまり画像内のインプレースオプションが利用可能 |

### コンポーネントのスタイル設定 {#component-styling}

ほとんどのコアコンポーネントのスタイルは、AEMスタイルシステムを使用して定義できます。

* テンプレート作成者は、そのコンポーネントのデザインダイアログで特定のコンポーネントに使用できるスタイルを定義できます。
* コンテンツ作成者は、コンポーネントの追加時やコンテンツの作成時に適用するスタイルを選択できます。

詳しくは [、スタイルシステム](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) のドキュメントを参照してください。

>[!NOTE]
>
>スタイルシステム機能を有効にするには、AEM6.3ではサービスパック2（6.3.2.0）以降が必要です。

## 使用可能なコアコンポーネントのリスト {#list-of-core-components-available}

以下は、編集およびデザインのダイアログ機能を詳細に説明するページにリンクされた使用可能なコアコンポーネントのリストです。

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

* [パンくず](breadcrumb.md)
* [フォームボタン](form-button.md)
* [カルーセル](carousel.md)
* [フォームコンテナ](form-container.md)
* [Content Fragment](content-fragment-component.md)
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
>一部のコアコンポーネントの一部のバージョンは、特定のバージョンのAEMとのみ互換性があります。
>
>互換性の情報については、個々のヘルプページ（前のリストにリンクされている）を参照するか、 [コアコンポーネントバージョン](versions.md) ドキュメントを参照して詳細を参照してください。

>[!NOTE]
>
>インスタンスによっては、要件に合わせて明示的に開発されたカスタマイズコンポーネントが存在する場合があります。これらは、ここで説明するいくつかのコンポーネントと同じ名前の場合があります。
>フォームコアコンポーネントはAEM Formsとは関係ありません。

## 開発者リソース {#developer-resources}

コアコンポーネントに関する技術情報については [、コアコンポーネント](developing.md) 開発者向けのドキュメントを参照してください。
