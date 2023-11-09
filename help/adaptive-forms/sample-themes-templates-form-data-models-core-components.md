---
title: AEM Formsコアコンポーネントのサンプルのテーマとテンプレートを入手するには？
description: AEM Formsコアコンポーネントには、サンプルのアダプティブフォームテーマ、テンプレート、フォームデータモデルが用意されています。
solution: Experience Manager Forms
topic: Administration
role: Admin, User
level: Intermediate
exl-id: aef6e88b-dcae-4777-9893-9257d7702f43
source-git-commit: 1dd55fdd836dff89763887d88af2671ed1f9ce2b
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 69%

---

# サンプルのテーマ、テンプレートおよびフォームデータモデル {#sample-themes-templates-and-data-models}

[!DNL AEM Forms] コアコンポーネントには、すぐに使用できるサンプルのテーマ、テンプレートおよびフォームデータモデルが用意されているので、用途の広いアダプティブフォームをすばやく作成することができます。これらは、フォーム作成者が、 [アダプティブFormsコアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=ja) データベースとの接続をシームレスに行いながら、簡単なフォームを短時間で、複雑なフォームを簡単に作成する。

参照コンテンツパッケージに含まれているサンプルのテーマ、テンプレートおよびフォームデータモデルは次のとおりです。

| テンプレート | テーマ | フォームデータモデル |
---------|----------|---------
| [空白](#Blank) | [キャンバス](#Canvas) | Microsoft® Dynamics 365 |
| [お問い合わせ](#Contact-Us) | [WKND](#WKND) | Salesforce |
| [連絡先詳細の更新](#Contact-Details-Update) | [イーゼル](#Easel) |   |
| [同意フォーム](#Consent-Form) | [FSI](#FSI) |  |
| [ログサービスリクエスト](#Log-Service-Request) | [ヘルスケア](#Healthcare) |  |
| [フィードバックの送信](#Give-Feedback) |  |  |
| [福利厚生の登録](#Benefits-Enrollment) |  |   |
| [従業員福利厚生の概要](#Employee-Benefits-Summary) |   |   |
| [取引明細書の請求](#Request-for-Account-Statement) |   |   |
| [安全点検フォーム](#Safety-Inspection) |   |   |
| [品質管理検査](#Quality-Control-Inspection) |   |   |
| [購入リクエスト](#Purchase-Request) |  |  |

## サンプルテーマ {#Sample-Themes}

リファレンスサンプルテーマは、フォームのスタイル設定の使用、定義、カスタマイズに役立ちます。CSS の基本知識を持つ作成者は、必要に応じてテーマをカスタマイズできます。

**これらのテーマの取得方法**
これらのテーマは、次の手順でに対して取得します。 **AEMas a Cloud Service** 環境：

1. [アダプティブフォームのコアコンポーネントの有効化](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=ja)
1. [環境へのAEM Archetype 45 プロジェクトのデプロイ](https://github.com/adobe/aem-project-archetype)


AEMアーキタイプをデプロイする場合、フォームで使用できるのは OOTB テーマのみです。必要に応じてテーマをカスタマイズするには、 [フロントエンドパイプラインの使用](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=ja) をクリックしてテーマをデプロイします。

>[!NOTE]
>
> * テーマは使用できません **AEM 6.5** 環境。

<!--

1. **AEM 6.5**

    1. [Enable Adaptive Form Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html)
    1. [Deploy an AEM Archetype 45 project to your environment](https://github.com/adobe/aem-project-archetype)


    When you deploy an AEM Archetype, you can only use the OOTB themes in your forms, To customize the themes as per your requirements, [Use the front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html) to deploy the themes.

-->


<!--

### Deploying an AEM Archetype 45 project to your environment {#using-archetype-to-deploy-themes}

You can get these themes by deploying an [AEM Archetype 45](https://github.com/adobe/aem-project-archetype) to your **AEM Forms as a Cloud Service** or **AEM 6.5** Forms environment.

### Enable core components and use front-end pipeline to deploy themes {#use-front-end-pipeline-to-deploy-themes}

1. To get these themes on **Forms as a Cloud Service** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html) and use the [front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html) to deploy these themes.
    
1. To get these themes on **AEM 6.5 Forms** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html) and use the [Package Manager](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html) to deploy these themes.

[Learn to use and customize themes in AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html). 

[Learn to use and customize themes in AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html).

-->

[アダプティブフォームコアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=ja)の&#x200B;**標準提供の**&#x200B;テーマは次のとおりです。

![OOTB テーマ](/help/adaptive-forms/assets/archetype-45-themes-1.png)

### キャンバス {#Canvas}

キャンバステーマはフォームのデフォルトのテーマで、基本色、透明度、フラットなアイコンの使用に重点を置いています。 以下のスクリーンショットでは、キャンバステーマの外観を確認できます。

![キャンバステーマ](/help/adaptive-forms/assets/Safety-Inspection-Theme-Canvas.png)

### WKND {#WKND}

WKND テーマは、生き生きとした想像力に富む魅力的なデザインを具現化して、スタイリッシュなアピアランスをフォームに表示します。このテーマは、[Adobe Experience Manager コアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=ja)で構築されたトラベル＆アドベンチャー web サイトである [WKND サイト](https://wknd.site/us/en.html)のアピアランスとスタイル設定に基づいています。

![WKND テーマ](/help/adaptive-forms/assets/Safety-Inspection-Form-Theme.png)


### イーゼル {#Easel}

イーゼルテーマは、魅力的でセットアップしやすいフォームアピアランスを作成するのに役立ち、シンプルで使いやすいようにカスタマイズされています。イーゼルのテーマは、絵画を描きながらキャンバスを支えるために携帯用のスタンドを使うコンセプトに基づいています。

![イーゼルテーマ](/help/adaptive-forms/assets/Safety-Inspection-Theme-Easel.png)

### FSI（金融サービス&amp;保険） {#FSI}

FSI のテーマは、フォームに清潔で実用的な外観を与えることに重点を置いています。 FSI テーマを適用すると、画像に表示されるように、青のマイルドな色合いがフォームに適用されます。

![FSI テーマ](/help/adaptive-forms/assets/fsi-theme-new1.png)


### ヘルスケア {#Healthcare}

ヘルスケアテーマでは、豊富で緑豊かなトーンを使用して、フォーム内のタブ、パネル、テキストボックス、ボタンなどの要素を強調します。

![ヘルスケアのテーマ](/help/adaptive-forms/assets/healthcare-new-theme.png)


## サンプルテンプレート {#Sample-templates}

テンプレートは、初期のフォーム構造、コンテンツおよびアクションを定義したもので、対象フォームで複製したり、同様のテンプレート構造を対象フォームに使用したりします。例えば、同意フォーム、福利厚生登録フォームなどがあります。

**これらのテンプレートの取得方法。**
これらのテンプレートは、 [AEM Archetype 45](https://github.com/adobe/aem-project-archetype) を **AEM Formsas a Cloud Service** 環境または **AEM 6.5 Forms** 環境。

<!--

>[!NOTE]
>
> * If you have [enabled core components and used front-end pipeline to deploy themes](#use-front-end-pipeline-to-deploy-themes), you need not to deploy an AEM Archetype.
> * You can find list of all OOTB templates when you create a form.

-->


[アダプティブフォームコアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=ja)の&#x200B;**標準提供の**&#x200B;テンプレートは次のとおりです。

![参照テンプレート](/help/adaptive-forms/assets/reference-templates-core-components.png)

<!--

### Basic {#Basic}

A basic template helps you quickly create an enrollment experience form. You can also use it to preview the functionality of [Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html). It provides a wizard layout for section-by-section presentation of data.

![Basic Template](/help/adaptive-forms/assets/Basic-template-desktop-view.png)

-->

### 空白 {#Blank}

空白キャンバステンプレートを使用すると、アダプティブフォームの構造、コンテンツおよびルールをゼロから作成できます。空白テンプレートには、フォームコンポーネントがあらかじめ組み込まれていません。

![空白テンプレート](/help/adaptive-forms/assets/Blank-temp-desktop-view.png)

### お問い合わせ {#Contact-Us}

お問い合わせフォームテンプレートを使用すると、Web サイト訪問者とフォーム管理者の間のコミュニケーションを円滑に進めるためのフォームを作成できます。ユーザーは、このフォームを通じて、問い合わせ、フィードバックまたはサポートリクエストを送信できます。

![お問い合わせテンプレート](/help/adaptive-forms/assets/Contact-us-desktop-view.png)

### 連絡先詳細の更新 {#Contact-Details-Update}

「連絡先詳細の更新」テンプレートは、作成者が顧客の住所と連絡先詳細の更新用のフォームを作成する際に役に立ちます。このフォームは、シームレスなコミュニケーションを確保し、サービスや福利厚生に中断なしにアクセスできるようにするために、顧客がサブスクリプションや福利厚生に関連する個人情報を更新する際にも役に立ちます。

![連絡先詳細の更新](/help/adaptive-forms/assets/Contact-details-update.png)

### 同意フォーム {#Consent-Form}

同意フォームテンプレートを使用して、特定の活動に参加する参加者、調査研究、医療処置、または個人情報や権利が関与する状況から法的文書を調達するためのフォームを作成します。 このフォームは、透明性の確保、参加者の権利の保護、個人の同意内容の明確な理解に役立ちます。

![同意フォーム](/help/adaptive-forms/assets/Consent-form-desktop-view.png)

### ログサービスリクエスト {#Log-Service-Request}

ログサービスリクエストテンプレートは、サービスプロバイダーにログ固有のログサービスを要求するフォームを作成する際に役立ちます。このフォームは、ステータスの監視や追跡をおこなうための、イベント、アクティビティまたはデータログのチケットを作成する正式なリクエストとして機能します。

![ログサービスリクエストテンプレート](/help/adaptive-forms/assets/Log-service-request-desktop-view.png)


### フィードバック送信 {#Give-Feedback}

フィードバック送信フォームのテンプレートは、別のユーザーやチームに建設的なフィードバックを提供するためのフォームを作成する際に役立ちます。フォームは、フィードバックが明確で具体的で実用的なものであることを確認し、オープンなコミュニケーションと改善を促進するのに役立ちます。

![フィードバック送信テンプレート](/help/adaptive-forms/assets/Give-feedback-desktop-view.png)


### 福利厚生加入 {#Benefits-Enrollment}

福利厚生加入フォームのテンプレートを使用すると、希望する福利厚生や補償範囲のオプションに関する必須の情報を従業員から収集するためのフォームを作成できます。通常は、年間の福利厚生加入期間に付随します。

![福利厚生加入テンプレート](/help/adaptive-forms/assets/Benefits-enrollment-form-template.png)


### 従業員福利厚生概要 {#Employee-Benefits-Summary}

従業員福利厚生概要フォームのテンプレートを使用すると、個人の福利厚生に関する必須の詳細情報を収集するためのフォームを作成できます。このフォームは、効率的な支援とサポートのための包括的な概要を提供して、補償内容の迅速かつ正確な評価に役立ちます。
![従業員福利厚生概要](/help/adaptive-forms/assets/Employee-benefits-summary.png)


### 取引明細書の請求 {#Request-for-Account-Statement}

取引明細書のリクエストテンプレートを使用すると、正確で最新の顧客明細書を取得するプロセスを開始するフォームを作成できます。 明細書は、このフォームを使用する顧客に関する金融取引、活動またはその他の関連情報の詳細な記録を提供します。

![取引明細書の請求](/help/adaptive-forms/assets/Request-for-account-statment.png)

### 安全点検 {#Safety-Inspection}

安全点検フォームのテンプレートは、安全な作業環境の詳細を入力するフォームの作成に役立ちます。このフォームを使用して定期検査を実施することで、潜在的な危険性を特定することができます。このフォームは、非常口、火災安全、電気安全、危険物、個人用保護具、ワークステーションの人間工学など、従業員、訪問者および顧客の安全と福祉に関する様々な側面をカバーしています。

![安全点検フォーム](/help/adaptive-forms/assets/Safety-inspection-form.png)

### 品質管理検査 {#Quality-Control-Inspection}

品質管理検査フォームのテンプレートを使用すると、製品やアイテムの外観、寸法、機能、ドキュメント、テスト結果および全体的な品質を評価および文書化するためのフォームを作成できます。欠陥、不適合および品質基準の確実な遵守に必要な是正措置を特定するのに役立ちます。

![品質管理検査](/help/adaptive-forms/assets/Quality-Control-Inspection.png)


### 購入リクエスト {#Purchase-Request}

購入リクエストフォームのテンプレートは、調達プロセスを開始し、作業に必要な商品やサービスの購入を従業員が正式にリクエストできるフォームの作成に役立ちます。このフォームでは、アイテムの説明、数量、希望するサプライヤー（該当する場合）、予算配分、購入理由、配送情報、必要な承認など、必須の詳細情報が取得されます。

![購入リクエストフォーム](/help/adaptive-forms/assets/Purchase-request-form.png)

## 参照フォームデータモデル {#reference-models}

[コアコンポーネント](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=ja)に基づいてアダプティブフォームを作成したら、フォームをデータベースの Microsoft® Dynamics 365 サーバーや Salesforce サーバーに接続して、ビジネスワークフローを有効にすることができます。例：

* アダプティブフォームの送信時に、データを Microsoft® Dynamics 365 や Salesforce に書き込みます。
* フォームデータモデル内で定義されているカスタムエンティティを使用して、データを Microsoft® Dynamics 365 や Salesforce に書き込みます（またはその逆の動作を行います）。
* Microsoft® Dynamics 365 サーバーや Salesforce サーバーに対してデータのクエリを行い、アダプティブフォームに事前に入力します。
* Microsoft® Dynamics 365 サーバーや Salesforce サーバーからデータを読み取ります。

[参照コンテンツパッケージ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-forms-reference-content.ui.content-2.1.0.zip)をインストールすると、次のフォームデータモデルを取得できます。

* Microsoft® Dynamics 365
* Salesforce

これらのモデルの使用については、[Microsoft® Dynamics 365 および Salesforce クラウドサービスの設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/configure-msdynamics-salesforce.html?lang=ja#configure-dynamics-cloud-service)を参照してください。
