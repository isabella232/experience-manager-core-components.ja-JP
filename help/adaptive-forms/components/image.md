---
title: アダプティブフォームのコアコンポーネント - 画像
description: アダプティブフォームの画像コアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: ht
source-wordcount: '1051'
ht-degree: 100%

---

# 画像 {#image-adaptive-forms-core-component}

アダプティブフォームの画像コンポーネントでは、フォームに画像を含めることができます。これらの画像を使用して、フォームの全体的なデザインを引き立てたり、追加情報を提供したり、ユーザーがフォームの目的を理解できるように視覚的な要素として機能させたりすることができます。画像コンポーネントを使用して、フォームにロゴ、写真またはグラフィックを追加できます。

アクセシビリティについては、視覚に障害があるユーザーのために、**代替テキスト**&#x200B;を画像に追加して、画像に代わる短い説明文を指定することが重要です。


**例**

![](/help/adaptive-forms/assets/image.png)


## 使用方法 {#reasons-to-use-image-in-a-form}

アダプティブフォームに画像コンポーネントを含める方がメリットが大きい理由は、次のようにいくつかあります。

* **ブランディング**：フォームを作成した組織のロゴや名前を表示することで、ブランドの認知度を上げ、信頼性を確立するのに役立ちます。

* **視覚要素**：画像は、ユーザーがフォームの目的を理解するのに役立つ視覚的な要素として機能し、ユーザーに追加情報を提供できます。

* **装飾**：フォームの全体的なデザインをより魅力的なものにすることができます。

* **ユーザーエクスペリエンス**：ユーザーがフォームフィールドにアクセスして入力する際に明確で直感的な方法を提供することで、フォームをより使いやすいものにすることができます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブフォームの画像コアコンポーネントの最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。


## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、訪問者の画像エクスペリエンスを簡単にカスタマイズできます。また、簡単に画像オプションを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

![「プロパティ」タブ](/help/adaptive-forms/assets/image_properties.png)

* **名前** - フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **タイトル** - タイトルを使用すると、フォーム内のコンポーネントを簡単に識別できます。デフォルトでは、コンポーネントの上にタイトルが表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

* **レコードのドキュメントのバインド参照** - このオプションを使用すると、アダプティブフォームフィールドをレコードのドキュメントフィールドに関連付けることができます。 ユーザーがアダプティブフォームのリンクされたフィールドに値を入力すると、その値は対応するレコードのドキュメントのリンクされたフィールドにも表示されます。 例えば、レコードのドキュメントのバインド参照を使用して、フォームに入力された顧客の ID に基づいて、レコードのドキュメントに顧客の名前と住所を表示することができます。 この方法で AEM Forms を使用してレコードのドキュメントを生成し、データを収集および管理するためのシームレスなユーザーエクスペリエンスを提供します。

* **説明** - 説明とは、特定の画像の目的に関する追加情報や説明を提供する簡単な説明文です。

* **ここにアセットをドロップ、またはアップロードするファイルを参照** - このオプションでは、マウスのドラッグ＆ドロップ操作で画像などのアセットをドロップできます。また、「**参照**」ボタンを使って、ローカルのファイルシステムからファイルをアップロードすることもできます。画像を追加すると、画像の下部に 3 つのボタンが表示されます。
   * **編集** - アセットエディターでアセットのレンディションを管理するには、「**編集**」をタップまたはクリックします。
   * **消去** - 現在選択されている画像を選択解除するには、「**消去**」をタップまたはクリックします。
   * **選択** - アセットフォルダーから別の画像を選択するには、「**選択**」オプションをタップまたはクリックします。

* **代替テキスト** - このオプションは、視覚に障害のあるユーザー向けに、画像の代わりとなる短い説明文を入力するために使用されます。

* **コンポーネントを非表示** - フォームでコンポーネントを非表示にするには、このオプションを選択します。このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。 これは、ユーザーが表示する必要のない情報や直接変更した情報を保存する必要がある場合に役立ちます。

* **読み取り専用** - コンポーネントを編集不可にするには、このオプションを選択します。ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

## デザインダイアログ {#design-dialog}

デザインダイアログでは、画像コンポーネントの CSS スタイルを定義および管理できます。

### 「スタイル」タブ {#styles-tab}

タブを使用して、コンポーネントの CSS スタイルの定義と管理を行います。アダプティブフォームの画像コアコンポーネントは、AEM の[スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

![デザインダイアログ](/help/adaptive-forms/assets/image_designdialog.png)

**デフォルトの CSS クラス**：アダプティブフォームの画像コアコンポーネントのデフォルト CSS クラスを指定できます。

**許可されたスタイル**：スタイルを表す名前と CSS クラスを指定してスタイルを定義します。例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight: bold」を指定できます。アダプティブフォームエディターでアダプティブフォームにこれらのスタイルを使用または適用できます。スタイルを適用するには、アダプティブフォームエディターでスタイルを適用するコンポーネントを選択し、「プロパティ」ダイアログに移動して「**スタイル**」ドロップダウンリストから希望のスタイルを選択します。スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新して変更を保存します。

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
* [ヘッダー](/help/adaptive-forms/components/header.md)
* [水平タブ](/help/adaptive-forms/components/horizontal-tabs.md)
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