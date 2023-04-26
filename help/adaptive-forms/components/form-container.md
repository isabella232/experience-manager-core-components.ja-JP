---
title: アダプティブフォームのコアコンポーネント - フォームコンテナ
description: Web ページへのアダプティブフォームの追加。
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: ht
source-wordcount: '719'
ht-degree: 100%

---


# フォームコンテナ {#form-container-adaptive-forms-core-component}

フォームを使用して価値のある情報を提供すると、web サイトの訪問者のエンゲージメントとユーザー満足度を高めることができます。Adobe Experience Manager（AEM）Sites のアダプティブフォームコンテナを使用すると、web サイトの所有者は、ページに簡単にフォームを追加できます。これにより、訪問者がフィードバックの提供や問い合わせなどのアクションを合理化することで、web サイトの訪問者と web サイトの所有者または組織とのコミュニケーションが容易になります。

## 使用方法 {#reasons-to-use-forms-container}

フォームを web サイトに追加したほうが良い理由はいくつかあります。

* **データ収集**：フォームを使用して、市場調査やユーザー行動分析など、様々な目的で web サイトの訪問者からデータを収集できます。

* **リードジェネレーション**：フォームを使用して、見込み客から名前やメールアドレスなどの情報を収集し、販売やマーケティング活動のリードを生成できます。

* **e コマース**：フォームをオンラインショッピングに使用すると、顧客は web サイトを通じて注文や支払いを行えるようになります。

* **問い合わせ**：問い合わせフォームを使用すると、web サイトの訪問者は web サイトの所有者や組織に簡単に連絡できます。

* **調査および投票**：フォームは、調査や調査を通じて web サイトの訪問者からフィードバックや意見を収集するのに使用できます。

* **イベント登録**：フォームをイベント登録に使用すると、web サイトの訪問者はイベントや web セミナーに登録できます。

* **購読**：フォームを web サイトの購読に使用すると、訪問者がニュースレターやその他の標準のコミュニケーションに新規登録できます。

* **ユーザー認証**：フォームをユーザー認証に使用すると、web サイトの訪問者がアカウントを作成し、ログインして制限されたコンテンツや機能にアクセスできるようになります。

* **コンバージョン率の向上**：適切に設計されたフォームがあると、製品の購入やサービスへの新規登録など、ユーザーが簡単に目的のアクションを完了できるようにすることで、コンバージョン率を高めることができます。


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

* **事前入力サービス** - このオプションを使用すると、ユーザーはアダプティブフォームのレンダリング時にデータを取得するための事前入力サービスを選択できます。詳しくは、[事前入力サービスの作成および設定方法](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=ja#aem-forms-custom-prefill-service)を参照してください

* **クライアントライブラリカテゴリ** - ユーザーはアダプティブフォームごとにカスタム JavaScript ライブラリを設定できます。 jquery および underscore.js サードパーティライブラリに依存する再利用可能な関数のみを、ライブラリに保持することをお勧めします。

### 「送信」タブ {#submission-tab}

![「送信」タブ](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

ユーザーは、アダプティブフォームの送信に対して様々なアクションを設定できます。

* **リダイレクト URL／パス** - このオプションを使用すると、ユーザーはアダプティブフォームの送信後にユーザーがリダイレクトされる各フォームのページを設定できます。詳しくは、[リダイレクトページの設定方法](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=ja)を参照してください。

![「メッセージを表示」タブ](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **メッセージを表示** - このオプションを使用すると、ユーザーはアダプティブフォームが正常に送信されたときに表示されるメッセージを追加できます。定義済みのテキストはダイアログボックスに含まれ、ユーザーが変更できます。「メッセージを表示」ダイアログでは、追加したテキストを書式設定できるリッチテキスト形式のツールがサポートされています。

* **送信アクション** - 送信アクションは、ユーザーがアダプティブフォームの「送信」ボタンをクリックしたときにトリガーされます。ユーザーは、すぐに使用できるよう用意されているドロップダウンリストから「送信アクション」を選択することができます。詳しくは、[「送信」タブでの送信アクションの設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=ja#supporting-custom-functions-in-validation-expressions-br)を参照してください。
