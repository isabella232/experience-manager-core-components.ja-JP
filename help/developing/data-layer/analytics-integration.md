---
title: Adobe Client Data Layer を使用してコアコンポーネントと Adobe Analytics を統合する
description: コアコンポーネントイベントを登録するよう Adobe Analytics を設定する方法
translation-type: ht
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: ht
source-wordcount: '1000'
ht-degree: 100%

---


# Adobe Client Data Layer を使用してコアコンポーネントと Adobe Analytics を統合する {#analytics-integration}

このドキュメントでは、AEM、Adobe Client Data Layer、Adobe Launch および Adobe Analytics に基づいてエンドツーエンドの設定をおこない、以下を追跡する方法について詳しく説明します。

* ページが読み込まれるときに Adobe Client Data Layer に保存されるページ ID
* 画像がクリックされたときに Adobe Client Data Layer  に保存される画像パス

コアコンポーネントを例として使用していますが、独自のカスタムコンポーネントに使用することもできます。

## 手順 1 - Adobe Analytics でレポートスイートを作成する {#create-report-suite}

データの集計と分析をおこなうには、まずレポートスイートを作成する必要があります。

1. `https://analytics.adobe.com` にアクセスします。
1. Adobe ID を使用してログインします。
1. **Analytics** アイコンをクリックします。
1. **管理者／レポートスイート**&#x200B;に移動します。
1. **新規作成／レポートスイート**&#x200B;をクリックします。
1. フォームに入力します。
   1. **レポートスイート ID**：`yourSuiteID`
   1. **サイトのタイトル**：`Your suite description`
   1. **タイムゾーン**：必要に応じて
   1. **公開日**：本日の日付、または適切な日付
   1. **日別予想ページビュー数**：必要に応じて 0 または 100
1. 「**レポートスイートの作成**」をクリックします。

成功すると、次のメッセージが緑色で表示されます。`Report Suite <yourReportSuite> has been successfully created.`

## 手順 2 - レポートスイートを表示する {#make-visible}

新しいレポートスイートを使用するには、そのレポートスイートが表示されている必要があります。

