---
title: Adobe Client Data Layerを使用したコアコンポーネントとAdobe Analyticsの統合
description: コアコンポーネントイベントを登録するためのAdobe Analyticsの設定方法
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 3%

---


# Adobe Client Data Layerを使用したコアコンポーネントとAdobe Analyticsの統合 {#analytics-integration}

このドキュメントでは、AEM、Adobeクライアントデータレイヤー、Adobe LaunchおよびAdobe Analyticsに基づいてエンドツーエンドの設定を設定し、追跡する方法について詳しく説明します。

* ページが読み込まれるときにAdobeクライアントデータレイヤーに保存されるページID
* 画像がクリックされたときにAdobeクライアントデータレイヤーに保存される画像パス

これは、コアコンポーネントを例として使用しますが、独自のカスタムコンポーネントに使用することもできます。

##  手順1 - Adobe Analyticsでレポートスイートを作成する {#create-report-suite}

データの集計と分析を行うには、まずレポートスイートを作成する必要があります。

1. `https://analytics.adobe.com` にアクセスします。
1. Adobe IDを使用してサインインします。
1. Click the **Analytics** icon.
1. [ **管理者] > [レポートスイート**]に移動します。
1. Click **Create New -> Report Suite**.
1. フォームに入力します。
   1. **レポートスイート ID**: `yourSuiteID`
   1. **サイトのタイトル**: `Your suite description`
   1. **タイムゾーン**: 必要に応じて
   1. **Go Live日**: 今日の日付、または適切な日付
   1. **予想日別ページ表示数**: 100または必要に応じて
1. Click **Create Report Suite**.

成功すると、次のメッセージが緑色で表示されます。 `Report Suite <yourReportSuite> has been successfully created.`

## 手順2 — レポートスイートを表示する {#make-visible}

新しいレポートスイートを使用するには、そのレポートスイートが表示されている必要があります。

