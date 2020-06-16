---
title: Adobe Client Data Layer を使用してコアコンポーネントと Adobe Launch を統合する
description: Adobe Launch を使用してコアコンポーネントイベントを登録するよう設定する方法
translation-type: ht
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: ht
source-wordcount: '1160'
ht-degree: 100%

---


# Adobe Client Data Layer を使用してコアコンポーネントと Adobe Launch を統合する{#launch-integration}

Adobe Client Data Layer を使用することで、コアコンポーネントを Adobe Launch と統合できます。このドキュメントでは、例として、画像コンポーネントのクリックイベントを追跡するよう Adobe Launch を設定する方法について説明します。

この設定をおこなった場合、コア画像コンポーネントがクリックされると、Launch はブラウザーコンソールで次の出力を生成します。

![コンソール出力の例](/help/assets/launch-console-output.png)

## Launch と AEMの統合 {#launch-aem}

最初に、Adobe Launch を AEM サイトと統合する必要があります。

### 手順 1 - Adobe I/O で統合を作成する {#create-io-integration}

最初に Adobe I/O にログインして、統合の設定を開始します。

1. `https://console.adobe.io` にアクセスします。
1. Adobe ID を使用してログインします。
1. 「クイックスタート」セクションで「**統合を作成**」をクリックします。
1. 「**API にアクセス**」を選択し、「**続行**」をクリックします。
1. Adobe Experience Platform の下にある「**Experience Platform Launch API**」を選択し、「**続行**」をクリックします。

### 手順 2 - AEM で IMS 設定を作成する {#ims-configuration}

AEM では、Adobe I/O で設定を開始した統合を定義する必要があります。

1. AEM ホームページに移動し、**ツール／セキュリティ／Adobe IMS 設定**&#x200B;をクリックします。
1. 「**作成**」をクリックします。
1. 「**クラウドソリューション**」として **Adobe Launch** を選択します。
1. 「**新しい証明書を作成**」を選択します。
1. 証明書のエイリアス（例：**aem-launch-certificate**）を入力します。
1. 「**証明書を作成**」をクリックし、ポップアップで「**OK**」をクリックして証明書を作成します。
1. 「**公開鍵をダウンロード**」をクリックし、ポップアップで「**ダウンロード**」をクリックします。

### 手順 3 - Adobe I/O 設定を終了する {#finish-io}

AEM IMS 設定で作成した証明書とキーを使用して、Adobe I/O 設定を完了できます。

