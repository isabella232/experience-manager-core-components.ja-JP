---
title: アダプティブフォームのコアコンポーネント - ヘッダー
description: アダプティブフォームのヘッダーコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: ht
source-wordcount: '748'
ht-degree: 100%

---

# ヘッダー {#header-adaptive-forms-core-component}

アダプティブフォームのヘッダーコンポーネントとは、フォームのタイトル、ロゴまたは名前など、通常はフォーム上部のセクションを指します。ヘッダーには、フォームの目的の簡単な説明、フォームを作成した組織の名前、フォームに関するサポート連絡先など、その他の情報も含めることができます。ヘッダーは、ユーザーにフォームの概要を提供し、入力する情報のコンテキストを提供するために使用されます。これは、ユーザーがフォームの目的や正しい入力方法を理解するのに役立ちます。

**例**

![](/help/adaptive-forms/assets/header.png)

## 使用方法 {#reasons-to-use-header}

* **ブランディング**：このヘッダーは、フォームを作成した組織のロゴや名前を表示することで、ブランドの認知度を上げ、信頼性を確立するのに役立ちます。

* **コンテキスト**：このヘッダーではフォームの目的の簡単な説明を提供し、フォームが使用されるコンテキストをユーザーが理解できるようにします。

* **ナビゲーション**：このヘッダーには、ユーザーが web サイトやアプリケーションの他の部分に移動するためのリンクやボタンを含めることができます。

* **情報**：このヘッダーには連絡先情報やヘルプリソースへのリンクを含めることができ、必要に応じてユーザーにヒントを提供できます。

* **ユーザーエクスペリエンス**：このヘッダーは、ユーザーがフォームフィールドにアクセスして入力する際に直感的でわかりやすい方法を提供することで、より使いやすくフォームを作成するために使用します。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術的詳細 {#technical-details}

アダプティブフォームのヘッダーコアコンポーネントの最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者によるヘッダーの利用を簡単にカスタマイズできます。 また、簡単にヘッダーオプションを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 「画像」タブ {#image-tab}

ヘッダーのこの部分には、ヘッダーのタイトルと画像が含まれます。

![Imagetab](/help/adaptive-forms/assets/header_image.png)

* **画像アセット** - このオプションを使用すると、マウスでのドラッグ&amp;ドロップによって画像などのアセットをドロップできます。また、「**参照**」ボタンを使って、ローカルファイルシステムからファイルをアップロードすることも可能です。画像を追加すると、画像の下部に 3 つのボタンが表示されます。画像を追加すると、画像の下部に 3 つのボタンが表示されます。
   * **編集** - アセットエディターでアセットのレンディションを管理するには、「**編集**」をタップまたはクリックします。
   * **消去** - 現在選択されている画像を選択解除するには、「**消去**」をタップまたはクリックします。
   * **選択** - 「**選択**」オプションをタップまたはクリックすると、アセットフォルダーから別の画像を選択できます。

* **タイトル** - このオプションは、ヘッダーに見出しを追加するために使用します。定義済みのテキストはダイアログボックスに含まれ、ユーザーが変更できます。
* **リンク先** - **参照**&#x200B;アイコンから見出しをフォルダーにリンクすることができます。
* **説明** - 説明とは、特定の画像の目的に関する追加情報や説明を提供する簡単な説明文です。
* **サイズ (px)** - ピクセルを増減して画像の長さと幅を調整できます。

![accessibilitytab](/help/adaptive-forms/assets/header_accessibility.png)

* **代替テキスト** - このオプションは、視覚に障害のあるユーザー向けに、画像の代わりとなる短い説明文を入力するために使用されます。

* **画像は装飾画像** - 画像が支援テクノロジーによって無視される場合（したがってその代替テキストが不要な場合）はオンにします。これは、装飾画像にのみ適用されます。

### 「テキスト」タブ {#text-tab}

このセクションでは、ヘッダーに含めるテキストを入力できます。

## 関連記事 {#related-article}

* [AEM Sites ページまたはエクスペリエンスフラグメントでアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=ja)

* [スタンドアロンのアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=ja)

## 関連トピック {#see-also}

* [アコーディオン](/help/adaptive-forms/components/accordion.md)
* [ボタン](/help/adaptive-forms/components/button.md)
* [チェックボックス グループ](/help/adaptive-forms/components/checkbox-group.md)
* [日付選択](/help/adaptive-forms/components/date-picker.md)
* [ドロップダウンリスト](/help/adaptive-forms/components/drop-down.md)
* [メール入力](/help/adaptive-forms/components/email-input.md)
* [フォームコンテナ](/help/adaptive-forms/components/form-container.md)
* [ファイル添付](/help/adaptive-forms/components/file-attachment.md)
* [フッター](/help/adaptive-forms/components/footer.md)
* [水平タブ](/help/adaptive-forms/components/horizontal-tabs.md)
* [画像](/help/adaptive-forms/components/image.md)
* [数値入力](/help/adaptive-forms/components/number-input.md)
* [パネルコンテナ](/help/adaptive-forms/components/panel-container.md)
* [ラジオボタン](/help/adaptive-forms/components/radio-button.md)
* [リセットボタン](/help/adaptive-forms/components/reset-button.md)
* [送信ボタン](/help/adaptive-forms/components/submit-button.md)
* [電話入力](/help/adaptive-forms/components/telephone-input.md)
* [テキスト入力](/help/adaptive-forms/components/text-input.md)
* [テキスト](/help/adaptive-forms/components/text.md)
* [タイトル](/help/adaptive-forms/components/title.md)
* [ウィザード](/help/adaptive-forms/components/wizard.md)