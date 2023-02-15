---
title: アダプティブFormsコアコンポーネント — テキスト入力（テキストボックス）
description: アダプティブFormsテキスト入力コアコンポーネントの使用またはカスタマイズ
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 1%

---


# テキスト入力（テキストボックス） {#text-input-adaptive-forms-core-component}

テキスト入力（テキストボックス）コンポーネントを使用すると、入力要素の type 属性に応じて、1 行または複数行のテキストを入力および編集できます。 テキスト入力コンポーネントは、フォーム内に配置でき、通常は目的を簡単に識別できる便利なテキストでラベル付けされます。 これらはあらゆるフォームの基本要素で、ユーザーから様々な種類のデータを収集するために広く使用されています。これらは簡単で柔軟で、入力を検証し、データ収集の精度を高めるために設定できます。


**例**

![](/help/adaptive-forms/assets/text-input.png)


## 使用方法 {#reasons-to-use-text-input-field}

アダプティブフォーム内でテキスト入力コンポーネントを使用する理由はいくつかあります。

* **データ収集**:テキスト入力フィールドは、名前、電子メールアドレス、電話番号、その他のタイプのテキストデータなど、ユーザーから様々な情報を収集するために使用される最も一般的なフォーム要素の 1 つです。

* **使いやすい**:テキスト入力フィールドはシンプルで使いやすく、ユーザーが簡単にテキストを入力および編集できます。

* **柔軟性**:テキスト入力フィールドを使用して、短い 1 行のテキストエントリから長い複数行のテキストエントリまで、様々な情報を収集できます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブFormsテキスト入力コアコンポーネントは、コアコンポーネント 2.0.4 の一部として 2023 年 2 月にリリースされました。次の表に、サポートされているすべてのバージョン、AEMの互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | 互換性あり<br>[リリース 2.0.4](/help/versions.md) 以降 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、 [コアコンポーネントのバージョン](/help/versions.md) 文書。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

上部のコアコンポーネントのアダプティブFormsのタブに関する最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput). コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](/help/developing/overview.md).

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者に対するテキスト入力エクスペリエンスを簡単にカスタマイズできます。 また、シームレスなユーザーエクスペリエンスを実現するために、簡単にテキスト入力オプションを定義できます。

![基本タブ](/help/adaptive-forms/assets/textinput_basictab.png)

* **名前**  — フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **タイトル**  — タイトルを使用すると、フォーム内のコンポーネントを簡単に識別でき、デフォルトでは、タイトルがコンポーネントの上に表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

* **タイトルを非表示**  — コンポーネントのタイトルを非表示にするには、このオプションを選択します。

* **プレースホルダーテキスト**  — フォームコンポーネント内のプレースホルダーテキストは、入力フィールド内に表示される短いラベルまたはプロンプトを指し、そのフィールドに入力する必要のある情報の種類に関するヒントとしてユーザーに表示します。 ユーザーがフィールドへの入力を開始すると、プレースホルダーテキストが消え、フィールドが空のままの場合は再び表示されます。 ユーザーに視覚的なキューを提供しますが、フィールドの永続的なラベルや値としては機能しません。

* **バインド参照**  — バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。 連結参照を使用すると、データをフォームフィールドに動的に連結して、フォームにデータソースの最新のデータを表示することができます。 例えば、バインド参照を使用して、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示することができます。 バインド参照を使用して、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Formsで外部データソースとやり取りするフォームを作成し、シームレスなユーザーエクスペリエンスでデータの収集と管理をおこなうことができます。

* **コンポーネントを非表示**  — フォームでコンポーネントを非表示にするには、このオプションを選択します。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。 これは、ユーザーが表示する必要のない情報や直接変更する必要のない情報を保存する必要がある場合に役立ちます。

* **コンポーネントを無効にする**  — コンポーネントを無効にするオプションを選択します。 無効になっているコンポーネントは、エンドユーザーがアクティブまたは編集できません。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。

* **読み取り専用**  — コンポーネントを編集不可にするには、このオプションを選択します。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。

* **デフォルト値**  — このオプションを使用すると、フォームフィールドにデフォルト値を追加できます。 ユーザーがフィールドへの入力を開始すると、テキストが消えます。 If **無効なコンポーネント** または **読み取り専用コンポーネント** が選択されている場合、デフォルト値が画面に表示されます。 ユーザーがフォームフィールドに値を入力しない場合、この値はフォームの送信時に送信されます。

* **複数行を許可**  — このオプションを使用すると、ユーザーはフォームフィールドに複数行を入力できます。

* **リッチテキストを許可**  — 編集ダイアログには、ユーザーがテキストの書式を設定できる、標準のリッチテキスト書式設定ツールが用意されています。

* **自動入力属性** - 「自動入力」オプションは、パターンまたは以前に入力したテキストに従ってフォームフィールドに入力します。 ユーザーがフォームフィールドにテキストを入力し始めると、候補がドロップダウンリストに表示され、そこから適切なオプションを選択できます。

### 「検証」タブ {#validation-tab}

![「検証」タブ](/help/adaptive-forms/assets/textinput_validationtab.png)

