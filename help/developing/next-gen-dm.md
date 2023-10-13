---
title: 次世代の Dynamic Media サポート
description: リモートの次世代の Dynamic Media アセットをサポートするコアコンポーネントの画像コンポーネントおよびティーザーコンポーネントを設定する方法について説明します。
role: Architect, Developer, Admin, User
exl-id: b462c1f3-a6c8-4a2a-abf4-d08ec82d4371
source-git-commit: 79cedf7099e2dc267a4cb1c25c06d4f0460367b2
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 100%

---

# 次世代の Dynamic Media サポート {#next-gen-dm-support}

リモートの次世代の Dynamic Media アセットをサポートするコアコンポーネントの画像コンポーネントおよびティーザーコンポーネントを設定する方法について説明します。

## 最新バージョンの AEM の取得 {#latest}

次世代の Dynamic Media リモートアセットのサポートには、以下が必要です。

* AEM 6.5 SP 18 以降または AEM as a Cloud Service
* コアコンポーネントリリース 2.23.2 以降

## HTTPS を設定 {#https}

通常は、HTTP を使用して、すべての実稼動 AEM インスタンスを実行することをお勧めします。ただし、ローカル開発環境がこのように設定されていない場合があります。しかし、次世代の Dynamic Media リモートアセットを機能させるには HTTPS が必要です。

[このガイドを使用](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html?lang=ja)して、開発環境を含むリモートアセットを使用する場所で HTTPS を設定します。

## OSGi の設定 {#osgi}

リモートアセットの場所は、OSGi の設定で定義する必要があります。**次世代の Dynamic Media 設定** OSGi の設定を次のように行って、値をリモートアセット環境の値に置き換えます。

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![次世代の Dynamic Media 設定 OSGi の設定ウィンドウ](/help/assets/remote-assets-osgi.png)

OSGi の設定方法について詳しくは、次のドキュメントを参照してください。

* AEM as a Cloud Service 用の [Adobe Experience Manager as a Cloud Service の OSGi の設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html?lang=ja)
* AEM 6.5 用の [OSGi の設定](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html?lang=ja)

## 設定の確認 {#verify}

次世代の Dynamic Media リモートアセット機能が動作していることを確認できます。これを行うには、WKND サンプルサイトとコアコンポーネントをインストールします。

* [コアコンポーネント](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip)リリース 2.23.2 以降が必要です。
* [WKND サンプルサイト](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip)リリース 3.2.0 以降が必要です。

コアコンポーネントと WKND サイトをインストールすると、任意の WKND ページで機能をテストできます。

1. HTTPS を使用して、AEM インスタンスにアクセスします。

1. ページエディターで、`https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html` などの WKND デモページを開きます。

1. ページに画像コンポーネントを追加します。

1. コンポーネントの設定ダイアログで、「**アセット**」タブの「**ページからアイキャッチ画像を継承**」オプションのチェックをオフにし、「**選択**」をクリックします。

1. 設定が正しい場合は、「**ローカル**」オプションと「**リモート**」オプションを含むドロップダウンが表示されます。「**リモート**」を選択します。

   ![画像選択用のリモートとローカルの選択オプション](/help/assets/remote-asset-selection.png)

1. ダイアログが開き、リモートサービスに対する認証を行う必要があります。

1. 認証が完了すると、リモートサービスのアセットブラウザーが開きます。目的のアセットを選択し、「**選択**」をタップまたはクリックします。

   ![リモートアセットの選択](/help/assets/remote-asset-picker.png)

リモートアセットがローカルの AEM ページに追加され、機能が正しく設定されていることを確認できます。

## リモートアセットの使用 {#using}

設定が完了すると、[画像コンポーネント](/help/components/image.md)や[ティーザーコンポーネント](/help/components/teaser.md)などのコアコンポーネントを使用してアセットを選択する際に、リモートアセットを選択できるようになります。