1. `https://adminconsole.adobe.com` にアクセスします。
1. Adobe IDを使用してサインインします。
1. 「 **Adobe Analytics - &lt;yourSite>** 」カードをクリックします。
1. 「 **Adobe Analytics - &lt;yourSite>** 」リンクをクリックします。
1. Select the **Permissions** tab
1. 「 **レポートスイート** 」行の「 **編集** 」ボタンをクリックします。
1. **手順1で作成したレポートスイートの「** +」 [ボタンをクリックして、「](#create-report-suite) 含まれる権限項目 **** 」カテゴリに追加します。
1. 「**保存**」をクリックします。

## 手順3 - AEMサイトとAdobe Launchを統合する {#integrate-launch}

データを生成するには、LaunchがAEMサイトに統合されている必要があります。

Adobeクライアントデータレイヤーの [使用によるコアコンポーネントの統合とAdobe Launch](launch-integration.md) ドキュメントの手順に従います。

## 手順4 - Adobe LaunchでのAdobe Analytics Extensionのインストールと設定 {#install-extension}

Adobe Analytics Extensionを使用すると、AnalyticsをLaunchと統合できます。

1. 「Adobe Launch」で、 [手順3で作成した新しく追加されたプロパティを選択します。](#integrate-launch)
1. 「 **拡張子** 」タブに移動し、「 **カタログ**」を選択します。
1. 「 **Adobe Analytics**」を検索します。
1. 「**インストール**」をクリックします。
1. 拡張機能を設定します。
   1. 適切な **環境に対して、** 手順1で作成した [AnalyticsレポートスイートIDを入力します](#create-report-suite) 。
   1. Set **Character Set** to UTF-8
1. 「保存」をクリックします。

## 手順5 - Adobe LaunchでページIDのデータ要素を作成する {#create-data-element}

ページIDを追跡するには、「起動」でデータ要素が必要です。

1. 「Adobe Launch」で、 [手順3で作成したプロパティを選択します。](#integrate-launch)
1. 「 **データ要素** 」タブを選択し、「 **データ要素**」をクリックします。
   1. **名前**: `dl-page-id`
   1. **拡張子**: **コア**
   1. **データ要素の種類**: **カスタムコード**
1. 「 **編集画面を開く」をクリックします**
1. エディターで、次のコードを入力します。 `return adobeDataLayer.getState().page.id;`
1. 「**保存**」をクリックします。
1. 「 **保存** 」をクリックして、データ要素を作成します。

## 手順6 - Adobe Launchでルールを作成してAnalyticsでページIDを追跡する {#track-page}

ルールを使用すると、AnalyticsのページIDなど、ブラウズ属性を追跡できます。

「Adobe Client Data Layerの [使用」のパート5bで手順を繰り返して、コアコンポーネントとAdobe Launch](launch-integration.md#launch-rule) ドキュメントを統合し、Adobe Launchに次のルールを追加します。

* **名前**: `track-dl-page-id`
* イベント:
   * **拡張子**: **コア**
   * **イベントタイプ**: **ページ下部**
* アクション1:
   * **拡張子**: **Adobe Analytics**
   * **Action Type**: **変数の設定**
   * **prop1**: `%dl-page-id%`
* アクション2:
   * **拡張子**: **Adobe Analytics**
   * **Action Type**: **ビーコンの送信**
   * Check **s.t(): Adobe Analyticsにデータを送信し、ページ表示として扱う**

## 手順7 - Adobe Launchでルールを作成してImage Clickイベントを登録する {#register-click}

ルールを使用すると、Analyticsのクリックイベントなど、参照属性を追跡できます。

「Adobe Client Data Layerの [使用」のパート5bで手順を繰り返して、コアコンポーネントとAdobe Launch](launch-integration.md#launch-rule) ドキュメントを統合し、Adobe Launchに次のルールを追加します。

* **名前**: `register-dl-image-click`
* イベント:
   * **拡張子**: **コア**
   * **イベントタイプ**: **ページ下部**
* アクション1:
   * **拡張子**: **コア**
   * **Action Type**: **カスタムコード**
   * エディタ： 次のコードを入力します。

      ```
      var myListener = function(event) {
        _satellite.track('dlImageClicked', event.info.path);
      };
      adobeDataLayer.addEventListener('image clicked', myListener());
      ```

## 手順8 - Adobe Launchでルールを作成し、Analyticsでのイメージクリックイベントを追跡する {#track-click}

ルールを使用すると、Analyticsのクリックイベントなど、参照属性を追跡できます。

「Adobe Client Data Layerの [使用」のパート5bで手順を繰り返して、コアコンポーネントとAdobe Launch](launch-integration.md#launch-rule) ドキュメントを統合し、Adobe Launchに次のルールを追加します。

* **名前**: `track-dl-image-click`
* イベント:
   * **拡張子**: **コア**
   * **イベントタイプ**: **ダイレクト型**
   * **識別子**: `dlImageClicked`
* アクション1:
   * **拡張子**: **Adobe Analytics**
   * **Action Type**: **変数の設定**
   * **prop2**: 設定形式 `%event.detail%`
* アクション2:
   * **拡張子**: **Adobe Analytics**
   * **Action Type**: **ビーコンの送信**
   * Check **s.t(): Adobe Analyticsにデータを送信し、ページ表示として扱う**

## 手順9 — 起動コードをWebサイトに公開する {#publish-launch}

「起動」でこれらのルールおよびプロパティの追跡を有効にするには、コードを発行する必要があります。

1. 「 **Adobe Launch** 」タブで、「 **Publishing** 」タブを選択します。
1. 「 **追加新規ライブラリ**」をクリックします。
1. As **Name** enter: `data-layer-analytics-1`.
1. 「 **環境** 」として「 **開発（開発）」を選択し**&#x200B;ます。
1. 「 **追加All Changed Resources**」をクリックします。
1. 次の3つのルール(`track-dl-page-id`、 `register-dl-image-click` および `track-dl-image-click`)のそれぞれに対して、
1. 「 **ルール」>「ルール」>「最新** 」を選択し、「 **選択して新しいリビジョンを作成**」をクリックします。
1. 「**保存して開発用にビルド**」をクリックします。

## 手順10 - Adobe Analyticsに情報を送信するページをトリガーする {#trigger-page}

この手順では、Chrome拡張機能 **LaunchとDTM Switchをインストールします**。 この拡張機能を使用する場合は、起動コードを作成して開発環境にデプロイする必要があります。 ステージング用と実稼動用の環境をデプロイする必要はありません。

1. Chrome Extension **LaunchとDTM Switch** from Discoveryをインストールします。
1. スイッチの **起動** アイコンをクリックし、「デバッグ」を「 *オン*」に設定します。
1. ページを再読み込み `http://<host>:<port>/content/core-components-examples/library/image.html`.
1. ブラウザーコンソールを開くと、次のように表示されます。

![Analyticsコンソールの出力](/help/assets/analytics-console-output.png)

>[!TIP]
>
>また、Chrome用 **Experience Cloud Debugger** extensionをインストールして、Adobe LaunchとAnalyticsによって表示することもできます。

## 手順11 - Adobe Analyticsでの追跡情報の表示 {#view-info}

これで、Adobe Analyticsでトリガーしたイベントを表示できます。

1. `https://analytics.adobe.com` にアクセスします。
1. Adobe IDを使用してサインインします。
1. Click the **Analytics** icon.
1. Select the **Reports** tab.
1. 右上のドロップダウンで、 [手順1で作成したレポートスイートを選択します。](#create-report-suite)
1. 最初の列で、「 **カスタムトラフィック —>カスタムトラフィック1-10 ->カスタムインサイト1** 」を選択し、データレイヤーに保存されている追跡対象のページID（パス）を表示します。 次のように表示されます。

   ![カスタムインサイト1](/help/assets/custom-insight-1.png)

1. 追跡する画像パスをデータレイヤーに保存している場合は、 **カスタムインサイト2** にアクセスして表示します。 次のように表示されます。

   ![カスタムインサイト2](/help/assets/custom-insight-2.png)
