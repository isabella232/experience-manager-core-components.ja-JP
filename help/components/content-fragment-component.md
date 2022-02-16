---
title: コンテンツフラグメントコンポーネント
description: コアコンポーネントのコンテンツフラグメントコンポーネントを使用すれば、コンテンツフラグメントを表示できます。
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 99%

---

# コンテンツフラグメントコンポーネント {#content-fragment-component}

コアコンポーネントのコンテンツフラグメントコンポーネントを使用すれば、[コンテンツフラグメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=ja)を表示できます。

>[!NOTE]
>
>コアコンポーネントのリリース 2.4.0 以前は、コンテンツフラグメントコンポーネントはコアコンポーネントの拡張機能として提供されており、別途ダウンロードして明示的に有効にする必要がありました。

## 使用方法 {#usage}

コアコンポーネントのコンテンツフラグメントコンポーネントを使用すれば、[コンテンツフラグメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)をページに組み込むことができます。

* フラグメントとそのプロパティは、[設定ダイアログ](#configure-dialog)で選択できます。
* 特定の画像やグリッドを処理するリソースタイプは、[デザインダイアログ](#design-dialog)で定義できます。
* 編集オプションを選択すると、選択したフラグメントが[コンテンツフラグメントエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html?lang=ja)内で開きます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、コンテンツフラグメントコンポーネントの現在のバージョン（2017 年 10 月にコアコンポーネントのリリース 1.1.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 互換性あり<br>[リリース2.17.4](/help/versions.md) および以前 | 互換性あり | 互換性あり |

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

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

コンテンツフラグメントコンポーネントを体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_cf_jp)を参照してください。

## 技術的詳細 {#technical-details}

コンテンツフラグメントコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツフラグメントとそのフラグメントを組み込む要素をコンテンツ作成者が定義できます。

### 「プロパティ」タブ {#properties-tab}

![コンテンツフラグメントコンポーネント](/help/assets/content-fragment-edit-properties.png)

* **コンテンツフラグメント**

   * 目的のコンテンツフラグメントへのパス
   * **選択ダイアログ**&#x200B;を使用して、フラグメントを見つけることができます。

* **ディスプレイモード**
   * **単一のテキスト要素** - 複数行テキスト要素を 1 つ選択でき、段落コントロールオプションを有効にします。
   * **複数の要素** - 選択したコンテンツフラグメントの複数の要素を選択できます。
* **エレメント** - コンテンツフラグメントを組み込む要素
* **バリエーション** - 使用するコンテンツフラグメントのバリエーション（デフォルトは&#x200B;**マスター**）

* **段落**

   * **すべて** - すべての段落を表示します
   * **範囲**

      * 表示する段落の範囲をセミコロンで区切って指定します
      * 例えば、`1;3-5;7;9-*` では、1 番目、3 番目から 5 番目まで、7 番目、9 番目が最終的な段落に含まれます。
* **ID** - このオプションを使用すると、HTML 内および[データレイヤー](/help/developing/data-layer/overview.md)内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

### 「段落制御」タブ {#paragraph-control-tab}

**複数の要素**&#x200B;モードが選択されている場合は、このタブを使用できません。

![コンテンツフラグメントコンポーネント](/help/assets/content-fragment-edit-paragraph.png)

* **段落** - すべての段落、または特定の範囲を選択できます。
* **見出しを独自の段落として処理**

## デザインダイアログ {#design-dialog}

デザインダイアログでは、混在メディア画像とレスポンシブグリッドを処理するためのリソースタイプをテンプレート作成者が定義できます。

![コンテンツフラグメントコンポーネントのデザインダイアログ](/help/assets/content-fragment-design.png)

* **内部レスポンシブグリッド**

   * 内部レスポンシブグリッドに使用される Sling リソースタイプ

## Adobe Client Data Layer {#data-layer}

コンテンツフラグメントコンポーネントは、[Adobe Client Data Layer](/help/developing/data-layer/overview.md) をサポートしています。
