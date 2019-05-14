---
title: Form Container Component
seo-title: Form Container Component
description: 'null'
seo-description: Core Component Form Container Componentを使用すると、単純な送信フォームを作成できます。
uuid: 9d556daf-3fe7-4b2a- b5ae-6926acb267a9
contentOwner: ユーザーは、
content-type: リファレンス
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: 3d33fe60- a0ac-4ff2- a865- d600b5448eb
disttype: dist5
gnavtheme: light
groupsectionnavitems: ' '
hidemerchandisingbar: inherit
hidepromocomponent: inherit
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 62643e5bd49ab006230f65004bb9374822dcc017

---


# Form Container Component{#form-container-component}

Core Component Form Container Componentを使用すると、単純な送信フォームを作成できます。

## 使用方法 {#usage}

フォームコンテナコンポーネントを使用すると、単純WCMフォームをサポートし、ネストされた構造を使用して追加のフォームコンポーネントを許可することで、単純な情報送信フォームと機能を構築できます。

設定ダイアログを [使用することで、コンテンツエディター](#configure-dialog) では、フォーム送信によってトリガーされるアクション、送信されたコンテンツが保存されるアクション、ワークフローをトリガーするかどうかを定義できます。テンプレート作成者は [、デザインダイアログ](#design-dialog) を使用して、テンプレートエディターの [標準レイアウトコンテナのデザインダイアログと同様のコンポーネントおよびそのマッピングを定義](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)できます。

>[!NOTE]
>
>コアコンポーネントのForm Container Componentは、コアコンポーネントフォームコンポーネント（ボタン、テキスト、非表示など）の使用のみをサポートします。コアコンポーネントフォームコンテナ内の [基盤コンポーネント](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) フォームコンポーネント（またはその逆）はサポートされていません。

## バージョンと互換性 {#version-and-compatibility}

現在のバージョンのForm Container Componentはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](form-container-v1.md) | 互換性 | 互換性 | 互換性 |

コアコンポーネントバージョンとリリースについて詳しくは、ドキュメント [コアコンポーネントバージョン](versions.md)を参照してください。

## 技術的詳細 {#technical-details}

Form Container Componentに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container)。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## ダイアログの設定 {#configure-dialog}

設定ダイアログでは、コンテンツ作成者がコンポーネントの送信時に実行するアクションを定義できます。

![](assets/screen_shot_2018-01-12at122046.png)

選択した **アクションタイプ**に応じて、コンテナ内の使用可能なオプションが変更されます。使用可能なアクションタイプは次のとおりです。

* [メール](#mail)
* [コンテンツを格納](#store-content)
* [注文を送信](#submit-order)
* [注文を更新](#update-order)

タイプに関係なく、各アクションに適用される [一般的な設定](#general-settings) があります。

### メール {#mail}

フォームが送信されると、メールアクションタイプによって指定した受信者に電子メールが送信されます。

![](assets/screen_shot_2018-01-12at122554.png)

* **件名**フォーム送信時に送信される電子メールの件名
* **フォーム**送信時に送信される電子メールの電子メールアドレスから
* **フォーム**送信時に電子メールを受信する受信者のアドレス

   * 追加のアドレスを追加するには、「 **追加」** ボタンをタップまたはクリックします
   * 「 **削除** 」ボタンをタップまたはクリックして電子メールアドレスを削除します
* **CC**フォーム送信時に送信される電子メールをカーボンコピーする受信者のアドレス
   * 追加のアドレスを追加するには、「 **追加」** ボタンをタップまたはクリックします
   * 「 **削除** 」ボタンをタップまたはクリックして電子メールアドレスを削除します

### コンテンツを格納 {#store-content}

フォームが送信されると、フォームのコンテンツは指定されたリポジトリの場所に保存されます。

![](assets/screen_shot_2018-01-12at122538.png)

* **コンテンツパス**コンテンツリポジトリパス送信されたコンテンツが保存される場所
* **データ**をタップまたはクリックして、保存済みのデータをJSONとして表示します
* **フォームの送信時にペイロードとして保存されたコンテンツを含むワークフローを開始するようにワークフロー**設定を開始

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

テンプレート作成者は、テンプレート作成者がテンプレートエディターの [標準レイアウトコンテナのデザインダイアログに類似したコンポーネントとコンテナのマッピングを定義](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)できます。