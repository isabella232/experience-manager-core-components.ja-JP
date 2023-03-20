---
title: アダプティブFormsコアコンポーネント — ヘッダー
description: アダプティブFormsヘッダーコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 6%

---

# ヘッダー {#header-adaptive-forms-core-component}

アダプティブフォームのヘッダーコンポーネントは、通常、フォームのタイトル、ロゴまたは名前を含む、フォーム上部のセクションです。 ヘッダーには、フォームの目的の簡単な説明、フォームを作成した組織の名前、フォームに関するヘルプ情報など、その他の情報も含めることができます。 ヘッダーは、ユーザーにフォームの概要を提供し、入力しようとしている情報のコンテキストを提供するために使用されます。 これは、ユーザーがフォームの目的や正しい入力方法を理解するのに役立ちます。

**例**

![](/help/adaptive-forms/assets/header.png)

## 使用方法 {#reasons-to-use-header}

* **ブランディング**:ヘッダーを使用して、フォームを作成した組織のロゴや名前を表示し、ブランド認知度と信頼性を確立できます。

* **コンテキスト**:ヘッダーには、フォームの目的の簡単な説明を入力し、フォームが使用されているコンテキストをユーザーが理解できるようにします。

* **ナビゲーション**:ヘッダーには、ユーザーが Web サイトやアプリケーションの他の部分に移動するためのリンクやボタンを含めることができます。

* **情報**:ヘッダーには、連絡先情報やヘルプリソースへのリンクを含めることができ、必要に応じてユーザーが簡単にサポートを受けることができます。

* **ユーザーエクスペリエンス**:ヘッダーを使用すると、ユーザーがフォームフィールドにアクセスして入力する際に直感的な方法を提供し、より使いやすくフォームを作成できます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブFormsアコーディオンコアコンポーネントは、Cloud Service用コアコンポーネント 2.0.4 の一部として 2023 年 2 月にリリースされ、AEM 6.5.16.0 Forms以降用コアコンポーネント 1.1.12 にリリースされました。 次の表に、サポートされているすべてのバージョン、AEMの互換性、および対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms以降 |
|---|---|---|
| v1 | 互換性あり<br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降 | 互換性あり<br>[リリース 1.1.12](/help/adaptive-forms/version.md) 2.0.0 未満です。 |

コアコンポーネントのバージョンとリリースについて詳しくは、 [コアコンポーネントのバージョン](/help/adaptive-forms/version.md) 文書。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術的詳細 {#technical-details}

アダプティブFormsヘッダーコアコンポーネントの最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader). コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](/help/developing/overview.md).

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者に対するヘッダーエクスペリエンスを簡単にカスタマイズできます。 また、簡単にヘッダーオプションを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 「画像」タブ {#image-tab}

ヘッダーのこの部分には、ヘッダーのタイトルと画像が含まれます。

![Imagetab](/help/adaptive-forms/assets/header_image.png)

* **画像アセット**  — このオプションを使用すると、マウスでのドラッグ&amp;ドロップによって画像などのアセットをドロップできます。 また、 **参照** 」ボタンをクリックします。 画像を追加すると、画像の下部に 3 つのボタンが表示されます。 画像を追加すると、画像の下部に 3 つのボタンが表示されます。
   * **編集**  — タップまたはクリック **編集** をクリックして、アセットエディターでアセットのレンディションを管理します。
   * **クリア**  — タップまたはクリック **クリア** をクリックして、現在選択されている画像の選択を解除します。
   * **選択**  — タップまたはクリック **選択**  「 」オプションを使用して、Assets フォルダーから別の画像を選択します。

* **タイトル**  — このオプションは、ヘッダーに見出しを追加するために使用されます。 定義済みのテキストはダイアログボックスに含まれ、ユーザーが変更できます。
* **リンク先** - 「 **参照** アイコン
* **説明**  — 説明とは、特定の画像の目的に関する追加情報や説明を提供する、簡単なテキストの説明です。
* **サイズ (px)**  — ピクセルを増減して画像の長さと幅を調整するのに役立ちます。

![accessibilitytab](/help/adaptive-forms/assets/header_accessibility.png)

* **代替テキスト**  — このオプションは、視覚に障害のあるユーザーに対して画像を説明する、画像に代わる短く説明的なテキストを入力するために使用されます。

* **画像は装飾画像** - 画像が支援テクノロジーによって無視される場合（したがってその代替テキストが不要な場合）はオンにします。これは、装飾画像にのみ適用されます。

### 「テキスト」タブ {#text-tab}

このセクションでは、ヘッダーに含めるテキストを入力できます。

