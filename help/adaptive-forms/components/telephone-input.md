---
title: アダプティブフォームのコアコンポーネント - 電話入力
description: アダプティブフォームの電話入力コアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
exl-id: d06179ac-04bd-4af4-b6ac-c4c78086058c
source-git-commit: 59cd9d65bf4c1be6ab2eaf15bbb747b532863fdd
workflow-type: tm+mt
source-wordcount: '1791'
ht-degree: 100%

---

# 電話入力 {#telephone-input-adaptive-forms-core-component}

アダプティブフォームの電話入力コアコンポーネントを使用すると、ユーザーは電話番号を入力できます。 電話の入力フィールドには、電話番号に関連するモバイルデバイスのキーボードが表示されます。 電話番号の形式と説明を指定するために、「パターン」や「プレースホルダー」などの追加の属性を使用してカスタマイズできます。

電話入力フィールドは、連絡手段として電話番号が必要な連絡先フォーム、登録フォーム、その他のフォームで一般的に使用されます。 また、「pattern」属性に基づいて、ブラウザーが電話番号の長さや形式などの特定の制約を適用できるので、ユーザーが必ず有効な電話番号を入力するようにもできます。

## 使用方法 {#reasons-to-use-telephone-input}

アダプティブフォームで電話入力フィールドを使用する一般的な理由は次のとおりです。

* **連絡先情報**：電話入力フィールドは通常、連絡手段としてユーザの電話番号を収集するために使用されます。

* **データの正確性の向上**：電話入力フィールドを使用すると、フォームで電話番号の形式に特定の制約を適用して、入力されるデータを正確かつ完全なものにすることができます。

* **ユーザーエクスペリエンスの向上**：電話入力フィールドは、ユーザが電話番号を入力する際の明確で直感的な方法を提供し、ユーザが連絡先情報を素早く簡単に入力できるようにすることで、ユーザエクスペリエンスを向上させます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブフォームの電話入力コアコンポーネントの最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/telephoneinput/v1/telephoneinput) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、訪問者による電話入力の操作を簡単にカスタマイズできます。 また、電話入力オプションを簡単に定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

![「基本」タブ](/help/adaptive-forms/assets/telephoneinput_basictab.png)

* **名前** - フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **タイトル** - タイトルを使用すると、フォーム内のコンポーネントを簡単に識別できます。デフォルトでは、コンポーネントの上にタイトルが表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

* **タイトルを非表示** - コンポーネントのタイトルを非表示にするには、このオプションを選択します。

* **プレースホルダーテキスト** - フォームコンポーネント内のプレースホルダーテキストとは、入力フィールド内に表示される短いラベルまたはプロンプトのことで、そのフィールドに入力する必要のある情報の種類に関するヒントとしてユーザーに表示されます。ユーザーがフィールドへの入力を開始するとプレースホルダーテキストが消え、フィールドが空のままの場合は再び表示されます。ユーザーに視覚的なキューを提供しますが、フィールドの永続的なラベルや値としては機能しません。

* **バインド参照** - バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。バインド参照を使用すると、データをフォームフィールドに動的にバインドして、フォームにデータソースの最新のデータを表示できます。 例えば、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示できます。 さらに、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Forms で外部データソースとやり取りするフォームを作成し、データの収集と管理においてシームレスなユーザーエクスペリエンスを提供できます。

* **コンポーネントを非表示** - フォームでコンポーネントを非表示にするには、このオプションを選択します。このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。 これは、ユーザーが表示する必要のない情報や直接変更した情報を保存する必要がある場合に役立ちます。

* **コンポーネントの無効化** - コンポーネントを無効にする場合は、このオプションを選択します。 エンドユーザーは、無効になっているコンポーネントをアクティブにしたり、編集したりすることはできません。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

* **読み取り専用** - コンポーネントを編集不可にするには、このオプションを選択します。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

* **デフォルト値** - このオプションを使用すると、フォームフィールドにデフォルト値を追加できます。「**無効なコンポーネント**」または「**読み取り専用コンポーネント**」が選択されている場合は、デフォルト値が画面に表示されます。ユーザーがフォームフィールドに値を入力しない場合、この値はフォーム送信時に送信されます

### 「検証」タブ {#validation-tab}

![「検証」タブ](/help/adaptive-forms/assets/telephoneinput_validationtab.png)