1. `https://adminconsole.adobe.com` にアクセスします。
1. Adobe ID を使用してログインします。
1. 「**Adobe Analytics - &lt;yourSite>**」カードをクリックします。
1. 「**Adobe Analytics - &lt;yourSite>**」リンクをクリックします。
1. 「**権限**」タブを選択します。
1. 「**レポートスイート**」行の「**編集**」ボタンをクリックします。
1. [手順 1](#create-report-suite) で作成したレポートスイートの「**+**」ボタンをクリックして、「**含まれる権限項目**」カテゴリに追加します。
1. 「**保存**」をクリックします。

## 手順 3 - AEM サイトと Adobe Launch を統合する {#integrate-launch}

データを生成するには、Launch が AEM サイトに統合されている必要があります。

[Adobe Client Data Layer を使用してコアコンポーネントと Adobe Launch を統合する](launch-integration.md)ドキュメントの手順に従います。

## 手順 4 - Adobe Launch で Adobe Analytics 拡張機能をインストールおよび設定する {#install-extension}

Adobe Analytics 拡張機能を使用すると、Analytics を Launch と統合できます。

1. Adobe Launch から、[手順 3](#integrate-launch) で作成し、新しく追加されたプロパティを選択します。
1. 「**拡張機能**」タブに移動し、「**カタログ**」を選択します。
1. **Adobe Analytics** を検索します。
1. 「**インストール**」をクリックします。
1. 拡張機能を設定します。
   1. 適切な環境に対して、**手順 1** で作成した [Analytics レポートスイート ID](#create-report-suite) を入力します 。
   1. **文字セット**&#x200B;を UTF-8 に設定します。
1. 「保存」をクリックします。

## 手順 5 - Adobe Launch でページ ID のデータ要素を作成する {#create-data-element}

ページ ID を追跡するには、Launch でデータ要素が必要となります。

1. Adobe Launch から、[手順 3](#integrate-launch) で作成したプロパティを選択します。
1. 「**データ要素**」タブを選択し、「**データ要素を追加**」をクリックします。
   1. **名前**：`dl-page-id`
   1. **拡張機能**：**コア**
   1. **データ要素のタイプ**：**カスタムコード**
1. 「**編集画面を開く**」をクリックします。
1. エディターで、次のコードを入力します。`return adobeDataLayer.getState().page.id;`
1. 「**保存**」をクリックします。
1. 「**保存**」をクリックして、データ要素を作成します。

## 手順 6 - Adobe Launch でルールを作成して Analytics でページ ID を追跡する {#track-page}

ルールを使用すると、Analytics のページ ID などのブラウジング属性を追跡できます。

「[Adobe Client Data Layer を使用してコアコンポーネントと Adobe Launch を統合する](launch-integration.md#launch-rule)」ドキュメントのパート 5b の手順を繰り返して、Adobe Launch で次のルールを追加します。

* **名前**：`track-dl-page-id`
* イベント：
   * **拡張機能**：**コア**
   * **イベントタイプ**：**ページ下部**
* アクション 1：
   * **拡張機能**：**Adobe Analytics**
   * **アクションタイプ**：**変数の設定**
   * **prop1**：`%dl-page-id%`
* アクション 2：
   * **拡張機能**：**Adobe Analytics**
   * **アクションタイプ**：**ビーコンを送信**
   * 「**s.t(): Send Data to Adobe Analytics and treat it as a page view**」にチェックマークを付けます

## 手順 7 - Adobe Launch でルールを作成して画像クリックイベントを登録する {#register-click}

ルールを使用すると、Analytics のクリックイベントなどのブラウジング属性を追跡できます。

「[Adobe Client Data Layer を使用してコアコンポーネントと Adobe Launch を統合する](launch-integration.md#launch-rule)」ドキュメントのパート 5b の手順を繰り返して、Adobe Launch で次のルールを追加します。

* **名前**：`register-dl-image-click`
* イベント：
   * **拡張機能**：**コア**
   * **イベントタイプ**：**ページ下部**
* アクション 1：
   * **拡張機能**：**コア**
   * **アクションタイプ**：**カスタムコード**
   * エディター：次のコードを入力します。

      ```
      var myListener = function(event) {
        _satellite.track('dlImageClicked', event.info.path);
      };
      adobeDataLayer.addEventListener('image clicked', myListener());
      ```

## 手順 8 - Adobe Launch でルールを作成して Analytics の画像クリックイベントを追跡する {#track-click}

ルールを使用すると、Analytics のクリックイベントなどのブラウジング属性を追跡できます。

「[Adobe Client Data Layer を使用してコアコンポーネントと Adobe Launch を統合する](launch-integration.md#launch-rule)」ドキュメントのパート 5b の手順を繰り返して、Adobe Launch で次のルールを追加します。

* **名前**：`track-dl-image-click`
* イベント：
   * **拡張機能**：**コア**
   * **イベントタイプ**：**直接呼び出し**
   * **識別子**：`dlImageClicked`
* アクション 1：
   * **拡張機能**：**Adobe Analytics**
   * **アクションタイプ**：**変数の設定**
   * **prop2**：`%event.detail%` として設定
* アクション 2：
   * **拡張機能**：**Adobe Analytics**
   * **アクションタイプ**：**ビーコンを送信**
   * 「**s.t(): Send Data to Adobe Analytics and treat it as a page view**」にチェックマークを付けます

## 手順 9 - Launch コードを Web サイトに公開する {#publish-launch}

Launch でこれらのルールおよびプロパティのトラッキングを有効にするには、コードを公開する必要があります。

1. 「**Adobe Launch**」タブで、「**公開**」タブを選択します。
1. 「**Add New Library**」をクリックします。
1. 「**名前**」に「`data-layer-analytics-1`」と入力します。
1. 「**環境**」として「**Development (development)**」を選択します。
1. 「**Add All Changed Resources**」をクリックします。
1. 次の 3 つのルール（`track-dl-page-id`、`register-dl-image-click` および `track-dl-image-click`）のそれぞれに対して：
1. **ルール／ルール／最新**&#x200B;を選択し、「**Select &amp; Create a New Revision**」をクリックします。
1. 「**Save &amp; Build for Development**」をクリックします。

## 手順 10 - ページをトリガーして Adobe Analytics に情報を送信する {#trigger-page}

この手順では、Chrome 拡張機能 **Launch and DTM Switch** をインストールします。この拡張機能を使用する場合は、Launch コードを作成して開発環境にデプロイする必要があります。ステージング環境と実稼動環境をデプロイする必要はありません。

1. Discovery から Chrome 拡張機能 **Launch and DTM Switch** をインストールします。
1. **Launch スイッチ**&#x200B;アイコンをクリックし、「デバッグ」を「*オン*」に設定します。
1. `http://<host>:<port>/content/core-components-examples/library/image.html`ページをリロードします。
1. ブラウザーコンソールを開くと、次のように表示されます。

![Analytics コンソールの出力](/help/assets/analytics-console-output.png)

>[!TIP]
>
>また、Chrome 用 **Experience Cloud Debugger** 拡張機能をインストールして、ページに関する Adobe Launch および Analytics 固有の情報を表示することもできます。

## 手順 11 - Adobe Analytics で追跡した情報を表示する {#view-info}

これで、Adobe Analytics でトリガーしたイベントを表示できます。

1. `https://analytics.adobe.com` にアクセスします。
1. Adobe ID を使用してログインします。
1. **Analytics** アイコンをクリックします。
1. 「**レポート**」タブを選択します。
1. 右上のドロップダウンから、[手順 1](#create-report-suite) で作成したレポートスイートを選択します。
1. 最初の列で、「**カスタムトラフィック／カスタムトラフィック 1～10／カスタムインサイト 1**」を選択し、データレイヤーに保存されている追跡対象のページ ID（パス）を表示します。次のように表示されます。

   ![カスタムインサイト 1](/help/assets/custom-insight-1.png)

1. 追跡した画像パスをデータレイヤーに保存している場合は、**カスタムインサイト 2** にアクセスして表示します。次のように表示されます。

   ![カスタムインサイト 2](/help/assets/custom-insight-2.png)
