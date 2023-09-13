---
title: アダプティブフォームのコアコンポーネント - テキスト
description: アダプティブフォームのテキストコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
exl-id: b8de68e4-ca0d-4ae5-9a04-104cc617f1be
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: ht
source-wordcount: '885'
ht-degree: 100%

---

# テキスト {#text-adaptive-forms-core-component}

アダプティブフォームのテキストとは、ユーザーが読むためにフォームに表示されるコンテンツを表します。 これには、テキストフィールドなどのフォーム要素のグループにラベルを付けるために使用されるテキストや、ユーザーに提供される追加の説明や情報などを使用できます。

これにより、フォームの構造を論理セクションに分割して、フォームを理解して完了しやすくすることができます。さらに、関連付けられている要素の簡単な説明を提供するアクセシビリティの目的でも使用できます。このようなテキストフィールドは、通常はフォームコンポーネントの近く（前後など）に表示されます。

**例**

![](/help/adaptive-forms/assets/text.png)

## 使用方法 {#reasons-to-use-text-label}

フォーム内でテキストを使用する理由はいくつかあります。

* **説明の提供**：テキストを使用して、フォームの入力方法や必要な情報に関する説明を提供できます。

* **コンテキストの提供**：テキストを使用して、フォームの目的や情報を収集している組織など、フォームのコンテキストを提供できます。

* **フォームを論理セクションに分割**：テキストを使用してフォームを論理セクションに分割することで、フォームを理解して完了しやすくすることができます。

* **ブランディングとアイデンティティ**：組織の名前をフォームに含めるなど、ブランディングやアイデンティティを示す目的でテキストを使用できます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブフォームのテキストコアコンポーネントの最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者のテキストエクスペリエンスを簡単にカスタマイズできます。また、シームレスなユーザーエクスペリエンスを実現するために、簡単にテキストオプションを定義できます。

![「基本」タブ](/help/adaptive-forms/assets/text_properties.png)

* **名前** - フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **バインド参照** - バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。バインド参照を使用すると、データをフォームフィールドに動的にバインドして、フォームにデータソースの最新のデータを表示できます。 例えば、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示できます。 さらに、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Forms で外部データソースとやり取りするフォームを作成し、データの収集と管理においてシームレスなユーザーエクスペリエンスを提供できます。
* **コンポーネントを非表示** - フォームでコンポーネントを非表示にするには、このオプションを選択します。このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。 これは、ユーザーが表示する必要のない情報や直接変更した情報を保存する必要がある場合に役立ちます。
* **読み取り専用** - コンポーネントを編集不可にするには、このオプションを選択します。ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。


## デザインダイアログ {#design-dialog}

デザインダイアログでは、テキストコンポーネントの CSS スタイルを定義および管理できます。

### 「スタイル」タブ {#styles-tab}

タブを使用して、コンポーネントの CSS スタイルの定義と管理を行います。アダプティブフォームのテキストコアコンポーネントは、AEM の[スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

![デザインダイアログ](/help/adaptive-forms/assets/reset_designdialog.png)

* **デフォルトの CSS クラス**：アダプティブフォームのテキストコアコンポーネントのデフォルト CSS クラスを指定できます。

* **許可されたスタイル**：スタイルを表す名前と CSS クラスを指定してスタイルを定義できます。例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight: bold」を指定できます。アダプティブフォームエディターでアダプティブフォームにこれらのスタイルを使用または適用できます。スタイルを適用するには、アダプティブフォームエディターでスタイルを適用するコンポーネントを選択し、「プロパティ」ダイアログに移動して「**スタイル**」ドロップダウンリストから希望のスタイルを選択します。スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新して変更を保存します。

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
* [画像](/help/adaptive-forms/components/image.md)
* [数値入力](/help/adaptive-forms/components/number-input.md)
* [パネルコンテナ](/help/adaptive-forms/components/panel-container.md)
* [ラジオボタン](/help/adaptive-forms/components/radio-button.md)
* [リセットボタン](/help/adaptive-forms/components/reset-button.md)
* [送信ボタン](/help/adaptive-forms/components/submit-button.md)
* [電話入力](/help/adaptive-forms/components/telephone-input.md)
* [テキスト入力](/help/adaptive-forms/components/text-input.md)
* [タイトル](/help/adaptive-forms/components/title.md)
* [ウィザード](/help/adaptive-forms/components/wizard.md)