---
title: アダプティブFormsコアコンポーネント — ボタン
description: アダプティブFormsボタンのコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 2%

---


# ボタンコンポーネント  {#button-component-adaptive-forms-core-component}

アダプティブフォーム内のボタンは、ユーザーがクリックしたときにアクションを開始できる UI 要素です。 button 要素を使用すると、フォームの送信、フォームのリセット、別のページへの移動やカスタムコードのトリガーなどの他のアクションの実行ができます。 ボタンは、ボタンコアコンポーネントを使用して作成できます。

アダプティブFormsルールエディターを使用すると、ボタンコンポーネントに対して様々なアクションを設定できます。 これらの操作には、Web サイトの開く、フォームコンポーネントの表示と非表示、パネルやコンポーネントのインスタンスの追加、フォームの送信またはリセットなどが含まれます。

アダプティブFormsでは、フォームの送信やリセットを行うための個別のボタンコンポーネントも提供されていますが、必要に応じて、これらの操作を実行するようにボタンコンポーネントを設定することもできます。

ユーザーは、アダプティブFormsルールエディターを使用して、ボタンコンポーネントでサポートされているすべてのアクションのリストにアクセスできます。 ルールエディターを使用すると、ボタンがクリックされたとき、フォームが読み込まれたとき、またはフィールド値が変更されたときなど、様々なイベントによってトリガーされるルールを作成できます。 これらのルールを使用して、コンポーネントの表示/非表示、フィールド値の設定、フォームの送信など、様々なアクションを実行できます。

## 使用方法 {#reasons-to-use-button}

アダプティブフォームにボタンを含める方がメリットが大きい理由は、次のようにいくつかあります。

* **フォーム送信**:通常、ボタンはフォームを送信するために使用され、ユーザーは入力したデータをサーバーに送信して処理できます。

* **フォームのリセット**:ボタンを使用して、フォームをリセットし、ユーザーが入力したすべてのデータをクリアすることもできます。

* **ナビゲーション**:ボタンを使用して、フォームの異なるセクション間や Web サイトの異なるページ間を移動できます。

* **イベントの処理**:ボタンを使用して、Web サイトを開く、コンポーネントの表示/非表示、パネルやコンポーネントのインスタンスのボタンへの追加など、様々なイベントをトリガーできます。

* **相互作用**:ボタンを使用して、インタラクティブフォームを作成できます。 例えば、ボタンを使用してモーダルダイアログを開いたり、フォームのセクションを切り替えたりできます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブFormsボタンコアコンポーネント v1 は、コアコンポーネント 2.0.4 の一部として 2023 年 2 月にリリースされました。次の表に、サポートされているすべてのバージョン、AEMの互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | 互換性あり<br>[リリース 2.0.4](/help/versions.md) 以降 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、 [コアコンポーネントのバージョン](/help/versions.md) 文書。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブFormsボタンコアコンポーネントの最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](/help/developing/overview.md).

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者に対するボタンのエクスペリエンスを簡単にカスタマイズできます。 また、簡単にボタンのプロパティを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 基本タブ {#basic-tab}

![基本タブ](/help/adaptive-forms/assets/button_basictab.png)

* **名前**  — フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **タイトル**  — タイトルを使用すると、フォーム内のコンポーネントを簡単に識別でき、デフォルトでは、タイトルがコンポーネントの上に表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

* **バインド参照**  — バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。 連結参照を使用すると、データをフォームフィールドに動的に連結して、フォームにデータソースの最新のデータを表示することができます。 例えば、バインド参照を使用して、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示することができます。 バインド参照を使用して、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Formsで外部データソースとやり取りするフォームを作成し、シームレスなユーザーエクスペリエンスでデータの収集と管理をおこなうことができます。

* **レコードのドキュメント連結参照**  — このオプションを使用すると、アダプティブフォームフィールドをレコードのドキュメントフィールドに関連付けることができます。 ユーザーがアダプティブフォームのリンクされたフィールドに値を入力すると、その値は対応するレコードのドキュメントのリンクされたフィールドにも表示されます。 例えば、レコードのドキュメントのバインド参照を使用して、フォームに入力された顧客の ID に基づいて、レコードのドキュメントに顧客の名前と住所を表示することができます。 この方法で、AEM Formsを使用してレコードのドキュメントを生成でき、データを収集および管理するためのシームレスなユーザーエクスペリエンスを提供します。

* **コンポーネントを非表示**  — フォームでコンポーネントを非表示にするには、このオプションを選択します。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。 これは、ユーザーが表示する必要のない情報や直接変更する必要のない情報を保存する必要がある場合に役立ちます。
* **コンポーネントを無効にする**  — コンポーネントを無効にするオプションを選択します。 無効になっているコンポーネントは、エンドユーザーがアクティブまたは編集できません。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。
* **読み取り専用**  — コンポーネントを編集不可にするには、このオプションを選択します。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）でもアクセスできます。

### ヘルプコンテンツタブ {#help-content}

![「ヘルプコンテンツ」タブ](/help/adaptive-forms/assets/button_helptab.png)

* **短い説明**  — 短い説明は、特定のフォームフィールドの目的に関する追加の情報や説明を提供する、簡単なテキストの説明です。 これにより、ユーザーは、フィールドに入力するデータの種類を理解しやすくなり、入力された情報が有効で目的の条件を満たしていることを確認できるように、ガイドラインや例を提供できます。 デフォルトでは、短い説明は非表示のままです。 を有効にします。 **短い説明を常に表示** オプションを使用して、コンポーネントの下に表示できます。

* **短い説明を常に表示**  — コンポーネントの下に短い説明を表示するオプションを有効にします。

* **ヘルプテキスト**  — ヘルプテキストは、フォームフィールドの正しい入力を支援するためにユーザーに提供される追加の情報やガイダンスを示します。 コンポーネントの横に配置されているヘルプアイコン (i) をクリックすると表示されます。 ヘルプテキストは、フォームフィールドのラベルやプレースホルダーテキストよりも詳細な情報を提供し、ユーザーがフィールドの要件や制約を理解できるように設計されています。 また、フォームへの入力をより簡単かつ正確にするための提案や例を提供することもできます。

### アクセシビリティ {#accessibility}

![「アクセシビリティ」タブ](/help/adaptive-forms/assets/button_accessibilitytab.png)


の **アクセシビリティ** タブ、値の設定 [ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/) コンポーネントのラベル。 スクリーンリーダー用のテキストを使用する場合は、次の様々なオプションを使用できます。

* **スクリーンリーダー用テキスト**  — スクリーンリーダー用テキストとは、視覚に障害のあるユーザーが使用する、支援テクノロジーによって読み上げられるように特別に意図された追加のテキストを指します。 このテキストには、フォームフィールドの目的に関するオーディオ説明が含まれ、フィールドのタイトル、説明、名前および関連するメッセージ（カスタムテキスト）に関する情報を含めることができます。 スクリーンリーダーのテキストを使用すると、視覚に障碍のあるユーザーを含むすべてのユーザーがフォームに確実にアクセスでき、フォームフィールドとその要件を完全に理解できます。


   * **カスタムテキスト**:ARIA アクセシビリティラベルにカスタムテキストを使用する場合は、このオプションを選択します。 このオプションを選択すると、[ カスタムテキスト ] ダイアログボックスが表示されます。 関連情報は、カスタムテキストダイアログボックスで追加できます。
   * **説明**:ARIA アクセシビリティラベルの説明を使用するには、このオプションを選択します。
   * **タイトル**:ARIA アクセシビリティラベルのタイトルを使用するには、このオプションを選択します。
   * **名前**:ARIA アクセシビリティラベルの名前を使用するには、このオプションを選択します。
   * **なし**:ARIA アクセシビリティラベルに追加しない場合は、このオプションを選択します。

## デザインダイアログ {#design-dialog}

デザインダイアログは、ボタンコンポーネントの CSS スタイルを定義および管理するために使用されます。

### 「スタイル」タブ {#styles-tab}

アダプティブFormsボタンコアコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling).

**デフォルトの CSS クラス**:アダプティブFormsボタンコアコンポーネントのデフォルトの CSS クラスを指定できます。

**許可されたスタイル**:スタイルを定義するには、スタイルを表す名前と CSS クラスを指定します。 例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight」を指定できます。太字」 アダプティブフォームに対して、アダプティブFormsエディターでこれらのスタイルを使用または適用できます。 スタイルを適用するには、アダプティブFormsエディターで、スタイルを適用するコンポーネントを選択し、プロパティダイアログに移動して、 **スタイル** 」ドロップダウンリストから選択できます。 スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新し、変更を保存します。
