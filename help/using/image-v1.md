---
title: 画像コンポーネント（v1）
seo-title: 画像コンポーネント（v1）
description: コアコンポーネントの画像コンポーネントは、インプレース編集機能を備えたアダプティブな画像コンポーネントです。
seo-description: コアコンポーネントの画像コンポーネントは、インプレース編集機能を備えたアダプティブな画像コンポーネントです。
uuid: 20ea7921-511d-4d3a-b3df-c2f2c1d8455d
content-type: reference
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: ab9041ab-e29e-4277-b326-85ab37df8413
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 画像コンポーネント（v1）{#image-component-v}

コアコンポーネントの画像コンポーネントは、インプレース編集機能を備えたアダプティブな画像コンポーネントです。

## 使用方法 {#usage}

画像コンポーネントを使用すれば、画像アセットを簡単に配置したり、インプレース編集をおこなったりすることができます。これには、遅延読み込みに対応したアダプティブ画像選択や切り抜きなど、コンテンツ作成者向けの機能が備わっています。

[デザインダイアログ](image-v1.md#main-pars_title_1995166862)では、テンプレート作成者が、許可される画像の幅や切り抜きの設定、追加の設定などを定義できます。コンテンツエディターは、[設定ダイアログ](image-v1.md#main-pars_title_55926120)でアセットをアップロードまたは選択し、[編集ダイアログ](image-v1.md#main-pars_title)で画像の切り抜きをおこなうことができます。画像を単純にインプレースで変更することもでき、非常に便利です。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 のコアコンポーネントのリリース 1.0.0 で最初に導入された、画像コンポーネントの v1 について説明します。

次の表に、画像コンポーネントの v1 の互換性の一覧を示します。

| AEM のバージョン | 画像コンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、画像コンポーネントの v1 について説明します。
>
>画像コンポーネントの現在のバージョンについて詳しくは、[画像コンポーネント](image.md)ドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retailのサンプルです](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### スクリーンショット {#screenshot}

![](assets/chlimage_1-7.png)

### HTML {#html}

```
<div class="cmp cmp-image aem-GridColumn aem-GridColumn--default--12">
 
        <noscript data-cmp-image="{&#34;smartImages&#34;:[],&#34;smartSizes&#34;:[],&#34;lazyEnabled&#34;:true}">
            <img src="/content/we-retail/us/en/equipment/_jcr_content/root/responsivegrid/image.img.jpg" alt="Surfboard"/>
        </noscript>

</div>
```

### JSON {#json}

```
"image": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "smartSizes": [],
              "smartImages": [],
              "lazyEnabled": true,
              "src": "/content/we-retail/us/en/equipment/equipment/jcr%3acontent/root/responsivegrid/image.img.jpeg",
              ":type": "weretail/components/content/image"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](versions.md#main-pars_title_236368006)を参照してください。

## 設定ダイアログ {#configure-dialog}

画像コンポーネントには、標準の[編集ダイアログ](image-v1.md#main-pars_title)と[デザインダイアログ](image-v1.md#main-pars_title_1995166862)のほかに、画像自体の定義やその説明および基本プロパティの定義をおこなうための設定ダイアログも用意されています。

![](assets/chlimage_1-50.png)

* **画像アセット**
   * Drop an asset from the [asset browser](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) or tap the **browse** option to upload from a local file system.
   * 現在選択されている画像を選択解除するには、「**クリア**」をタップまたはクリックします。
   * Tap or click **Edit** to [mange the renditions of the asset](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) in the asset editor.

* **画像は装飾画像** - 画像が支援テクノロジーによって無視される場合（したがってその代替テキストが不要な場合）はオンにします。これは、装飾画像にのみ適用されます。
* **代替テキスト** - 視覚に障害のあるユーザー向けの、画像の意味や機能を示す代替テキスト。
* **リンク**
   * 画像を別のリソースにリンクします。
   * 別の AEM リソースにリンクする場合は、選択ダイアログを使用します。
   * AEM リソースにリンクしない場合は、絶対 URL を入力します。非絶対 URL は、AEM に対する相対 URL として解釈されます。

* **キャプション** - 画像に関する追加情報。デフォルトでは画像の下に表示されます。
* **キャプションをポップアップとして表示** - オンにした場合、キャプションは画像の下には表示されなくなり、画像の上にマウスポインターを置いたときに一部のブラウザーでポップアップとして表示されるようになります。

## 編集ダイアログ{#edit-dialog}

編集ダイアログでは、コンテンツ作成者は画像の切り抜き、画像のローンチマップの変更および画像のズームをおこなえます。

![](assets/chlimage_1-8.png)

* 切り抜きを開始

   ![](assets/chlimage_1-9.png)

   このオプションを選択すると、定義済みの切り抜き比率のドロップダウンが開きます。

   * 独自の切り抜きを定義するには、オプション「**フリーハンド**」を選択します。
   * 元のアセットを表示するには、オプション「**切り抜きを削除**」を選択します。
   切り抜きオプションを選択したら、青色のハンドルを使用して画像上の切り抜きのサイズを調整します。

   ![](assets/chlimage_1-10.png)

* 右に回転

   ![](assets/chlimage_1-11.png)

   画像を右（時計回り）に 90° 回転させるには、このオプションを使用します。

* ローンチマップ

   ![](assets/chlimage_1-12.png)

   画像にローンチマップを適用するには、このオプションを使用します。このオプションを選択すると、ユーザーがマップシェイプを選択できる新しいウィンドウが開きます。

   * **長方形マップを追加**
   * **円形マップを追加**
   * **多角形マップを追加**

      * デフォルトでは三角形のマップが追加されます。シェイプの線をダブルクリックすると、新しい青色のサイズ変更ハンドルが新しいサイドに追加されます。
   マップシェイプを選択すると、マップは画像に重なって表示され、サイズを変更することができます。青色のサイズ変更ハンドルをドラッグ＆ドロップしてシェイプを調整します。

   ![](assets/chlimage_1-13.png)

   ローンチマップのサイズ調整が完了したら、マップをクリックしてフローティングツールバーを開き、リンクのパスを定義します。

   * **パス**
      * パスピッカーオプションを使用して AEM 内のパスを選択します。
      * パスが AEM 内にない場合は、絶対 URL を使用します。非絶対パスは、AEM に対する相対パスとして解釈されます。

      * **代替テキスト**
パス参照先の代替説明
      * **ターゲット**
         * **同じタブ**
         * **新しいタブ**
         * **親フレーム**
         * **トップフレーム**
   マップを保存するには青色のチェックマークを、キャンセルするには黒色の x を、削除するには赤色のごみ箱を、それぞれタップまたはクリックします。

   ![](assets/chlimage_1-14.png)

* ズームをリセット

   ![](assets/chlimage_1-15.png)

   画像が既にズームされている場合にこのオプションを使用すれば、ズームレベルがリセットされます。

* ズームスライダーを開く

   ![](assets/chlimage_1-16.png)

   画像のズームレベルを制御するためのスライダーを表示するには、このオプションを使用します。

   ![](assets/chlimage_1-17.png)

インプレースエディターを使用して画像を変更することもできます。スペース上の制限のため、インラインで使用できるのは基本的なオプションのみです。すべての編集オプションを使用したい場合は、フルスクリーンモードを使用してください。

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>画像編集操作（切り抜き、反転、回転）は GIF 画像ではサポートされません。編集モードで GIF に対しておこなわれたそのような変更は、一切保持されません。

## デザインダイアログ{#design-dialog}

デザインダイアログでは、コンテンツ作成者がこのコンポーネントの使用時に利用できる切り抜き、アップロード、回転の各オプションを、テンプレート作成者が定義することができます。

### メイン {#main}

「**メイン**」タブでは、画像の許可される幅（ピクセル単位）のリストを定義し、リスト内の最も適切な幅が自動的に読み込まれるようにします。

![](assets/chlimage_1-51.png)

別のサイズを追加するには、「追加」ボタンをタップまたはクリックします。

* サイズの順序を変更するには、グラブハンドルを使用します。
* 幅を削除するには、削除アイコンを使用します。

デフォルトでは、画像の読み込みは、画像が表示される時点まで遅延されます。ページ読み込み時に画像を読み込むには、オプション「**遅延読み込みを無効化**」を選択します。

### 機能 {#features}

「**機能**」タブでは、コンテンツ作成者がコンポーネントの使用時に利用できるオプション（アップロードオプション、向きのオプション、切り抜きオプションなど）を定義できます。

* ソース

   ![](assets/chlimage_1-19.png)

   コンテンツ作成者が自身のローカルコンピュータから画像をアップロードできるようにするには、オプション「**ファイルシステムからのアセットのアップロードを許可**」を選択します。コンテンツ作成者が AEM からしかアセットを選択できないようにするには、このオプションを選択解除します。

* 向き

   ![](assets/chlimage_1-20.png)

   * **回転** - コンテンツ作成者が「**右に回転**」オプションを使用できるようにするには、このオプションを使用します。
   * **反転**
コンテンツ作成が「**水平方向に反転**」および「**垂直方向に反転**」オプションを使用できるようにするには、このオプションを使用します。
   >[!CAUTION]
   >
   >「**反転**」オプションはデフォルトでは無効になっています。これを有効にすると、画像コンポーネントの編集ダイアログで「**水平方向に反転**」および「**垂直方向に反転**」ボタンが表示されますが、この機能は現在 AEM でサポートされていないので、これらのオプションを使用しておこなわれた変更は一切保持されません。

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
-->

* 切り抜き

   ![](assets/chlimage_1-21.png)

   コンテンツ作成者が編集ダイアログでコンポーネントの画像の切り抜きをおこなえるようにするには、オプション「**切り抜きを許可**」を選択します。
   * 定義済みの切り抜き縦横比を追加するには、「**追加**」をクリックします。
   * わかりやすい名前を入力します。この名前が「**切り抜きを開始**」ドロップダウンに表示されます。
   * 縦横比の数値を入力します。
   * 縦横比の順序を変更するには、ドラッグハンドルを使用します
   * 縦横比を削除するには、ごみ箱アイコンを使用します。
   >[!CAUTION]
   >
   >AEM では、切り抜きの縦横比は「**高さ / 幅**」で定義されます。これは従来の定義である「幅 / 高さ」とは異なり、レガシー互換性のための設定です。UI には比率自体ではなく UI が表示されるので、比率にわかりやすい名前を付けていれば、コンテンツ作成者がこの違いに気付くことはありません。

## 技術的詳細 {#technical-details}

イメージコンポーネントに関する最新の技術ドキュメ [ントは、GitHubで入手できます](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。
