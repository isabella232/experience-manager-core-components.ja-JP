---
title: コンテンツフラグメントコンポーネント
seo-title: コンテンツフラグメントコンポーネント
description: 'null'
seo-description: コアコンポーネントのコンテンツフラグメントコンポーネントを使用すれば、コンテンツフラグメントを表示できます。
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: ユーザー
content-type: reference
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: ht
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# コンテンツフラグメントコンポーネント{#content-fragment-component}

コアコンポーネントのコンテンツフラグメントコンポーネントを使用すれば、[コンテンツフラグメント](https://helpx.adobe.com/jp/experience-manager/6-5/assets/using/content-fragments.html)を表示できます。

>[!NOTE]
>
>コアコンポーネントのリリース 2.4.0 以前は、コンテンツフラグメントコンポーネントはコアコンポーネントの拡張機能として使用でき、別個にダウンロードして明示的に有効にする必要がありました。

## 使用方法 {#usage}

コアコンポーネントのコンテンツフラグメントコンポーネントを使用すれば、[コンテンツフラグメント](https://helpx.adobe.com/jp/experience-manager/6-5/assets/using/content-fragments.html)をページに組み込むことができます。

* フラグメントとそのプロパティは、[設定ダイアログ](#configure-dialog)で選択できます。
* 特定の画像やグリッドを処理するリソースタイプは、[デザインダイアログ](#design-dialog)で定義できます。
* 編集オプションをクリックすると、選択したフラグメントが[コンテンツフラグメントエディター](https://helpx.adobe.com/jp/content/help/en/experience-manager/6-5/assets/using/content-fragments.html)で開かれます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、コンテンツフラグメントコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 1.1.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

>[!NOTE]
>
>リリース 2.4.0 以前のバージョンでは、コンテンツフラグメントコンポーネントは拡張機能フォルダーに含まれていました。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>2.4.0 からは、次の場所に移動しました。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>どちらも v1 ですが、拡張機能フォルダーから使用されていたコンテンツフラグメントコンポーネントについては、リリース 2.4.0 以降のコアコンポーネントにアップグレードしたときに新しいリソースタイプを使用できるようにするには、関連するプロキシコンポーネントを移行する必要があります。

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

コンテンツフラグメントコンポーネントを実際に体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)を参照してください。

## 技術的詳細 {#technical-details}

コンテンツフラグメントコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragment/v1/contentfragment) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツフラグメントとそのフラグメントを組み込む要素をコンテンツ作成者が定義できます。

![](assets/chlimage_1-87.png)

* **コンテンツフラグメント**

   * 目的のコンテンツフラグメントへのパス
   * **選択ダイアログ** を使用して、フラグメントを見つけることができます。

* **要素** - コンテンツフラグメントを組み込む要素
* **バリエーション** - 使用するコンテンツフラグメントのバリエーション（デフォルトは **マスター**）

* **段落**

   * **すべて** - すべての段落を表示します
   * **範囲**

      * 表示する段落の範囲をセミコロンで区切って指定します
      * 例えば、`1;3-5;7;9-*` では、1 番目、3 番目から 5 番目まで、7 番目、9 番目が最終的な段落に含まれます。

* **見出しを独自の段落として処理**

## デザインダイアログ{#design-dialog}

デザインダイアログでは、混在メディア画像とレスポンシブグリッドを処理するためのリソースタイプをテンプレート作成者が定義できます。

![](assets/chlimage_1-88.png)

* **混在メディア画像タイプ**

   * 混在メディア画像のレンダリングに使用される Sling リソースタイプ

* **内部レスポンシブグリッド**

   * 内部レスポンシブグリッドに使用される Sling リソースタイプ