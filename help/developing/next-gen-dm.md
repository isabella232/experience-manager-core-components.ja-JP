---
title: 次世代のDynamic Mediaサポート
description: リモートの次世代Dynamic Media Assets をサポートするようにコアコンポーネントの画像およびティーザーコンポーネントを設定する方法について説明します。
role: Architect, Developer, Admin, User
source-git-commit: 57307b75bd33fd538a1eb704cc37822847c896de
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 5%

---


# 次世代のDynamic Mediaサポート {#next-gen-dm-support}

リモートの次世代Dynamic Media Assets をサポートするようにコアコンポーネントの画像およびティーザーコンポーネントを設定する方法について説明します。

## 最新バージョンのAEMを取得 {#latest}

次世代Dynamic Mediaリモートアセットのサポートには、次の要件が必要です。

* AEM 6.5 SP 18 以降またはAEM as a Cloud Service
* コアコンポーネントリリース2.23.2以降

## HTTPS を設定 {#https}

通常は、すべての実稼動AEMインスタンスを HTTP を使用して実行することをお勧めします。 ただし、ローカル開発環境がそのように設定されていない場合があります。 ただし、次世代Dynamic Mediaのリモートアセットを機能させるには HTTPS が必要です。

[このガイドを使用](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html) ：開発環境を含め、リモートアセットを使用する任意の場所に HTTPS を設定します。

## OSGi の設定 {#osgi}

リモートアセットの場所は、OSGi 設定で定義する必要があります。 を設定します。 **次世代のDynamic Media設定** OSGi の設定を次のように指定します。値をリモートアセット環境の値に置き換えます。

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![次世代のDynamic Media Config OSGi 設定ウィンドウ](/help/assets/remote-assets-osgi.png)

OSGi の設定方法の詳細については、次のドキュメントを参照してください。

* [Adobe Experience Manager as a Cloud Service用の OSGi の設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html?lang=ja) AEMas a Cloud Service
* [OSGi の設定](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html?lang=ja) (AEM 6.5 用 )

## 設定を検証 {#verify}

次世代のDynamic Mediaリモートアセット機能が動作していることを確認できます。 これをおこなうには、 WKND サンプルサイトとコアコンポーネントをインストールします。

* [コアコンポーネント](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip) リリース2.23.2以降が必要です。
* [WKND サンプルサイト](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip) リリース 3.2.0 以降が必要です。

コアコンポーネントと WKND サイトがインストールされたら、任意の WKND ページでこの機能をテストできます。

1. HTTPS を使用してAEMインスタンスにアクセスします。

1. ページエディターで WKND デモページ（例： ）を開きます。 `https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. ページに画像コンポーネントを追加します。

1. コンポーネントの設定ダイアログで、「 」オプションのチェックをオフにします。 **ページからアイキャッチ画像を継承** の **アセット** タブをクリックし、 **選択**.

1. 設定が正しい場合は、オプションを含むドロップダウンが表示されます **ローカル** および **リモート**. 選択 **リモート**.

   ![画像選択のリモートとローカルの選択オプション](/help/assets/remote-asset-selection.png)

1. ダイアログが開き、リモートサービスに対する認証が必要になります。

1. 認証が完了すると、リモートサービスのアセットブラウザーが開きます。 目的のアセットを選択し、をタップまたはクリックします。 **選択**.

   ![リモートアセットの選択](/help/assets/remote-asset-selection.png)

リモートアセットがローカルのAEMページに追加され、機能が正しく設定されていることを確認しました。

## リモートアセットの使用 {#using}

設定が完了したら、コアコンポーネント ( [画像コンポーネント](/help/components/image.md) そして [ティーザーコンポーネント。](/help/components/teaser.md)
