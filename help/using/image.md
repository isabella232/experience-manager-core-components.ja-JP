---
title: 画像コンポーネント
seo-title: 画像コンポーネント
description: コアコンポーネント画像コンポーネントは、インプレース編集のアダプティブ画像コンポーネント機能です。
seo-description: コアコンポーネント画像コンポーネントは、インプレース編集のアダプティブ画像コンポーネント機能です。
uuid: 1a229d42-2428-43aa-895a-9b7c1bf02834
contentOwner: User
content-type: リファレンス
topic-tags: オーサリング
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: d4684f33-2fb5-4f32-866f-7136cf1800d7
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 画像コンポーネント{#image-component}

Core Component Image Componentは、インプレース編集機能を備えたアダプティブ画像コンポーネントです。

## 使用 {#usage}

画像コンポーネントを使用すると、画像アセットを簡単に配置し、インプレース編集を行うことができます。これには、遅延読み込みとコンテンツ作成者の切り抜きを伴うアダプティブ画像選択機能があります。

The image widths as well as cropping and additional settings can be defined by the template author in the [design dialog](#design-dialog). The content editor can upload or select assets in the [configure dialog](#configure-dialog) and crop the image in the [edit dialog](#edit-dialog). 便宜上、画像の単純な配置の変更も利用できます。

## Version and Compatibility {#version-and-compatibility}

現在のバージョンのImage Componentはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](image-v1.md) | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## SVG Support {#svg-support}

Scalable Vector Graphics（SVG）はImage Componentでサポートされています。

* DAMからSVGアセットをドラッグ&amp;ドロップすると、ローカルファイルシステムからSVGファイルアップロードがアップロードされます。
* アダプティブ画像サーブレットストリームは、元のSVGファイルをストリーミングします（変換はスキップされます）。
* SVG画像の場合、画像モデルでは「スマート画像」と「スマートサイズ」が空の配列に設定されます。

### セキュリティ {#security}

セキュリティ上の理由から、元のSVGは画像エディターで直接呼び出されることはありません。It is called through `<img src=“path-to-component”>`. これにより、SVGファイルに埋め込まれているスクリプトが実行されなくなります。

>[!CAUTION]
>
>SVG support requires release 2.1.0 of the Core Components or higher along with [service pack 2](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) for AEM 6.4 or [service pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) for AEM 6.3 or higher to support [new image editor features](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) within AEM.

## Sample Component Output {#sample-component-output}

To experience the Image Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/image.html).

### Technical Details {#technical-details}

