---
title: アダプティブフォームのコアコンポーネント - タイトル
description: アダプティブフォームのタイトルコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: 59cd9d65bf4c1be6ab2eaf15bbb747b532863fdd
workflow-type: ht
source-wordcount: '899'
ht-degree: 100%

---

# タイトル {#title-input-adaptive-forms-core-component}

アダプティブフォームの「タイトル」とは、フォームの上部（通常、ヘッダーの下）に表示されるテキストを指します。タイトルは、タイトルコンポーネントを使用して指定します。このコンポーネントをフォームレイアウトに追加し、そのテキストをフォームの目的やトピックに合わせて編集できます。 タイトルは、ユーザーに対するフォームのラベルまたは短い説明として機能し、フォームを区別するのに役立ちます。

**例**

![](/help/adaptive-forms/assets/title.png)

## 使用方法 {#reasons-to-use-title-in-an-adaptive-form}

フォームでタイトルを使用するメリットはいくつかあります。

* **明確さ**：タイトルは、フォームの目的を明確に示し、ユーザーが提供する必要のある情報を理解するのに役立ちます。

* **組織**：タイトルは、トピック別または目的別にフォームを整理するのに役立ちます。また、ユーザーが必要なフォームを簡単に見つけられるようになります。

* **アクセシビリティ**：スクリーンリーダーで読み上げられ、ユーザーがフォームのコンテキストを理解するのに役立つため、タイトルはアクセシビリティのニーズを持つユーザーにとって重要な要素です。

* **ブランディング**：タイトルを使用して、会社または組織の名前を表示することもできます。ユーザーに信頼してもらい、親しみを持ってもらうのに役立ちます。

* **ナビゲーション**：タイトルは、特にフォームが長い場合や複雑な場合に、フォーム内を移動する際にも役立ちます。

* **検索エンジン最適化（SEO）**：フォームにタイトルを付けると SEO でも役立ちます。これは、検索エンジンがタイトルを使用して、検索クエリに対する web ページの関連性を判断するからです。

全体的に、フォームのタイトルはユーザーエクスペリエンスに関する重要な要素であり、フォームのコンテキストと目的を理解するのに役立つ明確で簡潔なラベルをフォームで提供する際に使用します。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術的詳細 {#technical-details}

アダプティブフォームのタイトルコアコンポーネントの最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者によるタイトルの利用を簡単にカスタマイズできます。 また、簡単にタイトルオプションを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

![「基本」タブ](/help/adaptive-forms/assets/title_properties.png)

編集ダイアログでは、コンテンツ作成者がタイトルテキストを定義したり、見出しレベルを選択したりできます。

* **タイトル** - タイトルを使用すると、フォーム内のコンポーネントを簡単に識別できます。デフォルトでは、コンポーネントの上にタイトルが表示されます。タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。
* **種類 / サイズ** - タイトルの見出しレベルを定義します.
* **ID** - このオプションを使用すると、HTML 内およびデータレイヤー内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

## デザインダイアログ {#design-dialog}

「デザイン」タブでは、日付選択コンポーネントの CSS スタイルを定義および管理できます。

### タイトル

「タイトル」タブでは、テンプレート作成者がフォーム作成者のために、許可されるデフォルトの HTML 見出し要素を設定できます。

![デザインダイアログの「プロパティ」タブ](/help/adaptive-forms/assets/title_heading.png)

* **許可されている見出し要素**：フォーム作成者がタイトルに使用できる見出し要素をテンプレート作成者が選択できる複数のオプションを含むリストです。

* **デフォルトの見出し要素**：タイトルコンポーネントのデフォルトの見出し要素を設定するドロップダウンリストです。

### 「スタイル」タブ {#styles-tab}

タブを使用して、コンポーネントの CSS スタイルの定義と管理を行います。アダプティブフォームの日付選択コアコンポーネントは、AEM の[スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

![デザインダイアログの「タイトル」タブ](/help/adaptive-forms/assets/title_styles.png)

* **デフォルトの CSS クラス**：アダプティブフォームの日付選択コアコンポーネントのデフォルト CSS クラスを指定できます。

* **許可されたスタイル**：スタイルを表す名前と CSS クラスを指定することで、スタイルを定義できます。例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight: bold」を指定できます。アダプティブフォームエディターでアダプティブフォームにこれらのスタイルを使用または適用できます。スタイルを適用するには、アダプティブフォームエディターでスタイルを適用するコンポーネントを選択し、「プロパティ」ダイアログに移動して「**スタイル**」ドロップダウンリストから希望のスタイルを選択します。スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新して変更を保存します。

### 「形式」タブ {#format-tab}

「形式」タブでは、デフォルトおよびカスタムの日付形式を指定できます。

![「形式」タブ](/help/adaptive-forms/assets/title_styles.png)

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
>* [電話入力](/help/adaptive-forms/components/telephone-input.md)
>* [テキスト入力](/help/adaptive-forms/components/text-input.md)
>* [テキスト](/help/adaptive-forms/components/text.md)
>* [ウィザード](/help/adaptive-forms/components/wizard.md)

## 関連トピック {#see-also}

{{see-also}}