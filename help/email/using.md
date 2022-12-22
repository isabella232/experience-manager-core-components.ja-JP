---
title: メールコアコンポーネントの使用
description: メールコアコンポーネントの基本的なインストール、設定および使用について説明します。
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: ht
source-wordcount: '653'
ht-degree: 100%

---


# メールコアコンポーネントの使用 {#using}

メールコアコンポーネントの基本的なインストール、設定および使用について説明します。

## メールコアコンポーネントのインストール {#installation}

メールコアコンポーネントは、AEM 6.5 で使用できます。詳しくは、[メールコアコンポーネントの概要ドキュメントの要件](introduction.md#requirements)を参照してください。

### コアコンポーネントのインストール {#core-components}

メールコアコンポーネントは、AEM コアコンポーネントに基づいて構築されています。 コアコンポーネントは AEM 6.5 に付属していないので、まず AEM コアコンポーネントをインストールしてからメールコアコンポーネントをインストールする必要があります。

コアコンポーネントのインストール方法について詳しくは、「コアコンポーネントの使用」ドキュメントの[ダウンロードとインストール](/help/get-started/using.md#download-and-install)の節を参照してください。

### メールコアコンポーネントのインストール {#email-core-components}

インスタンスにコアコンポーネントをインストールしたら、メールコアコンポーネントも同様にインストールする必要があります。 メールコアコンポーネントは、まだ AEM プロジェクトアーキタイプに含まれていないので、手動でプロジェクトに追加する必要があります。 [インストールするには、メールコアコンポーネント GitHub Wiki](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project) のドキュメントに従います。

メールコアコンポーネントを使用するように既存のプロジェクトを適応させる場合も、同じ手順に従います。

## 設定 {#configuration}

コアコンポーネントをインストールした後、2 つの重要な設定手順を実行する必要があります。

### キャンペーンの設定 {#configure-campaign}

AEM と Adobe Campaign の統合を設定して、これら 2 つのソリューションが通信できるようにする必要があります。

* Adobe Campaign 統合の設定
   * Adobe Campaign Classic：[Adobe Campaign Classic との統合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=ja)
   * Adobe Campaign Standard：[Adobe Campaign Standard との統合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=ja)
* メールコアコンポーネントを使用するコンテンツページに [Adobe Campaign 統合設定をリンク](/help/email/components/page.md#cloud-services-tab)します。

### メールコンポーネントの AEM リソースタイプフィルターの追加 {#aem-resource-filter}

Adobe Campaign がメールコアコンポーネントに基づいてメールをレンダリングできるようにするには、Campaign でフィルターを調整する必要があります。

1. クライアントコンソールを使用して、Adobe Campaign に管理者としてログインします。

1. メニューバーから&#x200B;**ツール**／**エクスプローラー**&#x200B;を選択します。

1. エクスプローラーで、**管理**／**プラットフォーム**／**オプション**&#x200B;ノードに移動します。

1. リストから「`AEMResourceTypeFilter`」オプションを選択します。

1. 「**値**」フィールドに `core/email/components/page/<v1>/page` を追加します（まだ存在しない場合）。

   * `<v1>` を、メールコアコンポーネントの[ページコンポーネント](/help/email/components/page.md)の最新バージョン（例：`v1`）に置き換えます。
   * なお、「**値**」フィールドの値はコンマで区切る必要があります。

1. 「**保存**」をクリックします。

## メールコアコンポーネントの使用 {#using-components}

メールコンポーネントをインストールし、Adobe Campaign との統合を設定したら、メールコンポーネントを使用して AEM でメールコンテンツを作成したあと、Adobe Campaign を使用してそのコンテンツを受信者に送信できます。 以下は、そのワークフローの概要です。

| 手順 | 説明 | ソリューション |
|---|---|---|
| 1 | 作成者は、フォルダーとメールコンテンツで構成される自由形式の階層構造をページとして作成します。 | AEM |
| 2 | [テンプレートエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)を使用して、作成者は、このページテンプレートから生成されるすべてのメールページで共有されるメールのヘッダーやフッターを設定します。 | AEM |
| 3 | 作成者は、[ページエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html?lang=ja)を使用してテキストエディターでメールコンテンツを作成します。エディターでは、Adobe Campaign の変数を選択し、セグメント化コンポーネントを使用して、受信者が特定の条件を満たす場合に条件付きで情報を表示できます。 | AEM |
| 4 | メールのコンテンツが完成すると、コンテンツを承認して Campaign に送信するための[ワークフローが実行されます](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html?lang=ja)。 | AEM |
| 5 | 配信が作成され、受信者のリストが定義されます。 | Campaign |
| 6 | AEM で作成されたコンテンツが配信のコンテンツとして選択されます。 | Campaign |
| 7 | コンテンツが受信者に送信され、Adobe Campaign 変数が受信者のパーソナライズされた情報に置き換えられます。 | Campaign |

AEM で電子メールコンテンツを作成し、Adobe Campaign で配信する例については、次のリソースを参照してください。

* AEM 6.5：[Adobe Campaign Classic および Adobe Campaign Standard との連携](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html?lang=ja)
