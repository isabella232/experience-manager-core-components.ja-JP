---
title: アダプティブフォームのアコーディオン
description: アコーディオンを使用すると、長いフォームや複雑なフォームを、より小さく、管理しやすいセクションに分割して整理し、簡略化できます。
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: ht
source-wordcount: '2088'
ht-degree: 100%

---

# アコーディオンコンポーネント {#accordion-component-adaptive-forms-core-component}

アコーディオンコアコンポーネントを使用すると、アダプティブフォーム内で展開と折りたたみが可能なセクションを作成できます。 多くの場合、長いフォームや複雑なフォームを、より小さく、管理しやすいセクションに分けて整理し、簡略化するために使用されます。アコーディオンの各セクションは通常、ヘッダーで表示されます。ヘッダーをクリックすると、対応するコンテンツを展開または折りたたむことができます。任意のコアコンポーネントをコンテンツにすることができます。

## 使用方法 {#usage}

アダプティブフォームにアコーディオンを含めると有益な理由はいくつかあります。以下に例を示します。

* **スペースの節約**：フォームのセクションを展開したり折りたたんだりして、すべてのフォームフィールドを一度に表示するのに必要なスペースを減らすことができます。

* **ナビゲーション**：階層的なナビゲーション構造を作成し、必要なフォームフィールドをユーザーが見つけやすくすることができます。

* **ユーザーエクスペリエンス**：ユーザーがフォームフィールドにアクセスして入力する際に、使いやすく直感的な方法を提供できます。

* **長いフォーム**：アコーディオンは長いフォームに最適なコンポーネントです。ユーザーは多くの情報を一度に提示されることなく、1 つのセクションに集中できます。

以下を使用できます。

