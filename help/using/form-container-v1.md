---
title: Form Container Component（v1）
seo-title: Form Container Component（v1）
description: Core Component Form Container Componentを使用すると、単純な送信フォームを作成できます。
seo-description: Core Component Form Container Componentを使用すると、単純な送信フォームを作成できます。
uuid: 075d83ed- de40-414e- a18f-46b3a857acba
content-type: リファレンス
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: 800c064e-2ad5-41f3-9xf- b025a555efd9
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Form Container Component（v1）{#form-container-component-v}

Core Component Form Container Componentを使用すると、単純な送信フォームを作成できます。

## 使用方法 {#usage}

Form Container Componentは、単純なWCMフォームをサポートし、ネストされた構造を使用して追加のフォームコンポーネントを許可することで、単純な情報送信フォームと機能の構築を有効にしました。

[設定ダイアログ](form-container-v1.md#main-pars_title) を使用することで、コンテンツエディターは、アクションフォーム送信トリガーの種類、送信されたコンテンツの保存先、ワークフローをトリガーする場合に定義できます。テンプレート作成者は [、テンプレートエディターの標準レイアウトコンテナのデザインダイアログと同様に、デザインダイアログ](form-container-v1.md#main-pars_title_1995166862) を使用して [、コンポーネントとそのマッピングを定義](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)できます。

## バージョンと互換性 {#version-and-compatibility}

本書では、元々、コアコンポーネントのリリース1.0.0とAEM6.3で導入された、Form Container Componentのv1について説明します。

次の表に、Form Container Componentのv1との互換性を示します。

| AEM のバージョン | Form Container Component v1 |
|--- |--- |
| 6.3 | 互換性 |
| 6.4 | 互換性 |

>[!CAUTION]
>
>このドキュメントでは、Form Container Componentのv1について説明します。
>
>Form Container Componentの現在のバージョンの詳細については [、&quot;Form Container Component](form-container.md) 」ドキュメントを参照してください。

## 設定ダイアログ {#settings-dialog}

設定ダイアログでは、コンテンツ作成者がコンポーネントの送信時に実行するアクションを定義できます。

![](assets/chlimage_1.png)

選択した **アクションタイプ**に応じて、コンテナ内の使用可能なオプションが変更されます。使用可能なアクションタイプは次のとおりです。

* [メール](form-container-v1.md#main-pars_title_966511656)
* [コンテンツを格納](form-container-v1.md#main-pars_title_2065985840)
* [注文を送信](form-container-v1.md#main-pars_title_686874527)
* [注文を更新](form-container-v1.md#main-pars_title_410109286)

タイプに関係なく、各アクションに適用される [一般的な設定](form-container-v1.md#main-pars_title_375403046) があります。

### メール {#mail}

フォームが送信されると、メールアクションタイプによって指定した受信者に電子メールが送信されます。

![](assets/chlimage_1-1.png)

* **Subject** -フォーム送信時に送信される電子メールの件名
* **From-** フォーム送信時に送信される電子メールの電子メールアドレス
* **宛先-** フォーム送信時に電子メールを受信する受信者のアドレス
   * 追加のアドレスを追加するには、「 **追加」** ボタンをタップまたはクリックします
   * 「 **削除** 」ボタンをタップまたはクリックして電子メールアドレスを削除します
* **CC** -フォーム送信時に送信される電子メールをカーボンコピーする受信者のアドレス
   * 追加のアドレスを追加するには、「 **追加」** ボタンをタップまたはクリックします
   * 「 **削除** 」ボタンをタップまたはクリックして電子メールアドレスを削除します

### コンテンツを格納 {#store-content}

フォームが送信されると、フォームのコンテンツは指定されたリポジトリの場所に保存されます。

![](assets/chlimage_1-2.png)

* **コンテンツパス** -送信されたコンテンツが保存されるコンテンツリポジトリパス
* **データを表示** -をタップまたはクリックして、保存済みのデータをJSONとして表示
* **ワークフローを開始** -フォーム送信時にペイロードとして保存されたコンテンツを含むワークフローを開始するよう設定します

### 注文を送信 {#submit-order}

フォームが送信されると、注文が送信されます。

![](assets/chlimage_1-3.png)

### 注文を更新 {#update-order}

フォームが送信されると、注文が更新されます。

![](assets/chlimage_1-4.png)

### 一般的な設定 {#general-settings}

選択したアクションタイプに関係なく、常に「ありがとうございます」ページを定義できます。

![](assets/chlimage_1-5.png)

フォーム送信の完了後、ユーザーは指定されたページにリダイレクトされます。

* 選択ダイアログを使用して、AEM内のリソースを選択します。
* 「ありがとうございます」ページがAEMにない場合は、絶対URLを指定します。絶対URL以外のURLは、AEMに対して解釈されます。
* 送信後にフォームを再度表示するには、空白のままにします。

## デザインダイアログ {#design-dialog}

テンプレート作成者は、テンプレート作成者がテンプレートエディターの [標準レイアウトコンテナのデザインダイアログに類似したコンポーネントとコンテナのマッピングを定義](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)できます。

## 技術的詳細 {#technical-details}

Form Container Componentに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)。

コアコンポーネントプロジェクト全体をGitHubからダウンロードできます。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。
