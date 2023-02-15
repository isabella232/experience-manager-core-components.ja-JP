---
title: アダプティブフォームアコーディオン
description: アコーディオンを使用すると、長いフォームや複雑なフォームを、より小さく、管理しやすいセクションに分割して整理し、簡略化できます。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 4%

---

# アコーディオンコンポーネント  {#accordion-component-adaptive-forms-core-component}

アコーディオンコアコンポーネントを使用すると、アダプティブフォーム内で拡張可能で折りたたみ可能なセクションを作成できます。 長いフォームや複雑なフォームを、より小さく、管理しやすいセクションに分けて整理し、簡略化するためによく使用されます。 アコーディオンの各セクションは、通常、ヘッダーで表されます。ヘッダーをクリックすると、対応するコンテンツを展開または折りたたむことができます。 任意のコアコンポーネントをコンテンツにすることができます。

## 使用方法 {#usage}

アダプティブフォームにアコーディオンを含めると有益な理由はいくつかあります。以下に例を示します。

* **スペースを節約**:アコーディオンを使用すると、フォームのセクションを展開したり折りたたんだりできるので、すべてのフォームフィールドを一度に表示するのに必要なスペースを減らすことができます。

* **ナビゲーション**:アコーディオンを使用して、階層的なナビゲーション構造を作成し、必要なフォームフィールドをユーザーが見つけやすくすることができます。

* **ユーザーエクスペリエンス**:アコーディオンを使用すると、ユーザーがフォームフィールドにアクセスして入力する際に使いやすく直感的な方法を提供し、より使いやすくすることができます。

* **ロングForms**:アコーディオンは長いフォームを処理するのに最適なコンポーネントです。多くの情報を一度に処理しようとするのではなく、1 つのセクションに集中できるからです。

以下を使用できます。

