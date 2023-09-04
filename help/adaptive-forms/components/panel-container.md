---
title: アダプティブフォームのコアコンポーネント - パネルコンテナ
description: アダプティブフォームのパネルコンテナコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
source-git-commit: b6e3a443c7425a60fc6c3469dc273960a4e29088
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 99%

---

# パネルコンテナ {#panel-container-adaptive-forms-core-component}

アダプティブフォームでは、パネルはコンテナ要素であり、関連するフォーム要素をグループ化するために使用できます。これにより、様々なフォーム要素を論理的で意味のある方法でグループ化して整理できます。また、フォームの全体的な構造と読みやすさが向上し、ユーザーがフォームを理解して移動しやすくなります。

パネルを使用して、折りたたみ可能なセクションを作成することもできます。このセクションは、複雑なフォームフィールドやあまり頻繁に使用されないフォームフィールドを隠すのに役立ち、フォームをシンプルで使いやすいものにできます。また、テキスト、チェックボックス、ボタンなど、他のコンポーネントを含めることもできます。

また、フォームの送信、web サイトを開く、コンポーネントの表示／非表示、パネルのインスタンスの追加など、様々なルールベースのアクションを設定する場合にも使用できます。

**例**

![](/help/adaptive-forms/assets/panel-container.png)

## 使用方法 {#reasons-to-use-panel-container}

フォーム内でパネルを使用する理由は、次のようにいくつかあります。

- **フォーム要素の整理**：関連するフォーム要素をグループ化し、ユーザーがフォームを理解して移動しやすくすることができます。

- **フォーム構造の改善**：フォーム要素をパネルにグループ化すると、フォームの全体的な構造と読みやすさが向上して理解しやすくなります。

- **折りたたみ可能なセクションの作成**：パネルを使用して、折りたたみ可能なセクションを作成できます。このセクションは、複雑なフォームフィールドやあまり頻繁に使用されないフォームフィールドを隠すのに役立ち、フォームをシンプルで使いやすいものにできます。

