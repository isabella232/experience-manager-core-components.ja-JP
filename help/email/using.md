---
title: 電子メールコアコンポーネントの使用
description: 電子メールコアコンポーネントの基本的なインストール、設定、使用方法について説明します。
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 7%

---


# 電子メールコアコンポーネントの使用 {#using}

電子メールコアコンポーネントの基本的なインストール、設定、使用方法について説明します。

## 電子メールコアコンポーネントのインストール {#installation}

電子メールコアコンポーネントは、AEM 6.5 で使用できます。詳しくは、 [「 E メールコアコンポーネントの概要」ドキュメントの要件に関する節](introduction.md#requirements) を参照してください。

### コアコンポーネントのインストール {#core-components}

電子メールコアコンポーネントは、AEMコアコンポーネント上に構築されています。 コアコンポーネントはAEM 6.5 には付属していないので、電子メールコアコンポーネントをインストールする前に、まずAEMコアコンポーネントをインストールする必要があります。

の節を参照してください。 [ダウンロードとインストール](/help/get-started/using.md#download-and-install) コアコンポーネントのインストール方法について詳しくは、コアコンポーネントの使用を参照してください。

### 電子メールコアコンポーネントのインストール {#email-core-components}

インスタンスにコアコンポーネントをインストールしたら、電子メールコアコンポーネントも同様にインストールする必要があります。 電子メールコアコンポーネントは、まだAEMプロジェクトアーキタイプに含まれていないので、手動でプロジェクトに追加する必要があります。 ドキュメント ( [インストール先の電子メールコアコンポーネント GitHub Wiki です。](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

既存のプロジェクトを適応させてコアコンポーネントの電子メール送信を使用する場合も、同じ手順に従います。

## 設定 {#configuration}

コアコンポーネントをインストールした後、2 つの重要な設定手順を実行する必要があります。

### キャンペーンの設定 {#configure-campaign}

2 つのソリューションが通信するには、AEMとAdobe Campaignの統合を設定する必要があります。

* Adobe Campaign統合の設定
   * Adobe Campaign Classic: [Adobe Campaign Classicとの統合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard: [Adobe Campaign Standardとの統合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [Adobe Campaign統合設定のリンク](/help/email/components/page.md#cloud-services-tab) 電子メールコアコンポーネントを使用するコンテンツページに追加します。

### 電子メールコンポーネントにAEM Resource Type Filter を追加 {#aem-resource-filter}

Adobe Campaignが E メールコアコンポーネントに基づく E メールをレンダリングできるようにするには、Campaign でフィルターを調整する必要があります。

1. クライアントコンソールを使用して、Adobe Campaign に管理者としてログインします。

1. メニューバーから&#x200B;**ツール**／**エクスプローラー**&#x200B;を選択します。

1. エクスプローラーで、 **管理** -> **Platform** -> **オプション** ノード。

1. を選択します。 `AEMResourceTypeFilter` 」オプションを選択します。

1. 内 **値** フィールド、追加 `core/email/components/page/<v1>/page` （まだ存在しない場合）。

   * 置換 `<v1>` 電子メールコアコンポーネントの現在のバージョンと共に使用 [ページコンポーネント](/help/email/components/page.md) 例： `v1`.
   * なお、 **値** フィールドはコンマで区切る必要があります。

1. 「**保存**」をクリックします。

## 電子メールコアコンポーネントの使用 {#using-components}

電子メールコンポーネントをインストールし、Adobe Campaignとの統合を設定したら、電子メールコンポーネントを使用してAEMで電子メールコンテンツを作成し、Adobe Campaignを使用してそのコンテンツを受信者に送信できます。 以下は、ワークフローの概要です。

| 手順 | 説明 | ソリューション |
|---|---|---|
| 1 | 作成者は、フォルダーと E メールコンテンツをページとして自由形式の階層構造にします。 | AEM |
| 2 | の使用 [テンプレートエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja) 作成者は、このページテンプレートから生成されるすべての電子メールページで共有される電子メールヘッダーやフッターを設定します。 | AEM |
| 3 | 作成者は、 [ページエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html) テキストエディターを使用して e メールコンテンツを作成し、Adobe Campaignの変数を選択してセグメント化コンポーネントを使用し、受信者が特定の条件を満たす場合に条件付きで情報を表示できます。 | AEM |
| 4 | E メールのコンテンツが完了したら、 [ワークフローが実行される](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html) ：コンテンツを承認し、Campaign に送信します。 | AEM |
| 5 | 受信者のリストを定義して配信を作成します。 | Campaign |
| 6 | AEMで作成されたコンテンツが配信のコンテンツとして選択されます。 | Campaign |
| 7 | コンテンツは受信者に送信され、Adobe Campaign変数は受信者のパーソナライズされた情報に置き換えられます。 | Campaign |

AEMでの E メールコンテンツの作成とAdobe Campaignでの配信の例については、次のリソースを参照してください。

* AEM 6.5: [Adobe Campaign ClassicとAdobe Campaign Standardの使用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)