* この [設定ダイアログ](#configure-dialog) アコーディオンコンポーネントのプロパティを指定するには、次の手順を実行します。

* この [「パネルを選択」ポップオーバー](#select-panel-popover)  ：アコーディオンのパネルの順序を定義します。 これにより、作成者はパネルが表示される順序にパネルを配置できます。

* フォーム作成者が [デザインダイアログ](#design-dialog). 例えば、フォームの特定のフィールドやセクションを無効にするよう作成者が選択する場合があります。 これらのオプションを使用すると、作成者はフォームのデザインと機能をより詳細に制御でき、組織の特定のニーズに合わせて調整されたフォームを簡単に作成できます。

設定ダイアログ、選択パネルポップオーバーおよびデザインダイアログは、すべてコアコンポーネントの一部です。これらのコンポーネントは、フォームのオーサリングを容易にし、複雑なフォームを効率的に作成するために構築されています。

## バージョンと互換性 {#version-and-compatibility}


アダプティブFormsアコーディオンコアコンポーネントは、コアコンポーネント 2.0.4 の一部として 2023 年 2 月にリリースされました。次の表に、サポートされているすべてのバージョン、AEMの互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | 互換性あり<br>[リリース 2.0.4](/help/versions.md) 以降 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、 [コアコンポーネントのバージョン](/help/versions.md) 文書。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アコーディオンコンポーネントの最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](/help/developing/overview.md).

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者に対するアコーディオンエクスペリエンスを簡単にカスタマイズできます。 また、アコーディオンアイテム、パネル、動作、外観を簡単に定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 基本タブ {#basic-tab}

![「基本」タブ](/help/adaptive-forms/assets/accordion_basictab.png)

* **名前**  — フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **タイトル**  — タイトルを使用すると、フォーム内のコンポーネントを簡単に識別でき、デフォルトでは、タイトルがコンポーネントの上に表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

* **タイトルを非表示**  — コンポーネントのタイトルを非表示にするには、このオプションを選択します。

* **オブジェクト内でデータを折り返す** - 「オブジェクトでデータを折り返し」を選択して、ウィザードのフィールドデータを JSON オブジェクト内に配置します。 選択されていない場合、送信データ JSON はウィザードのフィールド用のフラット構造を持ちます。

* **レイアウト**  — ウィザードには固定レイアウト（シンプル）または柔軟なレイアウト（レスポンシブグリッド）を使用できます。 シンプルなレイアウトでは、すべてを固定した状態に保ち、レスポンシブグリッドでは、必要に応じてコンポーネントの位置を調整できます。 例えば、レスポンシブグリッドを使用して、「名」、「ミドルネーム」、「姓」を 1 行にフォーム内で整列させます。

* **バインド参照**  — バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。 連結参照を使用すると、データをフォームフィールドに動的に連結して、フォームにデータソースの最新のデータを表示することができます。 例えば、バインド参照を使用して、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示することができます。 バインド参照を使用して、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Formsで外部データソースとやり取りするフォームを作成し、シームレスなユーザーエクスペリエンスでデータの収集と管理をおこなうことができます。
* **コンポーネントを非表示**  — フォームでコンポーネントを非表示にするには、このオプションを選択します。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。 これは、ユーザーが表示する必要のない情報や直接変更する必要のない情報を保存する必要がある場合に役立ちます。
* **コンポーネントを無効にする**  — コンポーネントを無効にするオプションを選択します。 無効になっているコンポーネントは、エンドユーザーがアクティブまたは編集できません。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。

### 「項目」タブ {#items-tab}

![「項目」タブ](/help/adaptive-forms/assets/accordion_itemstab.png)

「追加」ボタンを使用すると、コンポーネント選択ウィンドウから、パネルとして追加するコンポーネントを選択できます。 コンポーネントを追加すると、次のオプションが表示されます。

* **アイコン**  — アイコンは、リスト内のパネルのコンポーネントを識別します。 アイコンの上にマウスポインターを置くと、完全なコンポーネント名がツールチップとして表示されます。
* **説明**  — パネルのテキストとして使用される説明。 デフォルトでは、パネルに対してコンポーネントの名前が選択されます。
* **削除** - タップまたはクリックすると、アコーディオンコンポーネントからパネルを削除できます。
* **並べ替え** - タップまたはクリックしてドラッグすると、パネルを並べ替えることができます。

### ヘルプコンテンツタブ {#help-content}

![「ヘルプコンテンツ」タブ](/help/adaptive-forms/assets/accordion_helpcontent.png)

* **短い説明**  — 短い説明は、特定のフォームフィールドの目的に関する追加の情報や説明を提供する、簡単なテキストの説明です。 これにより、ユーザーは、フィールドに入力するデータの種類を理解しやすくなり、入力された情報が有効で目的の条件を満たしていることを確認できるように、ガイドラインや例を提供できます。 デフォルトでは、短い説明は非表示のままです。 を有効にします。 **短い説明を常に表示** オプションを使用して、コンポーネントの下に表示できます。

* **短い説明を常に表示**  — コンポーネントの下に短い説明を表示するオプションを有効にします。

* **ヘルプテキスト**  — ヘルプテキストは、フォームフィールドの正しい入力を支援するためにユーザーに提供される追加の情報やガイダンスを示します。 コンポーネントの横に配置されているヘルプアイコン (i) をクリックすると表示されます。 ヘルプテキストは、フォームフィールドのラベルやプレースホルダーテキストよりも詳細な情報を提供し、ユーザーがフィールドの要件や制約を理解できるように設計されています。 また、フォームへの入力をより簡単かつ正確にするための提案や例を提供することもできます。

### 「アクセシビリティ」タブ {#accessibility}

![「アクセシビリティ」タブ](/help/adaptive-forms/assets/accordion_accessibility.png)

の **アクセシビリティ** タブ、値の設定 [ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/) コンポーネントのラベル。 スクリーンリーダー用のテキストを使用する場合は、次の様々なオプションを使用できます。

* **スクリーンリーダー用テキスト**  — スクリーンリーダー用テキストとは、視覚に障害のあるユーザーが使用する、支援テクノロジーによって読み上げられるように特別に意図された追加のテキストを指します。 このテキストには、フォームフィールドの目的に関するオーディオ説明が含まれ、フィールドのタイトル、説明、名前および関連するメッセージ（カスタムテキスト）に関する情報を含めることができます。 スクリーンリーダーのテキストを使用すると、視覚に障碍のあるユーザーを含むすべてのユーザーがフォームに確実にアクセスでき、フォームフィールドとその要件を完全に理解できます。


   * **カスタムテキスト**:ARIA アクセシビリティラベルにカスタムテキストを使用する場合は、このオプションを選択します。 このオプションを選択すると、[ カスタムテキスト ] ダイアログボックスが表示されます。 関連情報は、カスタムテキストダイアログボックスで追加できます。
   * **説明**:ARIA アクセシビリティラベルの説明を使用するには、このオプションを選択します。
   * **タイトル**:ARIA アクセシビリティラベルのタイトルを使用するには、このオプションを選択します。
   * **名前**:ARIA アクセシビリティラベルの名前を使用するには、このオプションを選択します。
   * **なし**:ARIA アクセシビリティラベルに追加しない場合は、このオプションを選択します。

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

デザインダイアログでは、テンプレート作成者がデフォルトでの表示方法を制御できます。 アダプティブFormsアコーディオンコンポーネントでは、以下を設定できます。

* デフォルトとして許可されて設定されるHTMLの見出し要素のタイプ（H1、H2、H3 など）
* フォーム作成者がアコーディオンに追加できるコアコンポーネントを、アダプティブFormsエディターでコアコンポーネントとして使用します。
* スタイル（CSS クラス）のシンプルな名前。アダプティブFormsエディター内のアコーディオンコンポーネントのプロパティダイアログで適用できます。

これにより、フォームの作成とカスタマイズのプロセスがより簡単で効率的になります。

### 「プロパティ」タブ {#properties-tab-design}

「プロパティ」タブを使用すると、テンプレート作成者は、フォーム作成者にデフォルトの許可HTML見出し要素と許可設定を指定できます。

![デザインダイアログの「プロパティ」タブ](/help/assets/accordion-design-properties.png)

* **許可されている見出し要素**:複数のオプションを含むドロップダウンリストで、作成者がアコーディオンで使用できる見出し要素をテンプレート作成者が選択できます。

* **デフォルトの見出し要素**:ドロップダウンリストは、アコーディオンコンポーネントのデフォルトの見出し要素を設定します。

### 「許可されたコンポーネント」タブ {#allowed-components-tab}

この **許可されたコンポーネント** 「 」タブを使用すると、テンプレートエディターで、アダプティブFormsエディター内のアコーディオンコンポーネントのパネルに、項目として追加できるコンポーネントを設定できます。

### 「スタイル」タブ {#styles-tab}

デザインダイアログは、コンポーネントの CSS スタイルを定義および管理するために使用します。 アダプティブFormsアコーディオンコアコンポーネントは、AEMをサポートしています [スタイルシステム](/help/get-started/authoring.md#component-styling).

**デフォルトの CSS クラス**:アコーディオンコンポーネントのデフォルトの CSS クラスを指定できます。

**許可されたスタイル**:スタイルを定義するには、スタイルを表す名前と CSS クラスを指定します。 例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight」を指定できます。太字」 アダプティブフォームに対して、アダプティブFormsエディターでこれらのスタイルを使用または適用できます。 スタイルを適用するには、アダプティブFormsエディターで、スタイルを適用するコンポーネントを選択し、プロパティダイアログに移動して、 **スタイル** 」ドロップダウンリストから選択できます。 スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新し、変更を保存します。


<!-- 

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



