---
title: Adobe Client Data Layerを使用したコアコンポーネントとAdobe Launchの統合
description: Adobe Launchを設定してAdobe Launchを使用してコアコンポーネントイベントを登録する方法
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 2%

---


# Adobe Client Data Layerを使用したコアコンポーネントとAdobe Launchの統合 {#launch-integration}

コアコンポーネントは、Adobe Clientデータレイヤーを使用して、Adobe Launchと統合できます。 このドキュメントでは、例として画像コンポーネントのクリックイベントを追跡するためのAdobe Launchの設定方法について説明します。

設定した場合、コアイメージコンポーネントがクリックされると、Launchはブラウザーコンソールで次の出力を生成します。

![コンソール出力の例](/help/assets/launch-console-output.png)

## AEMとの統合の開始 {#launch-aem}

最初のAdobe Launchは、AEMサイトと統合されている必要があります。

### 手順1 - Adobe I/Oでの統合の作成 {#create-io-integration}

最初にAdobe I/Oにサインインして、統合の設定を開始に依頼します。

1. `https://console.adobe.io` にアクセスします。
1. Adobe IDを使用してサインインします。
1. [クイック開始]セクションで[統合の **作成**]をクリックします。
1. Select **Access an API** and click **Continue**.
1. 「Adobe Experience Platform」の **下の「** Experience Platform Launch API **」を選択し、「**&#x200B;続行」をクリックします。

### 手順2 - AEMでIMS設定を作成する {#ims-configuration}

AEMでは、Adobe I/Oで設定を開始した統合を定義する必要があります。

