---
title: タイトルコンポーネント (v2)
description: コアコンポーネントのタイトルコンポーネントは、インプレース編集機能を備えたセクション見出しコンポーネントです。
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 94%

---


# タイトルコンポーネント（v2）  {#title-component}

コアコンポーネントのタイトルコンポーネントは、インプレース編集機能を備えたセクション見出しコンポーネントです。

## 使用方法 {#usage}

タイトルコンポーネントは、コンテンツのセクションのタイトルまたは見出しとして使用するためのものです。使用可能な見出しレベルは、[デザインダイアログ](#design-dialog)でテンプレート作成者が定義できます。コンテンツ編集者は、[編集ダイアログ](#edit-dialog)で、使用可能な見出しレベルから選択できます。利便性の向上のため、見出しテキストの簡単なインプレース編集も可能です。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入されたタイトルコンポーネント v2 について説明します。

>[!CAUTION]
>
>このドキュメントでは、タイトルコンポーネント v2 について説明します。
>
>タイトルコンポーネントの現在のバージョンについて詳しくは、[タイトルコンポーネント](/help/components/title.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

タイトルコンポーネントを体験し、その設定オプションや HTML および JSON 出力の例を確認するには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_title_jp)を参照してください。

### 技術的詳細 {#technical-details}

タイトルコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_title_v2_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 編集ダイアログ {#edit-dialog}

編集ダイアログでは、コンテンツ作成者がタイトルテキストを定義したり、見出しレベルを選択したりできます。

* **タイトル** - 空白の場合、ページタイトルが使用されます
* **種類 / サイズ** - タイトルの見出しレベルを定義します
* **リンク** - タイトルのリンク先のコンテンツを定義します。コンテンツページへのパス、外部 URL、ページアンカーのいずれかを指定できます。
* **ID** - このオプションを使用すると、HTML 内および[データレイヤー](/help/developing/data-layer/overview.md)内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

![タイトルコンポーネントの編集ダイアログ](/help/assets/title-edit.png)

>[!NOTE]
>
>タイトルのリンクを定義する機能は、コアコンポーネントのリリース 2.2.0 で導入されました。

インプレースエディターを使用して、タイトルコンポーネントのテキストを編集することもできます。

![タイトルコンポーネントのインプレース編集](/help/assets/title-edit-inline.png)

## デザインダイアログ {#design-dialog}

デザインダイアログでは、コンテンツ作成者が使用する際のタイトルコンポーネントのデフォルト見出しレベルをテンプレート作成者が定義できます。

### 「サイズ」タブ {#sizes-tab}

![タイトルコンポーネントのデザインダイアログ](/help/assets/title-design.png)

* **作成者に許可されたタイプ / サイズ** - コンテンツ作成者がタイトルコンポーネントを使用する際に選択できる見出しタイプを有効または無効にします。
* **デフォルトのタイプ / サイズ** - コンテンツ作成者がタイトルコンポーネントをページに追加したときに自動的に割り当てられる見出しタイプを定義します。
* **リンクを無効化** - タイトルコンポーネントでのリンクのサポートを無効にして、コンテンツ作成者がタイトルからリンクできないようにします。

>[!NOTE]
>
>タイトルのリンクを定義する機能は、コアコンポーネントのリリース 2.2.0 で導入されました。

### 「スタイル」タブ {#styles-tab}

タイトルコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

## Adobe Client Data Layer {#data-layer}

タイトルコンポーネントは、[Adobe Client Data Layer](/help/developing/data-layer/overview.md) をサポートしています。