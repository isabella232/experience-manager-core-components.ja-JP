---
title: アダプティブFormsコアコンポーネント — タイトル
description: アダプティブFormsタイトルコアコンポーネントの使用またはカスタマイズ。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 15%

---


# タイトル {#title-input-adaptive-forms-core-component}

アダプティブフォームでは、「タイトル」は、フォームの上部（通常、ヘッダーの下）に表示されるテキストを指します。 タイトルは、タイトルコンポーネントを使用して指定します。 このコンポーネントをフォームレイアウトに追加し、そのテキストをフォームの目的やトピックに合わせて編集できます。 タイトルは、ユーザーに対するフォームのラベルまたは簡単な説明として機能し、フォームを他のユーザーと区別するのに役立ちます。

**例**

![](/help/adaptive-forms/assets/title.png)

## 使用方法 {#reasons-to-use-title-in-an-adaptive-form}

フォームでタイトルを使用することをお勧めする理由はいくつかあります。

* **明確さ**:タイトルは、フォームの目的を明確に示し、ユーザーが提供する必要のある情報を理解するのに役立ちます。

* **組織**:タイトルを指定すると、トピック別または目的別にフォームを整理し、必要なフォームを簡単に見つけることができます。

* **アクセシビリティ**:タイトルは、スクリーンリーダーで読み上げられ、ユーザーがフォームのコンテキストを理解するのに役立つ、アクセシビリティのニーズを持つユーザーにとって重要な要素です。

* **ブランディング**:タイトルを使用して、会社または組織の名前を表示することもできます。これは、信頼感を作り出し、ユーザーに慣れるのに役立ちます。

* **ナビゲーション**:タイトルは、特にフォームが長い場合や複雑な場合に、フォーム内を移動する際にも役立ちます。

* **検索エンジン最適化 (SEO)**:フォームにタイトルを付けると、SEO でも役立ちます。検索エンジンでは、タイトルを使用して検索クエリに対する Web ページの関連度を判断します。

全体的に、フォームのタイトルはユーザーエクスペリエンスの重要な側面であり、フォームのコンテキストと目的を理解するのに役立つ、明確で簡潔なラベルをフォームに指定する場合に使用します。

## バージョンと互換性 {#version-and-compatibility}

アダプティブFormsタイトルコアコンポーネントは、コアコンポーネント 2.0.4 の一部として 2023 年 2 月にリリースされました。次の表に、サポートされているすべてのバージョン、AEMの互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | 互換性あり<br>[リリース 2.0.4](/help/versions.md) 以降 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、 [コアコンポーネントのバージョン](/help/versions.md) 文書。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術的詳細 {#technical-details}

アダプティブFormsタイトルコアコンポーネントの最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](/help/developing/overview.md).

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者に対するタイトルエクスペリエンスを簡単にカスタマイズできます。 また、簡単にタイトルオプションを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

![「基本」タブ](/help/adaptive-forms/assets/title_properties.png)

編集ダイアログでは、コンテンツ作成者がタイトルテキストを定義したり、見出しレベルを選択したりできます。

* **タイトル**  — タイトルを使用すると、フォーム内のコンポーネントを簡単に識別でき、デフォルトでは、タイトルがコンポーネントの上に表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。
* **種類 / サイズ** - タイトルの見出しレベルを定義します.
* **ID** - このオプションを使用すると、HTML 内およびデータレイヤー内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

## デザインダイアログ {#design-dialog}

デザインダイアログは、日付選択コンポーネントの CSS スタイルを定義および管理するために使用されます。

### タイトル

「タイトル」タブを使用すると、テンプレート作成者は、フォーム作成者にデフォルトの許可されるHTML見出し要素と許可される見出し要素を設定できます。

![デザインダイアログの「タイトル」タブ](/help/assets/accordion-design-properties.png)

* **許可されている見出し要素**:作成者がタイトルに使用できる見出し要素をテンプレート作成者が選択できる、複数のオプションを含むリストです。

* **デフォルトの見出し要素**:タイトルコンポーネントのデフォルトの見出し要素を設定するドロップダウンリストです。


### 「スタイル」タブ {#styles-tab}

デザインダイアログは、コンポーネントの CSS スタイルを定義および管理するために使用します。 アダプティブFormsの日付選択コアコンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling).

**デフォルトの CSS クラス**:アダプティブForms日付選択コアコンポーネントのデフォルト CSS クラスを指定できます。

**許可されたスタイル**:スタイルを定義するには、スタイルを表す名前と CSS クラスを指定します。 例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight」を指定できます。太字」 アダプティブフォームに対して、アダプティブFormsエディターでこれらのスタイルを使用または適用できます。 スタイルを適用するには、アダプティブFormsエディターで、スタイルを適用するコンポーネントを選択し、プロパティダイアログに移動して、 **スタイル** 」ドロップダウンリストから選択できます。 スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新し、変更を保存します。

### 「形式」タブ {#format-tab}

「形式」タブでは、デフォルトおよびカスタムの日付形式を指定できます。
