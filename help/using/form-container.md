---
title: フォームコンテナコンポーネント
description: コアコンポーネントのフォームコンテナコンポーネントを使用すれば、シンプルな送信フォームを作成できます。
translation-type: tm+mt
source-git-commit: 60df01ca9efe59b67bad57610d04496a2cdded9e

---


# フォームコンテナコンポーネント{#form-container-component}

コアコンポーネントのフォームコンテナコンポーネントを使用すれば、シンプルな送信フォームを作成できます。

## 使用方法 {#usage}

フォームコンテナコンポーネントでは、シンプルな WCM フォームをサポートし、フォームコンポーネントの追加が可能なネスト構造を使用しているので、シンプルな情報送信フォームおよび機能を作成できます。

[設定ダイアログ](#configure-dialog)を使用して、コンテンツ編集者は、フォーム送信でトリガーされるアクション、送信されたコンテンツの保存先、ワークフローをトリガーするかどうかを定義できます。The template author can use the [design dialog](#design-dialog) to define the allowed components and their mappings similar to the design dialog for the [standard layout container in the template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>コアコンポーネントのフォームコンテナコンポーネントでは、コアコンポーネントのフォームコンポーネント（ボタン、テキスト、非表示など）のみ使用できます。Using [foundation components](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) form components within the core components form container (and vice versa) is not supported.

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、フォームコンテナコンポーネントの現在のバージョン（2018 年 1 月にコアコンポーネントのリリース 2.0.0 で導入された v2）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 | クラウドサービスとしてのAEM |
|--- |--- |--- |--- |---|
| v2 | 互換性あり | 互換性あり | 互換性あり | 互換性あり |
| [v1](form-container-v1.md) | 互換性あり | 互換性あり | 互換性あり | - |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](versions.md)を参照してください。

## 技術的詳細 {#technical-details}

The latest technical documentation about the Form Container Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2).

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンポーネントの送信時に実行されるアクションをコンテンツ作成者が定義できます。

![](assets/screen_shot_2018-01-12at122046.png)

選択した&#x200B;**アクションタイプ**&#x200B;に応じて、コンテナ内で使用可能なオプションが変わります。使用可能なアクションタイプは次のとおりです。

* [メール](#mail)
* [コンテンツを格納](#store-content)
* [注文を送信](#submit-order)
* [注文を更新](#update-order)

タイプに関係なく、各アクションに適用される[一般的な設定](#general-settings)があります。

### メール {#mail}

アクションタイプが「メール」の場合、フォームが送信されると、指定した受信者に電子メールが送信されます。

![](assets/screen_shot_2018-01-12at122554.png)

* **件名** - フォーム送信時に送信される電子メールの件名
* **差出人** - フォーム送信時に送信される電子メールの差出人の電子メールアドレス
* **宛先-** - フォーム送信時に電子メールを受信する受信者のアドレス

   * アドレスを追加するには、「**追加**」ボタンをタップまたはクリックします
   * 電子メールアドレスを削除するには、「**削除**」ボタンをタップまたはクリックします
* **CC** - フォーム送信時に送信される電子メールのカーボンコピーを受信する受信者のアドレス
   * アドレスを追加するには、「**追加**」ボタンをタップまたはクリックします
   * 電子メールアドレスを削除するには、「**削除**」ボタンをタップまたはクリックします

### コンテンツを格納 {#store-content}

フォームが送信されると、フォームのコンテンツは、指定されたリポジトリの場所に保存されます。

![](assets/screen_shot_2018-01-12at122538.png)

* **コンテンツのパス** - 送信されたコンテンツが格納されるコンテンツリポジトリのパス
* **データを表示** - タップまたはクリックすると、保存された送信済みデータが JSON 形式で表示されます
* **ワークフローを開始** - 保存されたコンテンツをフォーム送信時のペイロードとして使用し、ワークフローを開始するように設定します

### 注文を送信 {#submit-order}

フォームが送信されると、注文が送信されます。

![](assets/chlimage_1-3.png)

### 注文を更新 {#update-order}

フォームが送信されると、注文が更新されます。

![](assets/chlimage_1-4.png)

### 一般的な設定 {#general-settings}

「ありがとうございます」ページは、選択したアクションタイプに関係なくいつでも定義できます。

![](assets/chlimage_1-5.png)

フォーム送信の完了後、ユーザーは指定したページにリダイレクトされます。

* 選択ダイアログを使用して、AEM 内のリソースを選択します。
* 「ありがとうございます」ページが AEM にない場合は、絶対 URL を指定します。絶対 URL 以外の URL は、AEM からの相対 URL と解釈されます。
* 空白のままにすると、送信後にフォームが再度表示されます。

## デザインダイアログ{#design-dialog}

The design dialog allows the template author to define the allowed components and their mappings for the container similar to the design dialog for the [standard layout container in the template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).