* **必須** - コンポーネントをアダプティブフォームに表示する場合は、このオプションを選択します。 このオプションが選択されていると、「**基本**」タブの「**コンポーネントを非表示**」または「**コンポーネントの無効化**」は選択できません。

* **エラーメッセージ** - このオプションを使用すると、「**必須**」チェックボックスがオンになっており、フィールドが空白の場合に表示されるメッセージを入力できます。

* **スクリプト検証メッセージ** - このオプションを使用すると、スクリプトの検証が失敗した場合に表示するメッセージを入力できます。

* **最大文字数** - このオプションを使用すると、コンポーネントで許可する最大文字数を指定できます。「**最大文字数**」に指定した値を超えて文字を入力すると、エラーメッセージが画面に表示されます。**最大文字数のエラーメッセージ**&#x200B;ダイアログボックスでは、カスタムエラーメッセージを追加できます。

* **最大文字数のエラーメッセージ** - **最大文字数のエラーメッセージ**&#x200B;ダイアログボックスでは、「**最大文字数**」オプションで指定した値を超える文字数を入力したときに表示されるカスタムのエラーメッセージを追加できます。

* **最小文字数** - このオプションを使用すると、フィールドで許可する最小文字数を指定できます。「**最小文字数**」に指定した値を下回る文字を入力すると、エラーメッセージが画面に表示されます。**最小文字数のエラーメッセージ**&#x200B;ダイアログボックスでは、カスタムのエラーメッセージを追加できます。

* *最小文字数のエラーメッセージ** - **最小文字数エラーメッセージ**&#x200B;ダイアログボックスでは、「**最小文字数**」オプションで指定した値を下回る文字数を入力した場合に表示されるカスタムのエラーメッセージを追加できます。

「**検証パターン**」オプションでは、入力した電話番号を検証するパターンを指定できます。入力された電話番号は、「**パターン**」オプションで指定された値に対して検証されます。電話番号が「**パターン**」オプションで指定された値での検証に失敗すると、エラーメッセージが画面に表示されます。

* **パターン** - 電話番号に対して許可される検証パターンを指定できます。ここでは正規表現も使用できます。

* **エラーメッセージ** - 入力した電話番号が、「**パターン**」オプションで指定された値に対する検証に失敗した場合に画面に表示されるメッセージを追加できます。

### 「ヘルプコンテンツ」タブ {#help-content-tab}

![「ヘルプコンテンツ」タブ](/help/adaptive-forms/assets/telephoneinput_helptab.png)

* **短い説明** - 短い説明は、特定のフォームフィールドの目的に関する追加の情報や説明を提供する簡単な説明文です。これにより、ユーザーは、フィールドに入力するデータの種類を理解しやすくなります。また、入力された情報が有効で目的の条件を満たしていることを確認できるように、ガイドラインや例を提供できます。デフォルトでは、短い説明は非表示になっています。 「**短い説明を常に表示**」オプションを有効にすると、コンポーネントの下に説明が表示されます。

* **短い説明を常に表示** - このオプションを有効にすると、コンポーネントの下に短い説明が表示されます。

* **ヘルプテキスト** - ヘルプテキストとは、フォームフィールドの正しい入力を支援するためにユーザーに提供される追加の情報やガイダンスを指します。コンポーネントの横に配置されているヘルプアイコン（i）をクリックすると表示されます。 ユーザーがフィールドの要件や制約を理解できるように設計されているヘルプテキストは、フォームフィールドのラベルやプレースホルダーテキストよりも詳細な情報を提供できます。また、フォームへの入力をより簡単かつ正確にするための提案や例を提供することも可能です。

### 「アクセシビリティ」タブ {#accessibility-tab}

![「アクセシビリティ」タブ](/help/adaptive-forms/assets/telephoneinput_accessibilitytab.png)

**スクリーンリーダー用テキスト** - スクリーンリーダー用テキストとは、視覚に障害のあるユーザーが使用する、支援テクノロジー（スクリーンリーダーなど）によって読み上げられる追加のテキストを指します。このテキストでは、フォームフィールドの目的に関するオーディオの説明が提供され、フィールドのタイトル、説明、名前および関連するメッセージ（カスタムテキスト）に関する情報を含めることができます。スクリーンリーダー用のテキストを使用すると、視覚に障害のあるユーザーを含むすべてのユーザーがフォームに確実にアクセスして、フォームフィールドとその要件を完全に理解できるようになります。

## デザインダイアログ {#design-dialog}

デザインダイアログでは、電話入力コンポーネントの CSS スタイルを定義および管理できます。