* **必須**  — コンポーネントをアダプティブフォームに表示する場合は、このオプションを選択します。 選択できない **コンポーネントを非表示** または **コンポーネントを無効にする**  内 **基本** 」タブを使用します。

* **エラーメッセージ**  — このオプションを使用すると、 **必須** チェックボックスがオンになっており、フィールドは空白のままです。

* **スクリプト検証メッセージ**  — このオプションを使用すると、スクリプトの検証が失敗した場合に表示するメッセージを入力できます。

* **最大文字数**  — このオプションを使用すると、コンポーネントで許可する最大文字数を指定できます。 指定した値より大きい文字を入力する場合は、 **最大文字数**&#x200B;と入力すると、エラーメッセージが画面に表示されます。 この **最大文字数のエラーメッセージ** ダイアログボックスで、カスタムエラーメッセージを追加できます。

* **最大文字数のエラーメッセージ** - **最大文字数のエラーメッセージ** ダイアログボックスで、 **最大文字数** オプション。

* **最小文字数**  — このオプションを使用すると、フィールドで許可する最小文字数を指定できます。 指定した値より小さい文字を入力する場合は、 **最小文字数**&#x200B;と入力すると、エラーメッセージが画面に表示されます。 この **最小文字数エラーメッセージ** ダイアログボックスで、カスタムエラーメッセージを追加できます。

* **最小文字数エラーメッセージ** - **最小文字数エラーメッセージ** ダイアログボックスで、 **最小文字数** オプション。

この **検証パターン** 「 」オプションを使用すると、入力したテキストを検証するパターンを入力できます。 テキストが **パターン** 」オプションを選択すると、エラーメッセージが画面に表示されます。

* **パターン**  — このオプションを使用すると、テキストに許可されている検証パターンを入力できます。 正規表現も使用できます。

* **エラーメッセージ**  — このオプションを使用すると、入力したテキストが、 **パターン** オプション

### ヘルプコンテンツタブ {#help-content-tab}

![「ヘルプコンテンツ」タブ](/help/adaptive-forms/assets/textinput_helptab.png)

* **短い説明**  — 短い説明は、特定のフォームフィールドの目的に関する追加の情報や説明を提供する、簡単なテキストの説明です。 これにより、ユーザーは、フィールドに入力するデータの種類を理解しやすくなり、入力された情報が有効で目的の条件を満たしていることを確認できるように、ガイドラインや例を提供できます。 デフォルトでは、短い説明は非表示のままです。 を有効にします。 **短い説明を常に表示** オプションを使用して、コンポーネントの下に表示できます。

* **短い説明を常に表示**  — コンポーネントの下に短い説明を表示するオプションを有効にします。

* **ヘルプテキスト**  — ヘルプテキストは、フォームフィールドの正しい入力を支援するためにユーザーに提供される追加の情報やガイダンスを示します。 コンポーネントの横に配置されているヘルプアイコン (i) をクリックすると表示されます。 ヘルプテキストは、フォームフィールドのラベルやプレースホルダーテキストよりも詳細な情報を提供し、ユーザーがフィールドの要件や制約を理解できるように設計されています。 また、フォームへの入力をより簡単かつ正確にするための提案や例を提供することもできます。

### 「アクセシビリティ」タブ {#accessibility-tab}

![「アクセシビリティ」タブ](/help/adaptive-forms/assets/textinput_accessibiltytab.png)

* **スクリーンリーダー用テキスト**  — スクリーンリーダー用テキストとは、視覚に障害のあるユーザーが使用する、支援テクノロジーによって読み上げられるように特別に意図された追加のテキストを指します。 このテキストには、フォームフィールドの目的に関するオーディオ説明が含まれ、フィールドのタイトル、説明、名前および関連するメッセージ（カスタムテキスト）に関する情報を含めることができます。 スクリーンリーダーのテキストを使用すると、視覚に障碍のあるユーザーを含むすべてのユーザーがフォームに確実にアクセスでき、フォームフィールドとその要件を完全に理解できます。

## デザインダイアログ {#design-dialog}

デザインダイアログは、テキストボックスコンポーネントの CSS スタイルを定義および管理するために使用します。

### 「スタイル」タブ {#styles-tab}

デザインダイアログは、コンポーネントの CSS スタイルを定義および管理するために使用します。 アダプティブFormsテキストボックスコアコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling).

**デフォルトの CSS クラス**:アダプティブFormsテキストボックスのコアコンポーネントのデフォルト CSS クラスを指定できます。

**許可されたスタイル**:スタイルを定義するには、スタイルを表す名前と CSS クラスを指定します。 例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight」を指定できます。太字」 アダプティブフォームに対して、アダプティブFormsエディターでこれらのスタイルを使用または適用できます。 スタイルを適用するには、アダプティブFormsエディターで、スタイルを適用するコンポーネントを選択し、プロパティダイアログに移動して、 **スタイル** 」ドロップダウンリストから選択できます。 スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新し、変更を保存します。

### 「形式」タブ {#format-tab}

「書式」タブでは、デフォルトの書式とカスタムの書式を指定できます。