---
title: アダプティブFormsコアコンポーネント — フォームコンテナ
description: アダプティブフォームを Web ページに追加します。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---


# フォームコンテナ {#form-container-adaptive-forms-core-component}

Formsを使用すると、Web サイトの訪問者は、価値のある情報を提供することで Web サイトとやり取りでき、エンゲージメントとユーザー満足度を高めることができます。 Adobe Experience Manager(AEM)Sites のアダプティブフォームコンテナを使用すると、Web サイトの所有者は、ページに簡単にフォームを追加できます。 これにより、訪問者がフィードバックを提供し、問い合わせを行い、その他のアクションを実行するのを合理化し、Web サイトの訪問者と Web サイトの所有者または組織とのコミュニケーションを容易にします

## 使用方法 {#reasons-to-use-forms-container}

フォームが Web サイトに追加される理由はいくつかあります。

* **データ収集**:Formsを使用して、市場調査、ユーザー行動分析など、様々な目的で web サイトの訪問者からデータを収集できます。

* **リードジェネレーション**:フォームを使用して、名前や電子メールアドレスなど、見込み客から情報を収集し、販売やマーケティング活動のリードを生成できます。

* **E コマース**:Formsはオンラインショッピングに使用でき、顧客は注文をし、Web サイトを通じて支払いを行うことができます。

* **連絡先**:コンタクトフォームを使用すると、Web サイトの訪問者は、Web サイトの所有者や組織に簡単にアクセスできます。

* **調査および投票**:Formsは、調査や調査を通じて、web サイトの訪問者からフィードバックや意見を収集するのに使用できます。

* **イベント登録**:Formsをイベント登録に使用すると、Web サイトの訪問者がイベントやウェビナーに登録できます。

* **購読**:Formsを web サイトの購読に使用すると、訪問者がニュースレターやその他の通常のコミュニケーションに新規登録できます。

* **ユーザー認証**:Formsをユーザー認証に使用すると、Web サイトの訪問者がアカウントを作成し、ログインして排他的なコンテンツや機能にアクセスできます。

* **コンバージョン率を上げる**:適切に設計されたフォームは、製品の購入やサービスへの新規登録など、ユーザーが簡単に目的のアクションを実行できるようにすることで、コンバージョン率を高めることができます。


## バージョンと互換性 {#version-and-compatibility}

アダプティブForms Container コアコンポーネントは、コアコンポーネント 2.0.4 の一部として 2023 年 2 月にリリースされました。次の表に、サポートされているすべてのバージョン、AEMの互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | 互換性あり<br>[リリース 2.0.4](/help/versions.md) 以降 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、 [コアコンポーネントのバージョン](/help/versions.md) 文書。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

アダプティブFormsコンテナコアコンポーネントの最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](/help/developing/overview.md).

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、フォームコンテナのエクスペリエンスを訪問者に合わせて簡単にカスタマイズできます。 また、シームレスなユーザーエクスペリエンスを実現するために、簡単にフォームコンテナオプションを定義できます。

### 基本タブ {#basic-tab}

![「基本」タブ](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **事前入力サービス**  — このオプションを使用すると、アダプティブフォームのレンダリング時にデータを取得するための事前入力サービスを選択できます。 詳細情報： [事前入力サービスの作成および設定方法](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

* **クライアントライブラリカテゴリ** ：ユーザーは、アダプティブフォームごとにカスタム JavaScript ライブラリを設定できます。 jquery および underscore.js サードパーティライブラリに依存する再利用可能な関数のみをライブラリに保持することをお勧めします。

### 「送信」タブ {#submission-tab}

![「送信」タブ](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

ユーザーは、アダプティブフォームの送信に対して様々なアクションを設定できます。

* **リダイレクト URL/パス**  — このオプションを使用すると、ユーザーはアダプティブフォームの送信後にフォームユーザーがリダイレクトされるページを各フォームに設定できます。 詳しくはここをクリック [リダイレクトページの設定方法](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![「メッセージ」タブを表示](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **メッセージを表示**  — このオプションを使用すると、アダプティブフォームが正常に送信されたときに表示されるメッセージを追加できます。 定義済みのテキストはダイアログボックスに含まれ、ユーザーが変更できます。 メッセージを表示ダイアログでは、追加したテキストを書式設定できるリッチテキスト書式設定ツールがサポートされています。

* **送信アクション**  — ユーザーがアダプティブフォームの「送信」ボタンをクリックすると、送信アクションがトリガーされます。 ユーザーは、ドロップダウンリストから「送信アクション」を選択して、すぐに使用できる状態でサポートされます。 方法を学ぶ [「送信」タブでの送信アクションの設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).