### 「スタイル」タブ {#styles-tab}

タブを使用して、コンポーネントの CSS スタイルの定義と管理を行います。アダプティブフォームの電話入力コアコンポーネントは、AEM の[スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

![デザインダイアログ](/help/adaptive-forms/assets/telephoneinput_designdialog.png)

* **デフォルトの CSS クラス**：アダプティブフォームの電話入力コアコンポーネントのデフォルト CSS クラスを指定できます。

* **許可されたスタイル**：スタイルを表す名前と CSS クラスを指定してスタイルを定義します。例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight: bold」を指定できます。アダプティブフォームエディターでアダプティブフォームにこれらのスタイルを使用または適用できます。スタイルを適用するには、アダプティブフォームエディターでスタイルを適用するコンポーネントを選択し、「プロパティ」ダイアログに移動して「**スタイル**」ドロップダウンリストから希望のスタイルを選択します。スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新して変更を保存します。

### 「形式」タブ {#format-tab}

「形式」タブでは、デフォルトとカスタムの形式を指定できます。

![「形式」タブ](/help/adaptive-forms/assets/telephoneinput_format.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->


>[!MORELIKETHIS]
>
>* [アコーディオン](/help/adaptive-forms/components/accordion.md)
>* [ボタン](/help/adaptive-forms/components/button.md)
>* [チェックボックスグループ](/help/adaptive-forms/components/checkbox-group.md)
>* [日付選択](/help/adaptive-forms/components/date-picker.md)
>* [ドロップダウンリスト](/help/adaptive-forms/components/drop-down.md)
>* [メール入力](/help/adaptive-forms/components/email-input.md)
>* [フォームコンテナ](/help/adaptive-forms/components/form-container.md)
>* [ファイル添付](/help/adaptive-forms/components/file-attachment.md)
>* [フッター](/help/adaptive-forms/components/footer.md)
>* [ヘッダー](/help/adaptive-forms/components/header.md)
>* [水平タブ](/help/adaptive-forms/components/horizontal-tabs.md)
>* [画像](/help/adaptive-forms/components/image.md)
>* [数値入力](/help/adaptive-forms/components/number-input.md)
>* [パネルコンテナ](/help/adaptive-forms/components/panel-container.md)
>* [ラジオボタン](/help/adaptive-forms/components/radio-button.md)
>* [リセットボタン](/help/adaptive-forms/components/reset-button.md)
>* [送信ボタン](/help/adaptive-forms/components/submit-button.md)
>* [テキスト入力](/help/adaptive-forms/components/text-input.md)
>* [テキスト](/help/adaptive-forms/components/text.md)
>* [タイトル](/help/adaptive-forms/components/title.md)
>* [ウィザード](/help/adaptive-forms/components/wizard.md)

>[!MORELIKETHIS]
>
>* [アコーディオン](/help/adaptive-forms/components/accordion.md)
>* [ボタン](/help/adaptive-forms/components/button.md)
>* [チェックボックスグループ](/help/adaptive-forms/components/checkbox-group.md)
>* [日付選択](/help/adaptive-forms/components/date-picker.md)
>* [ドロップダウンリスト](/help/adaptive-forms/components/drop-down.md)
>* [メール入力](/help/adaptive-forms/components/email-input.md)
>* [フォームコンテナ](/help/adaptive-forms/components/form-container.md)
>* [ファイル添付](/help/adaptive-forms/components/file-attachment.md)
>* [フッター](/help/adaptive-forms/components/footer.md)
>* [ヘッダー](/help/adaptive-forms/components/header.md)
>* [水平タブ](/help/adaptive-forms/components/horizontal-tabs.md)
>* [画像](/help/adaptive-forms/components/image.md)
>* [数値入力](/help/adaptive-forms/components/number-input.md)
>* [パネルコンテナ](/help/adaptive-forms/components/panel-container.md)
>* [ラジオボタン](/help/adaptive-forms/components/radio-button.md)
>* [リセットボタン](/help/adaptive-forms/components/reset-button.md)
>* [送信ボタン](/help/adaptive-forms/components/submit-button.md)
>* [テキスト入力](/help/adaptive-forms/components/text-input.md)
>* [テキスト](/help/adaptive-forms/components/text.md)
>* [タイトル](/help/adaptive-forms/components/title.md)
>* [ウィザード](/help/adaptive-forms/components/wizard.md)

## 関連トピック {#see-also}

{{see-also}}