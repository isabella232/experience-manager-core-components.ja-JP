---
title: アダプティブフォームのコアコンポーネント - フォームコンテナ
description: Web ページへのアダプティブフォームの追加。
role: Architect, Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
source-git-commit: 4d01c75fadb0220f0093a6647c27c4002cc979c9
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 91%

---

# フォームコンテナ {#form-container-adaptive-forms-core-component}

フォームを使用して価値のある情報を提供すると、web サイトの訪問者のエンゲージメントとユーザー満足度を高めることができます。Adobe Experience Manager（AEM）Sites のアダプティブフォームコンテナを使用すると、web サイトの所有者は、ページに簡単にフォームを追加できます。これにより、訪問者がフィードバックの提供や問い合わせなどのアクションを合理化することで、web サイトの訪問者と web サイトの所有者または組織とのコミュニケーションが容易になります。

## 使用方法 {#reasons-to-use-forms-container}

フォームを web サイトに追加したほうが良い理由はいくつかあります。

- **データ収集**：フォームを使用して、市場調査やユーザー行動分析など、様々な目的で web サイトの訪問者からデータを収集できます。

- **リードジェネレーション**：フォームを使用して、見込み客から名前やメールアドレスなどの情報を収集し、販売やマーケティング活動のリードを生成できます。

- **e コマース**：フォームをオンラインショッピングに使用すると、顧客は web サイトを通じて注文や支払いを行えるようになります。

- **問い合わせ**：問い合わせフォームを使用すると、web サイトの訪問者は web サイトの所有者や組織に簡単に連絡できます。

- **調査および投票**：フォームは、調査や調査を通じて web サイトの訪問者からフィードバックや意見を収集するのに使用できます。

- **イベント登録**：フォームをイベント登録に使用すると、web サイトの訪問者はイベントや web セミナーに登録できます。

- **購読**：フォームを web サイトの購読に使用すると、訪問者がニュースレターやその他の標準のコミュニケーションに新規登録できます。

- **ユーザー認証**：フォームをユーザー認証に使用すると、web サイトの訪問者がアカウントを作成し、ログインして制限されたコンテンツや機能にアクセスできるようになります。

- **コンバージョン率の向上**：適切に設計されたフォームがあると、製品の購入やサービスへの新規登録など、ユーザーが簡単に目的のアクションを完了できるようにすることで、コンバージョン率を高めることができます。


## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブフォームコンテナのコアコンポーネントの最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container)のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、フォームコンテナのエクスペリエンスを訪問者に合わせて簡単にカスタマイズできます。 また、フォームコンテナオプションを簡単に定義でき、シームレスなユーザーエクスペリエンスを実現できます。

### 「基本」タブ {#basic-tab}

![「基本」タブ](/help/adaptive-forms/assets/formcontainer_basictab.png)