- **操作性の向上**：パネルを使用してフォーム要素を整理すると、フォームがより簡単で使いやすくなり、完了率が高くなります。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのパネルコンテナコアコンポーネントは、コアコンポーネント 2.0.4 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | <br>[リリース 2.0.4](/help/versions.md) 以降と互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)ドキュメントをご覧ください。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブフォームのパネルコンテナコアコンポーネントに関する最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、パネルコンテナの操作を訪問者に合わせて簡単にカスタマイズできます。また、簡単にパネルコンテナオプションを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 「基本」タブ {#basic-tab}

![「基本」タブ](/help/adaptive-forms/assets/basic-panel.png)

- **名前** - フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

- **タイトル** - タイトルを使用すると、フォーム内のコンポーネントを簡単に識別できます。デフォルトでは、コンポーネントの上にタイトルが表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

- **タイトルを非表示** - コンポーネントのタイトルを非表示にするには、このオプションを選択します。

- **フォームの送信時に子コンポーネントのデータをグループ化（オブジェクトにデータを含める）** - このオプションを選択すると、子コンポーネントのデータが親コンポーネントの JSON オブジェクト内にネストされます。ただし、このオプションを選択しないと、送信した JSON データは、親コンポーネントのオブジェクトを持たないフラットな構造になります。例：

   - このオプションを選択すると、子コンポーネント（番地、市区町村、郵便番号など）のデータが、JSON オブジェクトとして親コンポーネント（住所）内にネストされます。これにより、階層構造が作成され、データは親コンポーネントの下に整理されます。

     送信したデータの構造：

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   - このオプションを選択しないと、送信した JSON データは、親コンポーネント（住所）のオブジェクトを持たないフラットな構造になります。すべてのデータは同じレベルにあり、階層構造はありません。


     送信したデータの構造：

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

- **レイアウト** - ウィザードには固定レイアウト（シンプル）または柔軟なレイアウト（レスポンシブグリッド）を使用できます。 シンプルなレイアウトでは、すべてを固定した状態に保ち、レスポンシブグリッドでは、必要に応じてコンポーネントの位置を調整できます。例えば、レスポンシブグリッドを使用して、「名」、「ミドルネーム」、「姓」を 1 行にフォーム内で整列できます。

- **バインド参照** - バインド参照は、外部データソースに保存され、フォーム内で使用されるデータ要素への参照です。バインド参照を使用すると、データをフォームフィールドに動的にバインドして、フォームにデータソースの最新のデータを表示できます。 例えば、フォームに入力された顧客 ID に基づいて、顧客の名前と住所をフォームに表示できます。 さらに、フォームに入力されたデータでデータソースを更新することもできます。 このようにして、AEM Forms で外部データソースとやり取りするフォームを作成し、データの収集と管理においてシームレスなユーザーエクスペリエンスを提供できます。
- **コンポーネントを非表示** - フォームでコンポーネントを非表示にするには、このオプションを選択します。このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。 これは、ユーザーが表示する必要のない情報や直接変更した情報を保存する必要がある場合に役立ちます。
- **コンポーネントの無効化** - コンポーネントを無効にする場合は、このオプションを選択します。 エンドユーザーは、無効になっているコンポーネントをアクティブにしたり、編集したりすることはできません。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

### 「繰り返しパネル」タブ {#repeat-panel}

![繰り返しタブ](/help/adaptive-forms/assets/repeat-panel.png)

繰り返しオプションを使用すると、パネルコンテナとその子コンポーネントの複製、最小繰り返し回数と最大繰り返し回数の定義、フォーム内の類似セクションの複製を簡単に行うことができます。パネルコンテナコンポーネントを操作してその設定にアクセスする際には、次のオプションが表示されます。

- **ウィザードを繰り返し可能にする**：ユーザーが繰り返し機能を有効または無効にできる切替スイッチ機能。
- **最小繰り返し回数**：パネルコンテナを繰り返し可能な最小回数を設定します。値 0 は、ウィザードパネルが繰り返されないことを示します。デフォルト値は 0 です。
- **最大繰り返し回数**：パネルコンテナを繰り返し可能な最大回数を設定します。デフォルトでは、この値は無制限です。

パネルコンテナ内で繰り返し可能なセクションを効果的に管理するには、[繰り返し可能なセクションを含むフォームの作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=ja)の記事に記載されている手順に従います。

### 「ヘルプコンテンツ」タブ {#help-content}

![「ヘルプコンテンツ」タブ](/help/adaptive-forms/assets/helpcontent-panel.png)


- **短い説明** - 短い説明は、特定のフォームフィールドの目的に関する追加の情報や説明を提供する簡単な説明文です。これにより、ユーザーは、フィールドに入力するデータの種類を理解しやすくなります。また、入力された情報が有効で目的の条件を満たしていることを確認できるように、ガイドラインや例を提供できます。デフォルトでは、短い説明は非表示になっています。 「**短い説明を常に表示**」オプションを有効にすると、コンポーネントの下に説明が表示されます。

- **短い説明を常に表示** - このオプションを有効にすると、コンポーネントの下に短い説明が表示されます。

- **ヘルプテキスト** - ヘルプテキストとは、フォームフィールドの正しい入力を支援するためにユーザーに提供される追加の情報やガイダンスを指します。コンポーネントの横に配置されているヘルプアイコン（i）をクリックすると表示されます。 ユーザーがフィールドの要件や制約を理解できるように設計されているヘルプテキストは、フォームフィールドのラベルやプレースホルダーテキストよりも詳細な情報を提供できます。また、フォームへの入力をより簡単かつ正確にするための提案や例を提供することも可能です。

### 「アクセシビリティ」タブ {#accessibility}

![「アクセシビリティ」タブ](/help/adaptive-forms/assets/accessibilty-panel.png)


- **スクリーンリーダー用テキスト** - スクリーンリーダー用テキストとは、視覚に障害のあるユーザーが使用する、支援テクノロジー（スクリーンリーダーなど）によって読み上げられる追加のテキストを指します。このテキストでは、フォームフィールドの目的に関するオーディオの説明が提供され、フィールドのタイトル、説明、名前および関連するメッセージ（カスタムテキスト）に関する情報を含めることができます。スクリーンリーダー用のテキストを使用すると、視覚に障害のあるユーザーを含むすべてのユーザーがフォームに確実にアクセスして、フォームフィールドとその要件を完全に理解できるようになります。

- **スクリーンリーダーが通知を行うための HTMLの役割** - HTMLの役割は、スクリーンリーダーなどの支援テクノロジーに対する HTML 要素の目的を指定するための属性です。役割の属性は、要素に追加のコンテキストと意味論的意味を提供するために使用されます。これにより、スクリーンリーダーがコンテンツを解釈して読み上げやすくなります。 例えば AEM Formsでは、フォームフィールドのラベルが「label」という役割を持ち、入力フィールドが「textbox」という役割を持つ場合があります。 これにより、スクリーンリーダーはラベルと入力フィールドの関係を理解し、ユーザーに対して正しく通知できるようになります。

## 関連記事 {#related-article}

- [AEM Sites ページまたはエクスペリエンスフラグメントでアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=ja)

- [スタンドアロンのアダプティブフォームを作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=ja)


## 関連トピック {#see-also}

- [アコーディオン](/help/adaptive-forms/components/accordion.md)
- [ボタン](/help/adaptive-forms/components/button.md)
- [チェックボックス グループ](/help/adaptive-forms/components/checkbox-group.md)
- [日付選択](/help/adaptive-forms/components/date-picker.md)
- [ドロップダウンリスト](/help/adaptive-forms/components/drop-down.md)
- [メール入力](/help/adaptive-forms/components/email-input.md)
- [フォームコンテナ](/help/adaptive-forms/components/form-container.md)
- [ファイル添付](/help/adaptive-forms/components/file-attachment.md)
- [フッター](/help/adaptive-forms/components/footer.md)
- [ヘッダー](/help/adaptive-forms/components/header.md)
- [水平タブ](/help/adaptive-forms/components/horizontal-tabs.md)
- [画像](/help/adaptive-forms/components/image.md)
- [数値入力](/help/adaptive-forms/components/number-input.md)
- [ラジオボタン](/help/adaptive-forms/components/radio-button.md)
- [リセットボタン](/help/adaptive-forms/components/reset-button.md)
- [送信ボタン](/help/adaptive-forms/components/submit-button.md)
- [電話入力](/help/adaptive-forms/components/telephone-input.md)
- [テキスト入力](/help/adaptive-forms/components/text-input.md)
- [テキスト](/help/adaptive-forms/components/text.md)
- [タイトル](/help/adaptive-forms/components/title.md)
- [ウィザード](/help/adaptive-forms/components/wizard.md)