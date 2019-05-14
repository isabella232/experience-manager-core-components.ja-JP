---
title: Teaserコンポーネント
seo-title: Teaserコンポーネント
description: Teaserコンポーネントでは、画像、タイトル、リッチテキストおよびオプションのコンテンツへのリンクを表示できます。
seo-description: Teaserコンポーネントでは、画像、タイトル、リッチテキストおよびオプションのコンテンツへのリンクを表示できます。
uuid: 46989314- df37-448b-8562- c707043f2160
contentOwner: behnert
content-type: リファレンス
topic-tags: コアコンポーネント
discoiquuid: e597c18e-3643-41be-9878-4a7872f1ab90
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Teaserコンポーネント{#teaser-component}

Core Component Teaserコンポーネントでは、画像、タイトル、リッチテキストおよびオプションのコンテンツへのリンクを表示できます。

## 使用方法 {#usage}

Teaserコンポーネントを使用すると、コンテンツ、タイトルまたはリッチテキストを使用してコンテンツ、タイトル、またはその他のアクションにリンクすることで、コンテンツ作成者がより簡単にコンテンツにティーザーを作成できます。

テンプレート作成者は [、デザインダイアログ](#design-dialog) を使用して、誘い文句（CTA:コールトゥアクション）を作成するオプションを定義したり、リンクを追加したり、様々な表示オプションを無効にすることができます。コンテンツ作成者は [、設定ダイアログ](#configure-dialog) を使用して、画像の設定、CTASの定義、タイトルと説明の設定、個々のティーザーへのリンクの設定を行うことができます。画像 [コンポーネント](image.md#edit-dialog)[](image.md) の編集ダイアログにアクセスして、Teaser画像を変更できます。

## バージョンと互換性 {#version-and-compatibility}

Teaserコンポーネントの現在のバージョンはv1であり、2018年7月のコアコンポーネントのリリース2.1.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v1 | 互換性 | 互換性 | 互換性 |

## サンプルコンポーネントの出力 {#sample-component-output}

以下は、We. Retailから [取得されたサンプル](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)です。

### スクリーンショット {#screenshot}

![](assets/screen_shot_2018-07-04at145042.png)

### コンポーネントライブラリ

Teaserコンポーネントをエクスペリエンスとして体験するには、その設定オプションの例およびHTMLおよびJSON出力の例 [](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html)を参照してください。

### 技術的詳細 {#technical-details}

Teaserコンポーネントに関する最新の技術ドキュメントは、GitHubにあり [ます](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser)。

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](developing.md)を参照してください。

## ダイアログの設定 {#configure-dialog}

コンテンツ作成者は、設定ダイアログを使用して個別のTeaserのプロパティを定義できます。また、選択した場合にTeaser画像を変更する [編集ダイアログ](#edit-dialog) もあります。

### 画像 {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **イメージアセット**
   * [アセットブラウザからアセットをドロップ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) するか、 **または参照** オプションをタップしてローカルファイルシステムからアップロードします。
   * 「 **クリア」** をタップまたはクリックして、現在選択されている画像を選択解除します。
   * **アセット** エディターでアセットのレンディションを [作成するには、「編集」を](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) タップまたはクリックします。

### テキスト {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **タイトル** Teaserのヘッドラインとして表示するタイトルを定義します。
* **リンクされたページ**からタイトルを取得するオンにすると、リンクされたページのタイトルがタイトルに入力されます。
* **説明**:
Teaserの下位見出しとして表示する説明を定義します。
* **リンクされたページ**から説明を取得するオンにすると、説明にリンクされたページの説明が入力されます。

### リンクとアクション {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **リンク**リンクがTeaserに適用されました。パスブラウザーを使用して、リンクターゲットを選択します。
* **「誘い文句（CTA:コールトゥアクション）を有効にする**」チェックボックスをオンにすると、誘い文句（CTA:コールトゥアクション）の定義が有効になります。リスト内の最初の誘い文句（CTA:コールトゥアクション）リンクが他のTeaser要素のリンクとして使用されます。

## ダイアログを編集 {#edit-dialog}

Teaserコンポーネントは画像レンダリングを [Image Componentに委任](image.md)します。そのため [、編集ダイアログ]（画像コンポーネントのimage. md# edit- dialog）を使用して、コンテンツ作成者がティーザー画像を操作できます。

## デザインダイアログ {#design-dialog}

デザインダイアログでは、テンプレート作成者がこのコンポーネントを使用するときにコンテンツ作成者によって割り当てられるTeaserオプションを定義できます。

### Teaserタブ {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **コールトゥアクション**
   * **コンテンツ作成者の誘い文句（CTA:コールトゥアクション****** ）オプションを非表示にする
* **要素**
   * **タイトルを非表示にする**
      * コンテンツ作成者の **タイトル** オプションを非表示にします
      * 選択した場合 **、タイトルタイプは非表示** になります
   * **Hide description**
Hide the **Description** option for content authors
* **タイトルタイプ** Teaserのタイトルで使用するHタグを定義します。
* **リンク**
   * **選択**した画像をリンクしない場合、Teaser画像はリンクされません
   * **タイトル**をリンクしない場合、Teaserのタイトルはリンクされません

### 「スタイル」タブ {#styles-tab}

Teaserコンポーネントは、AEM [スタイルシステムをサポート](authoring.md#component-styling)しています。
