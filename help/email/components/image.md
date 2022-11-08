---
title: 電子メール画像コンポーネント
description: 電子メール画像コンポーネントは、インプレース編集機能を備えたアダプティブな画像コンポーネントです。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 61%

---


# 電子メール画像コンポーネント {#email-image-component}

電子メール画像コンポーネントは、インプレース編集機能を備えたアダプティブな画像コンポーネントです。

## 使用方法 {#usage}

電子メール画像コンポーネントは、アダプティブ画像選択とレスポンシブ動作を備え、ページ訪問者に対する遅延読み込みと、コンテンツ作成者向けの簡単なドラッグ&amp;ドロップによる画像の配置と設定が可能です。

* 画像の幅と追加の設定は、テンプレート作成者が [デザインダイアログ。](#design-dialog)
* コンテンツ編集者は、[設定ダイアログ](#configure-dialog)でアセットをアップロードまたは選択できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、電子メール画像コンポーネントの現在のバージョン（2022 年 10 月に電子メールコアコンポーネントのリリース x で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、ドキュメントを参照してください。 [電子メールコアコンポーネントのバージョン](/help/email/versions.md).

## レスポンシブ機能 {#responsive-features}

電子メール画像コンポーネントには、すぐに使用できる堅牢なレスポンシブ機能が付属しています。 ページテンプレートレベルで、[デザインダイアログ](#design-dialog)を使用して、画像アセットのデフォルトの幅を定義できます。次に、電子メール画像コンポーネントは、ブラウザーウィンドウのサイズに応じて表示される正しい幅を自動的に読み込みます。 ウィンドウのサイズが変更されると、電子メール画像コンポーネントは、その場で適切な画像サイズを動的に読み込みます。 電子メール画像コンポーネントはコンテンツの読み込み用に最適化されているので、コンポーネント開発者はカスタムメディアクエリの定義を気にする必要はありません。

また、電子メール画像コンポーネントは、遅延読み込みをサポートし、ブラウザーに表示されるまで実際の画像アセットの読み込みを遅らせて、コンテンツの応答性を高めます。

>[!TIP]
>
>デフォルトでは、電子メール画像コンポーネントは、アダプティブ画像サーブレットを利用します。 アダプティブ画像サーブレットの仕組みについて詳しくは、[ドキュメント](#adaptive-image-servlet)を参照してください。

## Dynamic Media サポート {#dynamic-media}

電子メール画像コンポーネントは、 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=ja#dynamicmedia) アセット。 これらの機能を[有効](#design-dialog)にすると、簡単なドラッグ＆ドロップで、または他の画像と同様にアセットブラウザーを使用して、Dynamic Media 画像アセットを追加する機能が提供されます。また、画像修飾子、画像プリセット、スマート切り抜きもサポートされます。

E メールコアコンポーネントを使用して構築された E メールエクスペリエンスは、Senseiを利用した、豊富で堅牢で高パフォーマンスの、クロスプラットフォームのDynamic Media画像機能を備えています。

## SVG のサポート {#svg-support}

E メール画像コンポーネントでは、Scalable Vector Graphics(SVG) がサポートされています。

* DAM からの SVG アセットのドラッグ＆ドロップと、ローカルファイルシステムからの SVG ファイルのアップロード、はどちらもサポートされます。
* 元の SVG ファイルがストリーミングされます（変換はスキップされます）。
* SVG 画像の場合、画像モデルで「スマート画像」と「スマートサイズ」が空の配列に設定されます。

### セキュリティ {#security}

セキュリティ上の理由から、元の SVG が画像エディターで直接呼び出されることは決してありません。`<img src=“path-to-component”>` 経由で呼び出されます。これにより、ブラウザーが SVG ファイルに埋め込まれた任意のスクリプトを実行するのを防ぎます。

## コンポーネント出力のサンプル {#sample-component-output}

電子メール画像コンポーネントを実際に体験し、その設定オプションやHTMLおよび JSON 出力の例を確認するには、 [コンポーネントライブラリ。](https://adobe.com/go/aem_cmp_library_email_image)

### 技術的詳細 {#technical-details}

電子メール画像コンポーネントに関する最新の技術ドキュメント [は GitHub にあります。](https://adobe.com/go/aem_cmp_tech_email_image_v1)

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメントです。](/help/developing/overview.md)

画像コンポーネントは、をサポートしています。 [schema.org マイクロデータ。](https://schema.org)

## 設定ダイアログ {#configure-dialog}

電子メール画像コンポーネントには、画像自体の定義と、その説明および基本プロパティの定義をおこなうための設定ダイアログが用意されています。

### 「アセット」タブ {#asset-tab}

![電子メール画像コンポーネントの設定ダイアログの「アセット」タブ](/help/email/assets/email-image-configure-asset.png)

* **ページからアイキャッチ画像を継承** - このオプションは、 [リンクされたページのアイキャッチ画像](page.md)を使用します。画像がリンクされていない場合は現在のページのアイキャッチ画像を使用します。

* **アクセシビリティ用代替テキスト** - このフィールドでは、視覚に障害のあるユーザー向けの画像説明を定義できます。

   * **ページから代替テキストを継承** - このオプションでは、DAM における `dc:description` メタデータのリンク先アセット値の代替説明を使用します。アセットがリンクされていない場合は現在のページの代替説明を使用します。

* **画像アセット**
   * [アセットブラウザー](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=ja)からアセットをドロップするか、「**参照**」オプションをタップすると、ローカルファイルシステムからアップロードできます。
   * 現在選択されている画像を選択解除するには、「**クリア**」をタップまたはクリックします。
   * タップまたはクリック **編集** から [アセットのレンディションの管理](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=ja) （アセットエディター）。

* **代替テキストを提供しない** - このオプションは、画像が単なる装飾画像である場合や、ページへの追加情報を伝えない場合に、スクリーンリーダーなどの支援テクノロジーで画像を無視するように指定します。

* **遅延読み込みを無効にする**  — このオプションは、必要に応じて読み込まずに、すべての画像コンポーネントをプリロードします。

### 「メタデータ」タブ {#metadata-tab}

![画像コンポーネントの設定ダイアログの「メタデータ」タブ](/help/email/assets/email-image-configure-metadata.png)

* **プリセットの種類** - 使用可能な画像プリセットの種類（**画像プリセット**&#x200B;または&#x200B;**スマート切り抜き**）を定義します。これは、[Dynamic Media](#dynamic-meida) 機能が有効な場合にのみ使用できます。
   * **画像プリセット** -When **プリセットの種類** / **画像プリセット** が選択されている場合、ドロップダウン **画像プリセット** が使用可能になり、使用可能なDynamic Mediaプリセットから選択できます。 これは、選択したアセットに対してプリセットが定義されている場合にのみ使用できます。
   * **スマート切り抜き** -When **プリセットの種類** / **スマート切り抜き** がドロップダウンで選択されている **レンディション** が使用可能で、選択したアセットの使用可能なレンディションから選択できます。 これは、選択したアセットに対してレンディションが定義されている場合にのみ使用できます。
   * **画像の修飾子**  — ここで、Dynamic Mediaの追加の画像サービングコマンドを、 `&`（どちらかに関係なく） **プリセットの種類** が選択されている。
* **キャプション** - 画像に関する追加情報。デフォルトでは画像の下に表示されます。
   * **DAM からキャプションを取得** - オンにすると、DAM の `dc:title` メタデータの値が画像のキャプションテキストに設定されます。DAM からアセットが選択された場合にのみ使用できます。
   * **キャプションをポップアップとして表示** - オンにした場合、キャプションは画像の下には表示されなくなり、画像の上にマウスポインターを置いたときに一部のブラウザーでポップアップとして表示されるようになります。
* **リンク** - 画像を別のリソースにリンクします。
   * 別の AEM リソースにリンクする場合は、選択ダイアログを使用します。
   * AEM リソースにリンクしない場合は、絶対 URL を入力します。非絶対 URL は、AEM に対する相対 URL として解釈されます。
   * **リンクを新しいタブで開く** - このオプションを使用すると、リンクは新しいブラウザーウィンドウで開きます。
* **ID**  — このオプションを使用すると、HTML内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS に影響を与える可能性があります。
* **次で修正：**  — このオプションは、画像の幅をピクセル単位で定義します。
* **画像を使用可能な幅に拡大・縮小**  — このオプションは適用されます `"width":"100%"` を画像スタイル属性に追加します。

>[!TIP]
>
>**スマート切り抜き**&#x200B;と&#x200B;**画像プリセット**&#x200B;は、相互に排他的なオプションです。スマート切り抜きレンディションと共に画像プリセットを使用する必要がある場合、作成者は&#x200B;**画像修飾子**&#x200B;を使用して手動でプリセットを追加する必要があります。

### 「スタイル」タブ {#styles-tab-edit}

![電子メール画像コンポーネントの編集ダイアログの「スタイル」タブ](/help/assets/image-configure-styles.png)

電子メール画像コンポーネントは、AEM [スタイルシステム。](/help/get-started/authoring.md#component-styling)

ドロップダウンを使用して、コンポーネントに適用するスタイルを選択します。編集ダイアログでの選択項目は、コンポーネントツールバーから選択した項目と同じ効果があります。

スタイルは、内のこのコンポーネントに対して設定する必要があります [デザインダイアログ](#design-dialog) 」をクリックします。

## デザインダイアログ {#design-dialog}

### 「メイン」タブ {#main-tab}

![画像コンポーネントのデザインダイアログの「メイン」タブ](/help/email/assets/email-image-design-main.png)

* **DM 機能を有効にする** - オンにすると、[Dynamic Media 機能](#dynamic-media)を使用できます。
   * このオプションは、環境で Dynamic Media が有効になっている場合にのみ表示されます。
* **Web 最適化画像を有効にする** - オンにすると、[web に最適化された画像配信サービス](/help/developing/web-optimized-image-delivery.md)は WebP 形式で画像を配信し、画像のサイズを平均で 25%削減します。
   * このオプションは、AEMaaCS でのみ使用できます。
   * オフの場合、または Web に最適化された画像配信サービスを使用できない場合、 [アダプティブ画像サーブレット](/help/developing/adaptive-image-servlet.md) が使用されます。
* **画像は装飾画像** - ページへの画像コンポーネントの追加時に装飾画像オプションが自動的に有効化されるかどうかを定義します。
* **DAM から代替テキストを取得** - ページへの画像コンポーネントの追加時に 、DAM から代替テキストを取得するオプションが自動的に有効化されるかどうかを定義します。
* **DAM からキャプションを取得** - ページへの画像コンポーネントの追加時に、DAM からキャプションを取得するオプションが自動的に有効化されるかどうかを定義します。
* **キャプションをポップアップとして表示** - ページへの画像コンポーネントの追加時に、画像のキャプションをポップアップとして表示するオプションが自動的に有効化されるかどうかを定義します。
* **幅をサイズ変更** - この値は、DAM アセットであるベース画像の幅のサイズ変更に使用されます。
   * 画像の縦横比は維持されます。
   * 値が画像の実際の幅より大きい場合、この値は無効です。
   * この値は、SVG 画像には無効です。

画像の幅（ピクセル単位）のリストを定義でき、コンポーネントは、ブラウザーのサイズに基づいて最も適切な幅で自動的に読み込みます。これは、 [レスポンシブ機能](#responsive-features) 電子メール画像コンポーネントの

* **幅** - 画像の幅（ピクセル単位）のリストを定義でき、コンポーネントは、ブラウザーサイズに基づいて最適な幅を自動的に読み込みます。
   * 別のサイズを追加するには、「**追加**」ボタンをタップまたはクリックします。
      * サイズの順序を並べ替えるには、グラブハンドルを使用します。
      * 幅を削除するには、**削除**&#x200B;アイコンを使用します。
   * デフォルトでは、画像の読み込みは、画像が表示される時点まで遅延されます。
      * ページ読み込み時に画像を読み込むには、オプション「**遅延読み込みを無効化**」を選択します。
* **JPEG 画質** - 変換（拡大／縮小や切り抜きなど）が行われる JPEG 画像の品質係数（0 ～ 100 パーセントで指定）。
* **デフォルトの幅**  — デザインダイアログで使用される画像のデフォルトの幅（ピクセル単位）

>[!TIP]
>
>幅を慎重に定義してレンディションの選択を最適化するためのヒントについては、[アダプティブ画像サーブレット](/help/developing/adaptive-image-servlet.md)のドキュメントを参照してください。

### 「スタイル」タブ {#styles-tab}

電子メール画像コンポーネントは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling).