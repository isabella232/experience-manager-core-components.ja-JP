---
title: アダプティブフォームのコアコンポーネント - ボタン
description: アダプティブフォームボタンのコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
exl-id: cb75929b-8c86-49d1-b51a-368f5b80b1a9
source-git-commit: 0bebc248ee2b708f7677950d90356abd5bc70a98
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 100%

---

# ボタンコンポーネント  {#button-component-adaptive-forms-core-component}

アダプティブフォーム内のボタンは、ユーザーがクリックしたときにアクションを開始できる UI 要素です。 ボタン要素を使用すると、フォームの送信、フォームのリセット、または別のページへの移動やカスタムコードのトリガーといった他のアクションを実行できます。 ボタンは、ボタンコアコンポーネントを使用して作成できます。

アダプティブフォームのルールエディターを使用すると、ボタンコンポーネントに対して様々なアクションを設定できます。 これらの操作には、web サイトを開く、フォームコンポーネントの表示や非表示、パネルやコンポーネントのインスタンスの追加、フォームの送信またはリセットなどが含まれます。

アダプティブフォームには、[送信ボタン](/help/adaptive-forms/components/submit-button.md)と[リセットボタン](/help/adaptive-forms/components/reset-button.md)の別々のコンポーネントが備わっているので、ユーザーはフォームを簡単に送信またはリセットできます。ボタンコンポーネントは、特定のニーズに基づいて、これらのアクションを実行するように柔軟に設定できます。

ユーザーはアダプティブフォームのルールエディターを使用して、ボタンコンポーネントでサポートされているすべてのアクションのリストにアクセスできます。 ルールエディターでは、ボタンがクリックされたとき、フォームが読み込まれたとき、またはフィールド値が変更されたときなど、様々なイベントによってトリガーされるルールを作成できます。 これらのルールを使用して、コンポーネントの表示や非表示、フィールド値の設定、フォームの送信など、様々なアクションを実行できます。

## 使用方法 {#reasons-to-use-button}

アダプティブフォームにボタンを含めるメリットとしては、次のようにいくつかの理由があります。

* **フォームの送信**：通常、ボタンはフォームを送信するために使用され、ユーザーは入力したデータをサーバーに送信して処理できます。

* **フォームのリセット**：ボタンを使用してフォームをリセットし、ユーザーが入力したすべてのデータを消去することもできます。

* **ナビゲーション**：ボタンを使用して、フォームの異なるセクション間や web サイトの異なるページ間を移動できます。

* **イベントの処理**：ボタンを使用して、web サイトを開いたり、コンポーネントを表示または非表示にしたり、パネルやコンポーネントのインスタンスをボタンに追加するなど、様々なイベントをトリガーできます。

* **インタラクティブ機能**：ボタンを使用して、インタラクティブフォームを作成できます。 例えば、ボタンを使用してモーダルダイアログを開いたり、フォームのセクションを切り替えたりできます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブフォームボタンのコアコンポーネントの最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button) のテクニカルドキュメントをご覧ください。 コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