The latest technical documentation about the Image Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Image Component supports [schema.org microdata](https://schema.org).

## Configure Dialog {#configure-dialog}

In addition to the standard [edit dialog](#edit-dialog) and [design dialog](#design-dialog), the image component offers a configure dialog where the image itself is defined along with its description and basic properties.

### Asset Tab {#asset-tab}

![](assets/screen_shot_2018-01-08at114245.png)

* **イメージアセット**
   * [アセットブラウザからアセットをドロップ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) するか、 **または参照** オプションをタップしてローカルファイルシステムからアップロードします。
   * Tap or click **Clear** to de-select the currently selected image.
   * **アセット** エディターでアセットのレンディションを [作成するには、「編集」を](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) タップまたはクリックします。

### Metadata Tab {#metadata-tab}

![](assets/screen_shot_2018-01-08at114527.png)

* **画像は装飾的な** もので、画像が支援テクノロジーで無視される必要があるため、代替テキストを必要としません。これは、装飾的な画像にのみ適用されます。
* **視覚障害のある読者のための代替テキスト** の代替テキスト。
   * Get alternative text from DAM - When checked the image&#39;s alternative text will be populated with the value of the `dc:description` metadata in DAM.

* **キャプション** 画像に関する追加情報。初期設定で画像の下に表示されます。
   * **DAM** からキャプションを取得チェックをオンにすると、画像のキャプションテキストにDAM内の `dc:title` メタデータの値が入力されます。
   * **キャプションをポップアップ** として表示する場合、キャプションは画像の下に表示されませんが、画像の上にマウスポインターを置くとポップアップとして表示されます。

* **リンク**
   * 画像を別のリソースにリンクします。
   * 選択ダイアログを使用して、別のAEMリソースにリンクします。
   * AEMリソースにリンクしていない場合は、絶対URLを入力します。非アクティブURLは、AEMに対して相対的に解釈されます。

## Edit Dialog {#edit-dialog}

編集ダイアログを使用すると、コンテンツ作成者は、コンテンツ作成者が起動、起動マップの変更、画像のズームを実行できます。

![](assets/chlimage_1-8.png)

* 切り抜きを開始

   ![](assets/chlimage_1-9.png)

   このオプションを選択すると、切り抜きの縦横比が定義済みのドロップダウンが表示されます。

   * Choose the option **Free Hand** to define your own crop.
   * Choose the option **Remove Crop** to display the original asset.
   切り抜きオプションを選択したら、青いハンドルを使用して画像上の切り抜きのサイズを調整します。

   ![](assets/chlimage_1-10.png)

* 右に回転

   ![](assets/chlimage_1-11.png)

   画像を右（時計回り）に90°回転させるには、このオプションを使用します。

* 水平方向に反転

   ![](assets/screen_shot_2018-04-16at091404.png)

   このオプションを使用すると、画像を水平方向に反転したり、Y軸に沿って画像を180°回転させたりできます。

* 垂直方向に反転

   ![](assets/screen_shot_2018-04-16at091410.png)

   このオプションを使用すると、画像を垂直方向に反転したり、x軸に沿って画像を180°回転させたりできます。

* Map Map

   >[!CAUTION]
   >
   >The Launch Map feature requires release 2.1.0 of the Core Components or higher along with [service pack 2](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) for AEM 6.4 or [service pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) for AEM 6.3 or higher to support [new image editor features](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) within AEM.

   ![](assets/chlimage_1-12.png)

   このオプションを使用して、起動マップを画像に適用します。このオプションを選択すると、ユーザーがマップの形状を選択できる新しいウィンドウが開きます。

   * **長方形マップを追加**
   * **円形マップを追加**
   * **多角形マップを追加**
      * デフォルトでは、三角形のマップが追加されます。シェイプの行をダブルクリックして、新しい青いサイズ変更ハンドルを新しいサイドに追加します。
   マップシェイプを選択すると、サイズ変更可能な画像に重ね合わされます。青いサイズのサイズ変更ハンドルをドラッグ&amp;ドロップして、シェイプを調整します。

   ![](assets/chlimage_1-13.png)

   起動マップをサイズ調整したら、クリックしてフローティングツールバーを開き、リンクのパスを定義します。

   * **パス**
      * パスピッカーオプションを使用してAEMでパスを選択する
      * パスがAEMにない場合は、絶対URLを使用します。絶対パスは、AEMに対する相対パスで解釈されます。
   * **代替テキスト** パス先の代替説明
   * **ターゲット**
      * **同じタブ**
      * **新しいタブ**
      * **親フレーム**
      * **トップフレーム**
   青のチェックマークをタップまたはクリックして保存し、黒のxはキャンセルし、赤のごみ箱はマップを削除します。

   ![](assets/chlimage_1-14.png)

* ズームをリセット

   ![](assets/chlimage_1-15.png)

   画像が既にズームされている場合は、このオプションを使用してズームレベルをリセットします。

* Open Zoom Slider

   ![](assets/chlimage_1-16.png)

   このオプションを使用して、画像のズームレベルを制御するスライダを表示します。

   ![](assets/chlimage_1-17.png)

インプレースエディターを使用して画像を変更することもできます。スペースの制限により、基本オプションのみがインラインで使用できます。フルスクリーンモードの場合は、フルスクリーンモードを使用します。

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>画像編集操作（切り抜き、反転、回転）はGIF画像ではサポートされていません。編集モードで行われたそのような変更は、保持されません。

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者がこのコンポーネントを使用するときに、コンテンツ作成者による切り抜き、アップロード、回転オプションおよびアップロードオプションを定義できます。

### Main Tab {#main-tab}

**「メイン** 」タブでは、画像の幅のリストをピクセル単位で定義して、リストから最も適切な幅を自動的に読み込むことができます。

また、ページにコンポーネントを追加するときに、自動または無効にする一般的なコンポーネントオプションを定義できます。

![](assets/screenshot_2018-10-19at102756.png)

* **遅延読み込みを有効に** する画像コンポーネントをページに追加するときに遅延読み込みオプションが自動的に有効になっている場合に、定義を有効にします。
* **画像は、画像コンポーネントをページに追加するときに、装飾的な画像オプションが自動的に有効になっている場合に定義される装飾** 的な定義です。
* **DAM** から代替テキストを取得する場合、画像コンポーネントをページに追加するときにDAMから代替テキストを取得するオプションが自動的に有効になっている場合に、このテキストを定義します。
* **DAM** からキャプションを取得するために、画像コンポーネントをページに追加するときにDAMからキャプションを取得するオプションが自動的に有効になっているかどうかを定義します。
* **キャプションをポップアップ** として表示するには、画像コンポーネントをページに追加するときに、画像キャプションをポップアップとして表示するオプションが自動的に有効になっているかどうかを定義します。
* **UUIDトラッキング** チェックを無効にすると、画像アセットのUUIDのトラッキングが無効になります。

* **幅** 画像の幅のリストをピクセル単位で定義して、リストから最も適切な幅を自動的に読み込みます。
   * Tap or click the **Add** button to add another size.
      * グラブハンドルを使用して、サイズの順序を変更します。
      * Use the **Delete** icon to remove a width.
   * 初期設定では、画像の読み込みは、表示されるまで延期されます。
      * Select the option **Disable lazy loading** to load the images upon page load.
* **JPEG画質**変換（例えば、拡大縮小またはトリミング）
JPEG画像の画質係数（0~100のパーセンテージ）。

>[!CAUTION]
>
>&quot;JPEG画質」オプションは、コアコンポーネントのリリース2.2.0以降で使用できます。

>[!NOTE]
>
>As of release 2.2.0 of the Core Components, the Image Component adds the unique UUID attribute `data-asset-id` to the image asset to allow tracking and analysis of the number of views that individual assets receive.

### Features Tab {#features-tab}

**「機能** 」タブでは、アップロードオプション、方向、切り抜きオプションなど、コンポーネントの使用時にコンテンツ作成者が使用できるオプションを定義できます。

* ソース

   ![](assets/chlimage_1-19.png)

   Select the option **Allow asset upload from file system** to allow content authors to upload images from his or her local computer. コンテンツ作成者がAEMからアセットのみを選択できるようにするには、このオプションを選択解除します。

* 向き

   ![](assets/chlimage_1-20.png)

* **回転** このオプションを使用すると、コンテンツ作成者は「右 **に回転」** オプションを使用できます。
* **フリップ** このオプションを使用すると、コンテンツ作成者は「水平 **方向に反転」** および「垂直 **方向に反転」** オプションを使用できます。

   >[!CAUTION]
   >
   >**「フリップ」** オプションはデフォルトで無効になっています。Enabling it will display the **Flip Vertically** and **Flip Horizontally** buttons in the edit dialog of the image component, however the feature is not currently supported by AEM and any changes made using these options will not be persisted.

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
 -->

* 切り抜き

   ![](assets/chlimage_1-21.png)

   Select the option **Allow crop** to allow the content author to crop the image in the component in the edit dialog.
   * **「追加」** をクリックして、定義済みの切り抜き縦横比を追加します。
   * Enter a descriptive name, which will be shown in the **Start Crop** dropdown.
   * 縦横比の数値を入力します。
   * ドラッグハンドルを使用して、縦横比の順序を再調整します
   * ごみ箱アイコンを使用して、縦横比を削除します。
   >[!CAUTION]
   >
   >Note that in AEM, crop aspect ratios are defined as **height/width**. これは、従来の幅と高さの定義とは異なり、従来の互換性の理由で行われます。コンテンツの作成者は、比率の明確な名前を指定している限り、割合を認識しません。これは、比率自体ではなく、UIに表示されるからです。

### Styles Tab {#styles-tab-1}

The Image Component supports the AEM [Style System](authoring.md#component-styling).