1. AEMホームページに移動し、 **ツール/セキュリティ/Adobe IMS設定をクリックします**。
1. 「**作成**」をクリックします。
1. 「 **Cloud Solution**」として「 **Adobe Launch**」を選択します。
1. 「 **新しい証明書を作成**」を選択します。
1. 証明書のエイリアス( **aem-launch-certificate**&#x200B;など)を入力します。
1. 「証明書 **を作成** 」をクリックし、ポップアップで「 **OK** 」をクリックして証明書を作成します。
1. 「公開鍵を **ダウンロード** 」をクリックし、ポップアップで「 **ダウンロード**」をクリックします。

### 手順3 - Adobe I/O設定の終了 {#finish-io}

AEM IMS設定で作成した証明書とキーを使用して、Adobe I/O設定を完了できます。

1. 手 [順1に従って、Adobe I/Oコンソールに戻ります。](#create-io-integration)
1. 「 **新しい統合を** 作成 **」ウィンドウで、名前と説明(** AEM Launchデータレイヤーなど)を入力します。
1. 「 **公開鍵証明書**」で、 [手順2で作成した証明書をアップロードします。](#ims-configuration)
1. 「 **起動 — 実行」プロファイルを選択します**。
1. 「**統合を作成**」をクリックします。
1. 「統合の詳細 **に進む」をクリックします**。 これらの詳細は、後でAEMインスタンスのIMS設定を完了する必要があります。

### 手順4 - IMS設定を終了する {#finish-ims}

Adobe I/O統合の詳細を確認した上で、AEM IMSの設定を完了できます。

1. 「AEM」タブで、 **手順2の「** Adobe IMSテクニカルアカウント設定 [」タブで、](#ims-configuration) 「 **次へ**」をクリックします。
1. Adobe Launchの **IMS設定などのタイトルを入力します**。
1. 「Adobe I/O」タブで、 **APIキー（クライアントID）をコピーし**&#x200B;ます。
1. 「AEM」タブで、前にコピーしたキーを「 **APIキー」フィールドに貼り付けます**。
1. Adobe I/Oで、「 **Retrieve Client Secret** 」をクリックしてコピーします。
1. 「AEM」タブで、「 **Client Secret** 」フィールドに貼り付けます。
1. 「Adobe I/O」タブで、「 **JWT** 」タブを選択し、次のようなURLをコピーし `https://ims-na1.adobelogin.com`ます。
1. 「AEM」タブで、「 **認証サーバー** 」フィールドにURLを貼り付けます。
1. 「Adobe I/O」タブで、JWTペイロード（ブレースの間のコード）をコピーします。
1. 「AEM」タブで、「 **Payload** 」フィールドに貼り付けます。
1. 「 **作成** 」をクリックして、AEMでIMS設定を作成します。

### 手順5a - Adobe Launchでプロパティを作成する {#create-property}

プロパティは、Launchがサイトに挿入できる機能を定義します。

1. Adobe Launch（次の場所）に移動 `https://launch.adobe.com`します。
1. Adobe IDを使用してサインインします。
1. 「 **新しいプロパティ**」をクリックします。
1. 「 **Launch AEM Data Layer**」などの名前を入力します。
1. ドメインを入力します。
1. 「**保存**」をクリックします。

### 手順5b — 起動時にルールを作成する {#launch-rule}

作成したプロパティを使用して、アクションの発生時の動作を指定するルールを定義できます。

1. 手 [順5](#create-property) 「AEMデータレイヤーを **起動」から、新しく追加したプロパティをクリックします**。
1. 「 **ルール** 」タブを選択し、「新しいルールの **作成**」をクリックします。
1. 名前( **image-clickなど**)を入力します。
1. **イベントの下の「+」** ボタンをクリックします ****。
1. 「 **Core** as **Extension**」を選択し、「Extension **** 」をクリックします。次に、「 **イベントタイプ」をクリックします。**********「enter」をクリックし、「」をクリックします。
1. 「 **変更を保持**」をクリックします。
1. 「 **アクション」の下の「** +」 **ボタンをクリックします**。
1. 「 **Core** as **Extension**」、「Custom Code **as** Extension **」、「Action type」、「Action type」、「Open Editor」の順に選択します******。
1. エディターで、次のコードを入力します。 `console.log("DOM click event tracked by Launch for image: ", event.target.src);`
1. 「**保存**」をクリックします。
1. 「 **変更を保持**」をクリックします。
1. 「 **保存** 」をクリックして、新しいルールを作成します。

### 手順6 — 起動ルールを公開する {#publish-rule}

新しいルールをAEMサイトで使用できるようにするには、そのルールを発行する必要があります。

1. 「 **Adobe Launch** 」タブで、「 **Publishing** 」タブを選択します。
1. 「 **追加新規ライブラリ**」をクリックします。
1. 必要に応じて、 **demo-1のように** 名前 **を入力します**。
1. 「 **環境** 」では、必要に応じて **「**&#x200B;開発（開発）」を選択します。
1. 「リソ **追加ース**」をクリックします。
1. 「 **ルール」>「画像」>「最新」を選択し、** 「 **選択して新しいリビジョンを作成」をクリックします**。
1. 「**保存して開発用にビルド**」をクリックします。
1. ポップアップで、「更新を **適用して続行**」をクリックします。
1. ライブラリが構築されたら、省略記号アイコンをクリックし、「 **Submit for Approval**」を選択します。
1. ポップアップで「 **送信**」をクリックします。
1. 省略記号アイコンをクリックし、「 **Build for Staging**」を選択します。
1. ビルドが完了したら、省略記号アイコンをクリックし、「 **Approve for Publishing**」を選択します。
1. ポップアップで[ **承認**]をクリックします。
1. 省略記号アイコンをクリックし、「 **Build &amp; Publish to Production**」を選択します。
1. ポップアップで「 **公開**」をクリックします。

### 手順7 — サイトのクラウド設定を有効にする {#enable-configurations}

統合を使用するには、AEMでクラウド設定として割り当てる必要があります。

1. AEMコンソールで、 **ツール/一般/設定ブラウザーをクリックします**。
1. 「 **コアコンポーネントの例** 」を確認し、「 **プロパティ**」をクリックします。
1. 「 **Cloud Configurations** 」を確認し、「 **保存して閉じる**」をクリックします。

### 手順8 - AEMでサイトとの開始の統合を作成する {#create-launch-integration}

AEMがLaunchを操作するには、Launch統合が必要です

1. AEMコンソールで、 **ツール/クラウドサービス/Adobe Launch Configurations**（アドビ起動設定）をクリックします。
1. 「 **コアコンポーネントの例** 」を選択し、「 **作成**」をクリックします。
1. 「 **起動設定** 」などの **タイトルを入力します**。
1. 手順4で作成したIMS設定を選択し [ます。](#finish-ims)
1. 必要に応じて、 **会社** (A)を選択します。
1. 「 **プロパティ** 」として、 [手順5で作成した新しく追加した「起動」プロパティを選択します。](#create-property)
1. 「作成者に実稼動コードを **含める** 」スライダーを右に移動し、「 **次へ**」をクリックします。
1. 「**次へ**」をクリックします。
1. 「**次へ**」をクリックします。
1. 「**作成**」をクリックします。

### 手順9 - AEMサイトを起動の統合に接続する {#connect-aem}

AEMがLaunch統合を使用するには、クラウド設定として割り当てる必要があります。

1. AEMコンソールで、「 **サイト** 」をクリックし、 **コア**&#x200B;コンポーネントサイトを確認します。
1. 「**プロパティ**」をクリックします。
1. Select the **Advanced** tab.
1. 「 **Cloud Configuration**」として、 **コアコンポーネントの例を選択し、「** Select ****」をクリックします。
1. 「**保存して閉じる**」をクリックします。

### 手順10 — 起動ロジックがページに適用されていることを確認する {#verify-launch}

これまでの手順が成功したことをテストします。

1. コアコンポーネントライブラリのプレビューページを画像モードで開きます。 `http://<lhost&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 画像をクリックし、メッセージがブラウザーコンソールに表示さ `A Core Image was clicked` れることを確認します。

## AEMとデータレイヤーの統合の開始 {#data-layer-launch}

AEMとLaunchの統合が設定されたので、データレイヤーと統合できます。

### 手順1 - Adobe Launchでルールを作成する {#create-rule}

手順5の手順を繰り返し [て](#launch-rule) 、次の値を使用してAdobe Launchに新しいルールを追加します。

* 名前: `image-click-data-layer`
* イベント:
   * 拡張子： コア
   * イベントタイプ: DOM Ready
* アクション:
   * 拡張子： コア
   * アクションタイプ： カスタムコード
   * コード:

      ```
        function onImageClick(event) {
          console.log("Data layer click event tracked by Launch for image: " + event.info.path);
          console.log("dataLayer.getState(): ", adobeDataLayer.getState()); 
        }
        adobeDataLayer.addEventListener('image clicked', onImageClick);
      ```

### 手順2 — 起動ルールを発行してAEMサイトで使用できるようにする {#publish-rule-2}

手 [順6の手順を繰り返して、新しいルールを発行します](#publish-rule) 。

### 手順3 — 起動ロジックがページに適用されていることを確認する {#verify}

1. コアコンポーネントライブラリのプレビューページを画像モードで開きます。 `http://<host&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 画像をクリックし、ブラウザーコンソールに次のメッセージが表示されることを確認します。

   ![データレイヤーコンソールの出力](/help/assets/data-layer-console-output.png)