「設定」ダイアログを使用すると、ボタンに関する訪問者のエクスペリエンスを簡単にカスタマイズできます。 また、簡単にボタンのプロパティを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 「基本」タブ {#basic-tab}

![「基本」タブ](/help/adaptive-forms/assets/button_basictab.png)

* **名前** - フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

* **タイトル** - タイトルを使用すると、フォーム内のコンポーネントを簡単に識別できます。デフォルトでは、コンポーネントの上にタイトルが表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

* **バインド参照** - バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。 バインド参照を使用すると、データをフォームフィールドに動的にバインドして、フォームにデータソースの最新のデータを表示できます。 例えば、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示できます。 さらに、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Forms で外部データソースとやり取りするフォームを作成し、データの収集と管理においてシームレスなユーザーエクスペリエンスを提供できます。

* **レコードのドキュメントのバインド参照** - このオプションを使用すると、アダプティブフォームフィールドをレコードのドキュメントフィールドに関連付けることができます。 ユーザーがアダプティブフォームのリンクされたフィールドに値を入力すると、その値は対応するレコードのドキュメントのリンクされたフィールドにも表示されます。 例えば、レコードのドキュメントのバインド参照を使用して、フォームに入力された顧客の ID に基づいて、レコードのドキュメントに顧客の名前と住所を表示することができます。 この方法で、AEM Forms を使用してレコードのドキュメントを生成し、データの収集および管理においてシームレスなユーザーエクスペリエンスを提供できます。

* **コンポーネントを非表示** - フォームでコンポーネントを非表示にする場合に、このオプションを選択します。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。 これは、ユーザーが表示する必要のない情報や直接変更した情報を保存する必要がある場合に役立ちます。
* **コンポーネントの無効化** - コンポーネントを無効にする場合は、このオプションを選択します。 エンドユーザーは、無効になっているコンポーネントをアクティブにしたり、編集したりすることはできません。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。
* **読み取り専用** - コンポーネントを編集不可にするには、このオプションを選択します。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

### 「ヘルプコンテンツ」タブ {#help-content}

![「ヘルプコンテンツ」タブ](/help/adaptive-forms/assets/button_helptab.png)

* **短い説明** - 短い説明は、特定のフォームフィールドの目的に関する追加の情報や説明を提供する簡単な説明文です。これにより、ユーザーは、フィールドに入力するデータの種類を理解しやすくなります。また、入力された情報が有効で目的の条件を満たしていることを確認できるように、ガイドラインや例を提供できます。デフォルトでは、短い説明は非表示になっています。 「**短い説明を常に表示**」オプションを有効にすると、コンポーネントの下に説明が表示されます。

* **短い説明を常に表示** - このオプションを有効にすると、コンポーネントの下に短い説明が表示されます。

* **ヘルプテキスト** - ヘルプテキストとは、フォームフィールドの正しい入力を支援するためにユーザーに提供される追加の情報やガイダンスを指します。コンポーネントの横に配置されているヘルプアイコン（i）をクリックすると表示されます。 ユーザーがフィールドの要件や制約を理解できるように設計されているヘルプテキストは、フォームフィールドのラベルやプレースホルダーテキストよりも詳細な情報を提供できます。また、フォームへの入力をより簡単かつ正確にするための提案や例を提供することも可能です。

### アクセシビリティ {#accessibility}

![「アクセシビリティ」タブ](/help/adaptive-forms/assets/button_accessibilitytab.png)


* **スクリーンリーダー用テキスト** - スクリーンリーダー用テキストとは、視覚に障害のあるユーザーが使用する、支援テクノロジー（スクリーンリーダーなど）によって読み上げられる追加のテキストを指します。このテキストでは、フォームフィールドの目的に関するオーディオの説明が提供され、フィールドのタイトル、説明、名前および関連するメッセージ（カスタムテキスト）に関する情報を含めることができます。スクリーンリーダー用のテキストを使用すると、視覚に障害のあるユーザーを含むすべてのユーザーがフォームに確実にアクセスして、フォームフィールドとその要件を完全に理解できるようになります。

## デザインダイアログ {#design-dialog}

デザインダイアログは、ボタンコンポーネントの CSS スタイルを定義および管理するために使用されます。

### 「スタイル」タブ {#styles-tab}

アダプティブフォームボタンのコアコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

![デザインダイアログ](/help/adaptive-forms/assets/button_designdialog.png)

* **デフォルトの CSS クラス**：アダプティブフォームボタンのコアコンポーネントのデフォルトの CSS クラスを指定できます。

* **許可されたスタイル**：スタイルを定義するには、スタイルを表す名前と CSS クラスを指定します。例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight: bold」を指定できます。アダプティブフォームエディターでアダプティブフォームにこれらのスタイルを使用または適用できます。スタイルを適用するには、アダプティブフォームエディターでスタイルを適用するコンポーネントを選択し、「プロパティ」ダイアログに移動して「**スタイル**」ドロップダウンリストから希望のスタイルを選択します。スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新して変更を保存します。

## 関連記事 {#related-article}

* [AEM Sites ページまたはエクスペリエンスフラグメントでアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=ja)

* [スタンドアロンのアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=ja)

>[!MORELIKETHIS]
>
>* [アコーディオン](/help/adaptive-forms/components/accordion.md)
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
>* [電話入力](/help/adaptive-forms/components/telephone-input.md)
>* [テキスト入力](/help/adaptive-forms/components/text-input.md)
>* [テキスト](/help/adaptive-forms/components/text.md)
>* [タイトル](/help/adaptive-forms/components/title.md)
>* [ウィザード](/help/adaptive-forms/components/wizard.md)


## 関連トピック {#see-also}

{{see-also}}