1. [手順 1](#create-io-integration) に従って、Adobe I/O コンソールに戻ります。
1. 「**Create a new integration**」ウィンドウで、名前と説明（**AEM Launch データレイヤー**&#x200B;など）を入力します。
1. 「**Public keys certificates**」から、[手順 2](#ims-configuration) で作成した証明書をアップロードします。
1. 「**Launch - Prod profile**」を選択します。
1. 「**Create integration**」をクリックします。
1. 「**Continue to integration details**」をクリックします。これらの詳細は、後で AEM インスタンスのIMS設定を完了する際に必要となります。

### 手順 4 - IMS 設定を終了する {#finish-ims}

Adobe I/O 統合の詳細を確認しすると、AEM IMS の設定を完了できます。

1. 「AEM」タブから、[手順 2](#ims-configuration) の「**Adobe IMS テクニカルアカウント設定**」タブで「**次へ**」をクリックします。
1. 「**Adobe Launch の IMS 設定**」のようなタイトルを入力します。
1. 「Adobe I/O」タブで、**API キー（クライアント ID）**&#x200B;をコピーします。
1. 「AEM」タブで、前にコピーしたキーを「**API キー**」フィールドに貼り付けます。
1. Adobe I/O で、「**Retrieve Client Secret**」をクリックしてコピーします。
1. 「AEM」タブで、「**クライアントシークレット**」フィールドに貼り付けます。
1. 「Adobe I/O」タブで「**JWT**」タブを選択し、URL（例：`https://ims-na1.adobelogin.com`）をコピーします。
1. 「AEM」タブで、「**認証サーバー**」フィールドに URL を貼り付けます。
1. 「Adobe I/O」タブで、JWT ペイロード（括弧内のコード）をコピーします。
1. コピーしたペイロードを「AEM」タブの「**ペイロード**」フィールドに貼り付けます。
1. 「**作成**」をクリックして、AEM で IMS 設定を作成します。

### 手順 5a - Adobe Launch でプロパティを作成する {#create-property}

プロパティは、Launch がサイトに挿入できる機能を定義します。

1. `https://launch.adobe.com` で Adobe Launch に移動します。
1. Adobe ID を使用してログインします。
1. 「**新しいプロパティ**」をクリックします。
1. 名前（**Launch AEM データレイヤー**&#x200B;など）を入力します。
1. ドメインを入力します。
1. 「**保存**」をクリックします。

### 手順 5b - Launch でルールを作成する {#launch-rule}

作成したプロパティを使用して、アクションの発生時の動作を指定するルールを定義できます。

1. [手順 5](#create-property)**Launch AEM データレイヤー**&#x200B;で新しく追加したプロパティをクリックします。
1. 「**ルール**」タブを選択し、「**新規ルールを作成**」をクリックします。
1. 名前（例：**image-click**）を入力します。
1. 「**イベント**」の下の「**+**」 ボタンをクリックします 。
1. 「**拡張機能**」として「**コア**」、「**イベントタイプ**」として「**クリック**」を選択し、**CSS セレクター**&#x200B;に「**cmp-image**」と入力します。
1. 「**変更を保持**」をクリックします。
1. 「**アクション**」の下の「**+**」 ボタンをクリックします。
1. 「**拡張機能**」で「**コア**」、「**アクションタイプ**」で「**カスタムコード**」を選択し、「**エディターを開く**」をクリックします。
1. エディターで、次のコードを入力します。`console.log("DOM click event tracked by Launch for image: ", event.target.src);`
1. 「**保存**」をクリックします。
1. 「**変更を保持**」をクリックします。
1. 「**保存**」をクリックして、新しいルールを作成します。

### 手順 6 - Launch ルールを公開する {#publish-rule}

新しいルールを AEM サイトで使用できるようにするには、そのルールを公開する必要があります。

1. 「**Adobe Launch**」タブで、「**公開**」タブを選択します。
1. 「**Add New Library**」をクリックします。
1. 必要に応じて&#x200B;**名前**&#x200B;に「**demo-1**」などと入力します。
1. 「**環境**」では、必要に応じて 「**Development (development)**」など選択します。
1. 「**Add a Resource**」をクリックします。
1. **ルール／画像をクリック／最新**&#x200B;を選択し、「**Select &amp; Create a New Revision**」をクリックします。
1. 「**Save &amp; Build for Development**」をクリックします。
1. ポップアップで、「**Apply Updates and Continue**」をクリックします。
1. ライブラリが構築されたら、省略記号アイコンをクリックし、「**Submit for Approval**」を選択します。
1. ポップアップで「**送信**」をクリックします。
1. 省略記号アイコンをクリックし、「**Build for Staging**」を選択します。
1. ビルドが完了したら、省略記号アイコンをクリックし、「**Approve for Publishing**」を選択します。
1. ポップアップで「**承認**」をクリックします。
1. 省略記号アイコンをクリックし、「**Build &amp; Publish to Production**」を選択します。
1. ポップアップで「**公開**」をクリックします。

### 手順 7 - サイトのクラウド設定を有効にする {#enable-configurations}

統合を使用するには、AEM でクラウド設定として割り当てる必要があります

1. AEMコンソールで、**ツール／一般／設定ブラウザー**&#x200B;をクリックします。
1. 「**コアコンポーネントの例**」を確認し、「**プロパティ**」をクリックします。
1. 「**クラウド設定**」を確認し、「**保存して閉じる**」をクリックします。

### 手順 8 - AEM で Launch とサイトの統合を作成する {#create-launch-integration}

AEM が Launch で機能するためには、Launch 統合が必要です。

1. AEM コンソールで、**ツール／Cloud Services／Adobe Launch 設定**&#x200B;をクリックします。
1. 「**コアコンポーネントの例**」を選択し、「**作成**」をクリックします。
1. 「**タイトル**」に、「**Launch 設定**」などと入力します。
1. [手順 4](#finish-ims) で作成した IMS 設定を選択します。
1. 「**会社**」を、必要に応じて選択します。
1. 「**プロパティ**」では、[手順 5](#create-property) で作成し、新しく追加した Launch プロパティを選択します。
1. 「**Include Production Code on Author**」スライダーを右に動かし、「**次へ**」をクリックします。
1. 「**次へ**」をクリックします。
1. 「**次へ**」をクリックします。
1. 「**作成**」をクリックします。

### 手順 9 - AEM サイトを Launch 統合に接続する {#connect-aem}

AEM で Launch 統合を使用するには、クラウド設定として割り当てる必要があります。

1. AEM コンソールで、「**Sites**」をクリックし、**コアコンポーネント**&#x200B;サイトを確認します。
1. 「**プロパティ**」をクリックします。
1. 「**詳細**」タブを選択します。
1. 「**クラウド設定**」で「**コアコンポーネントの例**」を選択し、「**選択**」をクリックします。
1. 「**保存して閉じる**」をクリックします。

### 手順 10 - Launch ロジックがページに適用されていることを確認する {#verify-launch}

これまでの手順が成功したことをテストします。

1. コアコンポーネントライブラリの画像ページをプレビューモードで開きます。`http://<lhost&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 画像をクリックし、メッセージ`A Core Image was clicked`がブラウザーコンソールに表示されることを確認します。

## Launch と AEM およびデータレイヤーの統合 {#data-layer-launch}

これで AEM と Launch の統合が設定され、データレイヤーと統合できます。

### 手順 1 - Adobe Launch でルールを作成する {#create-rule}

[手順 5](#launch-rule) の手順を繰り返し、次の値を使用してAdobe Launch に新しいルールを追加します。

* 名前：`image-click-data-layer`
* イベント：
   * 拡張機能：コア
   * イベントタイプ：DOM Ready
* アクション：
   * 拡張機能：コア
   * アクションタイプ：カスタムコード
   * コード：

      ```
        function onImageClick(event) {
          console.log("Data layer click event tracked by Launch for image: " + event.info.path);
          console.log("dataLayer.getState(): ", adobeDataLayer.getState()); 
        }
        adobeDataLayer.addEventListener('image clicked', onImageClick);
      ```

### 手順 2 - Launch ルールを発行して AEM サイトで使用できるようにする {#publish-rule-2}

[手順 6](#publish-rule) の手順を繰り返して、新しいルールを発行します。

### 手順 3 - Launch ロジックがページに適用されていることを確認する {#verify}

1. コアコンポーネントライブラリの画像ページをプレビューモードで開きます。`http://<host&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 画像をクリックし、次のメッセージがブラウザーコンソールに表示されることを確認します。

   ![データレイヤーコンソールの出力](/help/assets/data-layer-console-output.png)