- **事前入力サービス** - このオプションを使用すると、ユーザーはアダプティブフォームのレンダリング時にデータを取得するための事前入力サービスを選択できます。詳しくは、[事前入力サービスの作成および設定方法](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=ja#aem-forms-custom-prefill-service)を参照してください

- **クライアントライブラリカテゴリ** - ユーザーはアダプティブフォームごとにカスタム JavaScript ライブラリを設定できます。 jquery および underscore.js サードパーティライブラリに依存する再利用可能な関数のみをライブラリに保持することをお勧めします。
場合によっては、 **複雑な検証ルール**&#x200B;に設定されている場合、正確な検証スクリプトはカスタム関数に存在し、ユーザーはこれらのカスタム関数をフィールド検証式から呼び出します。 サーバー側の検証を実行する際に、このカスタム関数ライブラリを既知で使用可能にするには、フォームユーザーが、 **[!UICONTROL 基本]** タブを使用して、アダプティブフォームコンテナのプロパティを次に示します。

ユーザーは、アダプティブフォームごとに customJavaScript ライブラリを設定できます。 ライブラリには、jQuery および underscore.js サードパーティライブラリに依存する、再利用可能な関数のみを保持します。

### 「データモデル」タブ {#data-model-tab}

![「送信」タブ](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

フォームデータモデルを使用してフォームをデータソースに接続し、ユーザーのアクションに基づいてデータを送受信することができます。また、フォームを JSON スキーマに接続して、送信されたデータを事前定義済みの形式で受信することもできます。必要に応じて、フォームを JSON スキーマまたはフォームデータモデルに接続します。
- JSON スキーマの作成と環境へのアップロード
- フォームデータモデルを作成

### 「送信」タブ {#submission-tab}

![「送信」タブ](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

ユーザーは、アダプティブフォームの送信に対して様々なアクションを設定できます。

- **リダイレクト URL／パス** - このオプションを使用すると、ユーザーはアダプティブフォームの送信後にユーザーがリダイレクトされる各フォームのページを設定できます。詳しくは、[リダイレクトページの設定方法](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=ja)を参照してください。

![「メッセージを表示」タブ](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **メッセージを表示** - このオプションを使用すると、ユーザーはアダプティブフォームが正常に送信されたときに表示されるメッセージを追加できます。定義済みのテキストはダイアログボックスに含まれ、ユーザーが変更できます。「メッセージを表示」ダイアログでは、追加したテキストを書式設定できるリッチテキスト形式のツールがサポートされています。

- **送信アクション** - 送信アクションは、ユーザーがアダプティブフォームの「送信」ボタンをクリックしたときにトリガーされます。ユーザーは、すぐに使用できるよう用意されているドロップダウンリストから「送信アクション」を選択することができます。詳しくは、[「送信」タブでの送信アクションの設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=ja#supporting-custom-functions-in-validation-expressions-br)を参照してください。

## デザインダイアログ {#design-dialog}

デザインダイアログでは、フォームコンテナコンポーネントの CSS スタイルを定義および管理できます。

### 「許可されたコンポーネント」タブ {#allowed-components-tab}

![デザインダイアログの「許可されたコンポーネント」タブ](/help/adaptive-forms/assets/formcontainer-allowedcomponents.png)

「**許可されたコンポーネント**」タブでは、テンプレートエディターで、アダプティブフォームエディターのコンポーネント内のパネルに、項目として追加できるコンポーネントを設定できます。

### デフォルトの「コンポーネント」タブ {#default-components-tab}

![デザインダイアログのデフォルトの「コンポーネント」タブ](/help/adaptive-forms/assets/formcontainer-defaultcomponents.png)

「**デフォルトのコンポーネント**」タブでは、テンプレートエディターで、デフォルトで表示されるコンポーネントを、アダプティブフォームエディター内のフォームコンテナコンポーネント内の項目として指定できます。

### 「レスポンシブ設定」タブ {#responsive-tab}

![デザインダイアログの「レスポンシブ設定」タブ](/help/adaptive-forms/assets/formcontainer-responsivestyle.png)

「**レスポンシブ設定**」タブでは、テンプレートエディターで、アダプティブフォームエディターのフォームコンテナコンポーネント内のグリッドの列数を指定できます。

### 「スタイル」タブ {#styles-tab}

アダプティブフォームのファイル添付コアコンポーネントは、AEM の[スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

![デザインダイアログ](/help/adaptive-forms/assets/formcontainer-styletab.png)

- **デフォルトの CSS クラス**：アダプティブFormsフォームコンテナのコアコンポーネントのデフォルト CSS クラスを指定できます。

- **許可されたスタイル**：スタイルを表す名前と CSS クラスを指定してスタイルを定義します。 例えば、「bold text」という名前のスタイルを作成し、CSS クラス「font-weight: bold」を指定できます。アダプティブフォームエディターでアダプティブフォームにこれらのスタイルを使用または適用できます。スタイルを適用するには、アダプティブフォームエディターでスタイルを適用するコンポーネントを選択し、「プロパティ」ダイアログに移動して「**スタイル**」ドロップダウンリストから希望のスタイルを選択します。スタイルを更新または変更する必要がある場合は、デザインダイアログに戻り、「スタイル」タブでスタイルを更新して変更を保存します。

### 「カスタムプロパティ」タブ

![カスタムプロパティダイアログ](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

カスタムプロパティを使用すると、フォームテンプレートを使用してカスタム属性（キーと値のペア）をアダプティブフォームのコアコンポーネントに関連付けることができます。カスタムプロパティは、コンポーネントのヘッドレスレンディションのプロパティセクションに反映されます。これにより、カスタム属性値に基づいて適応する動的なフォーム動作を作成できます。例えば、開発者は、モバイル、デスクトップ、web プラットフォーム上にヘッドレスフォームコンポーネントの様々なレンディションをデザインできるので、幅広いデバイスでのユーザーエクスペリエンスが大幅に向上します。

- **グループ名**：カスタムプロパティグループを識別する名前を指定できます。複数のカスタムプロパティグループを追加、削除または並べ替えることができます。カスタムプロパティグループを追加すると、次のオプションが表示されます。

   - **キーと値のペア**：各カスタムプロパティグループの「**追加**」ボタンをクリックすると、複数のカスタムプロパティ名とカスタムプロパティ値を追加できます。

   - **削除**：タップまたはクリックすると、カスタムプロパティ名とカスタムプロパティ値を削除できます。

   - **並べ替え**：タップまたはクリックしてドラッグすると、カスタムプロパティ名とカスタムプロパティ値の順序を並べ替えることができます。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 関連記事 {#related-articles}

{{more-like-this}}

## 関連トピック {#see-also}

{{see-also}}