* アコーディオンコンポーネントのプロパティを指定するための[設定ダイアログ](#configure-dialog)

* アコーディオンのパネルの順序を定義するための[「パネルを選択」ポップオーバー](#select-panel-popover)。これを使用することで、作成者は指定した順序でパネルを配置できます。

* [デザインダイアログ](#design-dialog)で、フォームの作成者が特定の機能を有効／無効にするためのオプション。例えば、作成者がフォームの特定のフィールドやセクションを無効にしたい場合は、これらのオプションでフォームのデザインや機能をより詳細に制御して、組織のニーズに合わせて調整されたフォームを簡単に作成できます。

設定ダイアログ、「選択パネル」ポップオーバーおよびデザインダイアログは、すべてコアコンポーネントの一部です。これらのコンポーネントは、フォームのオーサリングを容易にし、複雑なフォームを効率的に作成するために構築されています。

## バージョンと互換性 {#version-and-compatibility}


アダプティブフォームのアコーディオンコアコンポーネントは、コアコンポーネント 2.0.4 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEMの互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | <br>[リリース 2.0.4](/help/versions.md) 以降と互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)ドキュメントをご覧ください。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アコーディオンコンポーネントの最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、訪問者によるアコーディオンの操作を簡単にカスタマイズできます。また、アコーディオンのアイテム、パネル、動作、外観を簡単に定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 「基本」タブ {#basic-tab}

![「基本」タブ](/help/adaptive-forms/assets/acc-basic.png)

* **名前** - フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **タイトル** - タイトルを使用すると、フォーム内のコンポーネントを簡単に識別できます。デフォルトでは、コンポーネントの上にタイトルが表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

* **タイトルを非表示** - コンポーネントのタイトルを非表示にするには、このオプションを選択します。

* **フォームの送信時に子コンポーネントのデータをグループ化（オブジェクトにデータを含める）** - このオプションを選択すると、子コンポーネントのデータが親コンポーネントの JSON オブジェクト内にネストされます。ただし、このオプションを選択しないと、送信した JSON データは、親コンポーネントのオブジェクトを持たないフラットな構造になります。例：

   * このオプションを選択すると、子コンポーネント（番地、市区町村、郵便番号など）のデータが、JSON オブジェクトとして親コンポーネント（住所）内にネストされます。これにより、階層構造が作成され、データは親コンポーネントの下に整理されます。

     送信したデータの構造：

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   * このオプションを選択しないと、送信した JSON データは、親コンポーネント（住所）のオブジェクトを持たないフラットな構造になります。すべてのデータは同じレベルにあり、階層構造はありません。


     送信したデータの構造：

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

* **レイアウト** - ウィザードには固定レイアウト（シンプル）または柔軟なレイアウト（レスポンシブグリッド）を使用できます。 シンプルなレイアウトでは、すべてを固定した状態に保ち、レスポンシブグリッドでは、必要に応じてコンポーネントの位置を調整できます。例えば、レスポンシブグリッドを使用して、「名」、「ミドルネーム」、「姓」を 1 行にフォーム内で整列できます。

* **バインド参照** - バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。バインド参照を使用すると、データをフォームフィールドに動的にバインドして、フォームにデータソースの最新のデータを表示できます。 例えば、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示できます。 さらに、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Forms で外部データソースとやり取りするフォームを作成し、データの収集と管理においてシームレスなユーザーエクスペリエンスを提供できます。

* **コンポーネントを非表示** - フォームでコンポーネントを非表示にするには、このオプションを選択します。このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。 これは、ユーザーが表示する必要のない情報や直接変更した情報を保存する必要がある場合に役立ちます。

* **コンポーネントの無効化** - コンポーネントを無効にする場合は、このオプションを選択します。 エンドユーザーは、無効になっているコンポーネントをアクティブにしたり、編集したりすることはできません。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

### アコーディオンを繰り返す {#repeat-accordion}

![繰り返しアコーディオン](/help/adaptive-forms/assets/repeat-accordion.png)

繰り返しオプションを使用すると、アコーディオンパネルとその子コンポーネントの複製、最小繰り返し回数と最大繰り返し回数の定義、フォーム内の類似セクションの複製を簡単に行うことができます。アコーディオンコンポーネントを操作してその設定にアクセスする際には、次のオプションが表示されます。

* **アコーディオンを繰り返し可能にする**：ユーザーが繰り返し機能を有効または無効にできる切替スイッチ機能。
* **最小繰り返し回数**：アコーディオンパネルを繰り返し可能な最小回数を設定します。値 0 は、アコーディオンパネルが繰り返されないことを示します。デフォルト値は 0 です。
* **最大繰り返し回数**：アコーディオンパネルを繰り返し可能な最大回数を設定します。デフォルトでは、この値は無制限です。

アコーディオン内で繰り返し可能なセクションを効果的に管理するには、[繰り返し可能なセクションを含むフォームの作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=ja)の記事に記載されている手順に従います。

### 「項目」タブ {#items-tab}

![「項目」タブ](/help/adaptive-forms/assets/acc-items.png)

「追加」ボタンを使用すると、「コンポーネント選択」ウィンドウからパネルとして追加するコンポーネントを選択できます。コンポーネントを追加すると、次のオプションが表示されます。

* **アイコン** - アイコンは、リスト内のパネルのコンポーネントを識別します。アイコンの上にマウスポインターを置くと、完全なコンポーネント名がツールチップとして表示されます。
* **説明** - パネルのテキストとして使用される説明。デフォルトでは、パネルに対してコンポーネントの名前が選択されます。
* **削除** - タップまたはクリックすると、アコーディオンコンポーネントからパネルを削除できます。
* **並べ替え** - タップまたはクリックしてドラッグすると、パネルを並べ替えることができます。

### 「ヘルプコンテンツ」タブ {#help-content}

![「ヘルプコンテンツ」タブ](/help/adaptive-forms/assets/acc-helpcontent.png)

* **短い説明** - 短い説明は、特定のフォームフィールドの目的に関する追加の情報や説明を提供する簡単な説明文です。これにより、ユーザーは、フィールドに入力するデータの種類を理解しやすくなります。また、入力された情報が有効で目的の条件を満たしていることを確認できるように、ガイドラインや例を提供できます。デフォルトでは、短い説明は非表示になっています。 「**短い説明を常に表示**」オプションを有効にすると、コンポーネントの下に説明が表示されます。

* **短い説明を常に表示** - このオプションを有効にすると、コンポーネントの下に短い説明が表示されます。

* **ヘルプテキスト** - ヘルプテキストとは、フォームフィールドの正しい入力を支援するためにユーザーに提供される追加の情報やガイダンスを指します。コンポーネントの横に配置されているヘルプアイコン（i）をクリックすると表示されます。 ユーザーがフィールドの要件や制約を理解できるように設計されているヘルプテキストは、フォームフィールドのラベルやプレースホルダーテキストよりも詳細な情報を提供できます。また、フォームへの入力をより簡単かつ正確にするための提案や例を提供することも可能です。

### 「アクセシビリティ」タブ {#accessibility}

![「アクセシビリティ」タブ](/help/adaptive-forms/assets/acc-accessisbilty.png)

「**アクセシビリティ** 」タブでは、コンポーネントの [ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)ラベルの値を設定できます。スクリーンリーダー用のテキストを使用する場合は、次の様々なオプションを使用できます。

* **スクリーンリーダー用テキスト** - スクリーンリーダー用テキストとは、視覚に障害のあるユーザーが使用する支援テクノロジー（スクリーンリーダーなど）によって読み上げられる追加のテキストを指します。 このテキストでは、フォームフィールドの目的に関するオーディオの説明が提供され、フィールドのタイトル、説明、名前および関連するメッセージ（カスタムテキスト）に関する情報を含めることができます。スクリーンリーダー用のテキストを使用すると、視覚に障害のあるユーザーを含むすべてのユーザーがフォームに確実にアクセスして、フォームフィールドとその要件を完全に理解できるようになります。


   * **カスタムテキスト**：ARIA アクセシビリティラベルにカスタムテキストを使用する場合は、このオプションを選択します。 このオプションを選択すると、「カスタムテキスト」ダイアログボックスが表示されます。関連情報は、「カスタムテキスト」ダイアログボックスで追加できます。
   * **説明**：ARIA アクセシビリティラベルの説明を使用する場合は、このオプションを選択します。
   * **タイトル**：ARIA アクセシビリティラベルのタイトルを使用する場合は、このオプションを選択します。
   * **名前**：ARIA アクセシビリティラベルの名前を使用する場合は、このオプションを選択します。
   * **なし**：ARIA アクセシビリティラベルに追加しない場合は、このオプションを選択します。

<!--

### Properties Tab {#properties-tab}

![Properties tab of the edit dialog of the Accordion Component](/help/assets/accordion-edit-properties.png)

*   **Single item expansion** - When selected, this option forces a single accordion item to be expanded at a time. Expanding one item will then collapse all others.
*   **Expanded items** - This option defines the items that are expanded by default when the page is loaded.
    * When **Single item expansion** is selected, one panel must be selected. By default the first panel is selected.
    * When **Single item expansion** is not selected, this option is a multi-select and is optional.
*   **ID** - This option allows to control the unique identifier of the component in the HTML and in the [Data Layer](/help/developing/data-layer/overview.md).
    * If left blank, a unique ID is automatically generated for you and can be found by inspecting the resulting page.
    * If an ID is specified, it is the responsibility of the author to make sure that it is unique.
    * Changing the ID can have an impact on CSS, JS and Data Layer tracking.

## Select Panel Popover {#select-panel-popover}

The **Select Panel** option (![Select panel icon](/help/assets/select-panel-icon.png)) on the component toolbar enables content authors to modify the panels in an accordion with ease. By selecting this option, the author can switch to a different panel for editing and rearrange the order of the panels in the accordion. The configured panels will be displayed in a drop-down menu for the author to choose from. This feature optimizes the editing process and makes it user-friendly for content authors.

![Select panel popover](/help/assets/select-panel-popover.png)


* The panels are displayed in a numbered list, reflecting the assigned arrangement.
* Each panel is listed with its component type in bold, followed by a brief description in lighter font.
* By clicking or tapping on a panel in the drop-down, you can easily switch the view in the editor to that specific panel.
* To rearrange the panels, simply use the drag handles to move them into the desired order. -->

## デザインダイアログ {#design-dialog}

デザインダイアログでは、テンプレート作成者がデフォルトでの表示方法を制御できます。アダプティブフォームのアコーディオンコンポーネントでは、以下を設定できます。

* 許可され、デフォルトとして設定される HTML の見出し要素のタイプ（H1、H2、H3 など）
* フォーム作成者がアダプティブフォームエディターでアコーディオンに追加できるコアコンポーネント
* アダプティブフォームエディターのアコーディオンコンポーネントのプロパティダイアログで適用できる、スタイル（CSS クラス）のシンプルな名前。

この名前を使用することで、フォームの作成やカスタマイズのプロセスが、分かりやすく効率的になります。

### 「プロパティ」タブ {#properties-tab-design}

「プロパティ」タブを使用すると、テンプレート作成者はフォーム作成者のために、許可されるデフォルトの HTML 見出し要素と設定できます。

![デザインダイアログの「プロパティ」タブ](/help/assets/accordion-design-properties.png)

* **許可される見出し要素**：複数のオプションを含むドロップダウンリスト。作成者がアコーディオンで使用できる見出し要素をテンプレート作成者が選択できます。

* **デフォルトの見出し要素**：アコーディオンコンポーネントのデフォルトの見出し要素をドロップダウンリストから選択します。

### 「許可されたコンポーネント」タブ {#allowed-components-tab}

「**許可されたコンポーネント**」タブでは、アダプティブフォームエディター内のアコーディオンコンポーネントのパネルに項目として追加できるコンポーネントをテンプレートエディターで設定できます。

### 「スタイル」タブ {#styles-tab}

デザインダイアログは、コンポーネントの CSS スタイルを定義および管理するために使用します。 アダプティブフォームのアコーディオンコアコンポーネントは、AEM の[スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

**デフォルトの CSS クラス**：アコーディオンコンポーネントのデフォルトの CSS クラスを指定できます。

**許可されたスタイル**：スタイルを表す名前と CSS クラスを指定してスタイルを定義します。 例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight: bold」を指定できます。アダプティブフォームエディターでアダプティブフォームにこれらのスタイルを使用または適用できます。スタイルを適用するには、アダプティブフォームエディターでスタイルを適用するコンポーネントを選択し、「プロパティ」ダイアログに移動して「**スタイル**」ドロップダウンリストから希望のスタイルを選択します。スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新して変更を保存します。


<!--- 

The design dialog allows the template author to define the options available to the content author who uses the Accordion Component and the defaults set when placing the Accordion Component.


### Properties Tab {#properties-tab-design}

![Design dialog properties tab](/help/assets/accordion-design-properties.png)

* **Allowed Heading Elements** - This multi-select drop-down defines the accordion item heading HTML elements that are allowed to be selected by an author.
* **Default Heading Element** - This drop-down defines the default accordion item heading HTML element.

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as items to panels in the Accordion Component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### Styles Tab {#styles-tab}

The Accordion Component supports the AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

The Accordion Component supports the [Adobe Client Data Layer.](/help/developing/data-layer/overview.md) 


-->

## 関連記事 {#related-article}

* [AEM Sites ページまたはエクスペリエンスフラグメントでアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=ja)

* [スタンドアロンのアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=ja)

## 関連トピック {#see-also}

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
* [テキスト](/help/adaptive-forms/components/text.md)
* [タイトル](/help/adaptive-forms/components/title.md)
* [ウィザード](/help/adaptive-forms/components/wizard.md)