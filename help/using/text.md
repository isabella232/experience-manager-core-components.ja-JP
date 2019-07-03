---
title: テキストコンポーネント
seo-title: テキストコンポーネント
description: テキストコンポーネントは、インプレース編集機能を備えたリッチテキスト編集と構成コンポーネントです。
seo-description: テキストコンポーネントは、インプレース編集機能を備えたリッチテキスト編集と構成コンポーネントです。
uuid: 5f8eee8f-7317-4712- a77f- e34e8a024187
contentOwner: User
content-type: リファレンス
topic-tags: コアコンポーネント
discoiquuid: 9a290584-565e-4392-999c-999ee4a93da1
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# テキストコンポーネント{#text-component}

コアコンポーネントテキストコンポーネントは、インプレース編集機能を備えたリッチテキスト編集と構成コンポーネントです。

## 使用 {#usage}

テキストコンポーネントには堅牢なリッチテキストエディターが用意されています。これにより、シンプルなインラインエディターやフルスクリーン形式で簡単にテキスト編集を行うことができます。

[編集ダイアログ](#edit-dialog) 機能の編集ダイアログ機能には、フルスクリーン編集ダイアログで利用できる機能が制限されています。[デザインダイアログ](#design-dialog)を使用すると、コンテンツ作成者のテンプレート用に、見出し、特殊文字、段落スタイルなどのテキスト書式オプションを設定できます。

## Version and Compatibility {#version-and-compatibility}

テキストコンポーネントの現在のバージョンはv2であり、2018年1月のコアコンポーネントのリリース2.0.0で導入されています。このドキュメントで説明しています。

次の表に、サポートされているコンポーネントのすべてのバージョン、コンポーネントのバージョンが互換性があるAEMバージョン、および以前のバージョンのドキュメントへのリンクを示します。

| コンポーネントバージョン | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | 互換性 | 互換性 | 互換性 |
| [v1](text-v1.md) | 互換性 | 互換性 | 互換性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Text Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/text.html).

### Technical Details {#technical-details}

The latest technical documentation about the Text Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## The Text Component and the Rich Text Editor {#the-text-component-and-the-rich-text-editor}

コアコンポーネントテキストコンポーネントでは、AEMリッチテキストエディター（RTE）を利用します。RTEは、テキストコンテンツを編集するために幅広い機能を備えたコンテンツ作成者を提供します。RTEは設定で非常に柔軟性があり、数多くのオプションを提供しています。Further details about how the RTE can be configured can be found in the articles [Configure the Rich Text Editor](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/rich-text-editor.html) and [Configure the Rich Text Editor plug-ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

この記事の残りの部分では、標準コンポーネントテキストコンポーネントの標準設定を標準のRTE設定で示しています。

>[!NOTE]
>
>Only options enabled by [UI configurations of the RTE](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-5/sites/administering/using/rich-text-editor.html) are available by in the Text Component.

## Edit Dialog {#edit-dialog}

編集ダイアログには、ユーザーがテキストを構成することが予想される標準のリッチテキスト書式ツールが用意されています。

![](assets/screen_shot_2018-01-11at143025.png)

### 太字

![](assets/screen_shot_2018-01-11at125602.png)

選択したテキストに太字書式を適用したり、カーソルの後に入力したテキスト形式を太字で適用したりするために使用します。

**Ctrl+ B** はキーボードショートカットとして使用できます。

### 斜体

![](assets/screen_shot_2018-01-11at125609.png)

選択したテキストに斜体書式を適用したり、カーソルの後に入力したテキストを斜体で適用したりするために使用します。

**Ctrl+ I** キーをキーボードショートカットとして使用できます。

### 下線

![](assets/screen_shot_2018-01-11at125615.png)

カーソルの後に入力したテキストまたは下線のテキストに下線付きの書式設定を適用するために使用します。

**Ctrl+ U** はキーボードショートカットとして使用できます。

### 下付き文字

![](assets/screen_shot_2018-01-11at125703.png)

カーソルの後に入力したテキストまたはテキストの書式設定に使用します。

### 上付き文字

![](assets/screen_shot_2018-01-11at125708.png)

カーソルの後に入力したテキストまたはテキストの書式設定に使用します。

### テキストとして貼り付け

![](assets/screen_shot_2018-01-11at125713.png)

コピーしたテキストを書式設定なしでプレーンテキストとして貼り付けます。

このオプションを選択すると、テキストがテキストに挿入される前に、プレビューとしてテキストを貼り付けることができるプレーンテキストとして、ウィンドウが開きます。チェックマークをタップまたはクリックして受け入れ、xをタップまたはクリックしてキャンセルします。

![](assets/screen_shot_2018-01-11at143234.png)

### Word から貼り付け

![](assets/screen_shot_2018-01-11at125717.png)

このオプションを選択すると、テキストがテキストに挿入される前に、テキストの書式設定をプレビューとして保持するウィンドウが開きます。チェックマークをタップまたはクリックして受け入れ、xをタップまたはクリックしてキャンセルします。

![](assets/screen_shot_2018-01-11at143250.png)

### ハイパーリンク

![](assets/screen_shot_2018-01-11at125839.png)

このオプションを使用して、選択したテキストをハイパーリンクに変換したり、既に定義済みのリンクを変更したりします。このオプションは、テキストが既に選択されていて、リンクを設定するための追加オプションがあるウィンドウを開く場合にのみ有効です。

![](assets/screen_shot_2018-01-11at130003.png)

* 場所を入力
   * Select Selectionダイアログを使用してAEMでパスを選択する
   * リンクがAEM内にない場合は、絶対URLを入力します（絶対パスはAEMに対する相対パスと解釈されます）。
* リンクの代替説明テキストを入力します
* リンクの動作の選択
   * Target
   * 同じタブ
   * 新しいタブ
   * 親フレーム
   * トップフレーム
   または、チェックマークをタップまたはクリックして、リンクまたはxをキャンセルします。

### リンク解除

![](assets/screen_shot_2018-01-11at125901.png)

選択したテキストに既に適用されているリンクを削除するには、このオプションを使用します。このオプションは、リンクが既に選択されている場合にのみ有効です。

### 検索

![](assets/screen_shot_2018-01-11at125906.png)

指定したテキスト文字列のオカレンスを検索するには、このオプションを使用します。このオプションを選択すると、検索オプションを指定するウィンドウが開きます。

![](assets/screen_shot_2018-01-11at130107.png)

Enter the text for which you want to search and tap or click **Find** to begin the search. &quot;x&quot;をタップまたはクリックしてキャンセルします。
If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.
一致が見つかった場合、ハイライト表示され、検索ダイアログが淡色表示になります。Tap or click the **Find** button again in the dimmed dialog to search for the next occurrence.

![](assets/screen_shot_2018-01-11at130145.png)

追加の回数が見つからない場合は、メッセージが表示され、テキストの先頭から検索が再開されます。

![](assets/screen_shot_2018-01-11at130241.png)

### Replace

![](assets/screen_shot_2018-01-11at125910.png)

このオプションを使用して、指定したテキスト文字列のテキストを検索し、一致を別の文字列と置換します。このオプションを選択すると、検索および置換オプションを指定するウィンドウが開きます。

![](assets/screen_shot_2018-01-11at130441.png)

検索するテキストと、置換するテキストを入力します。

Tap or click **Find** to begin the search. &quot;x&quot;をクリックまたはタップしてキャンセルします。

If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.

一致が見つかった場合、ハイライト表示され、検索ダイアログが淡色表示になります。Click the **Find** button again in the dimmed dialog to search for the next occurrence or select the **Replace** button to replace the highlighted, matched text. **「置換** 」ボタンは、一致が作成されるとアクティブになります。

Select **Replace all** to replace all occurrences of the text at once.

### テキストを左揃え

![](assets/screen_shot_2018-01-11at142012.png)

テキストを左マージンに揃えます。

### テキストを中央揃え

![](assets/screen_shot_2018-01-11at142017.png)

テキストの中央揃えに使用します。

### テキストを右揃え

![](assets/screen_shot_2018-01-11at142021.png)

テキストを右マージンに揃えます。

### ビュレット

![](assets/screen_shot_2018-01-11at142025.png)

選択したテキストをバレットリストとしてフォーマットするか、カーソルの後にバレットリストを挿入するために使用します。

To end a bulleted list, tap or click the **Bullet** button again or enter two carriage returns.

### 番号付き

![](assets/screen_shot_2018-01-11at142030.png)

選択したテキストを番号付きリストとして書式設定するか、カーソルの後に番号付きリストを挿入するために使用します。

To end a numbered list, tap or click the **Numbered** button again or enter two carriage returns.

### アウトデント

![](assets/screen_shot_2018-01-11at141917.png)

カーソルの後に入力したテキストまたはテキストのインデントレベルを減らすために使用します。

選択したテキストまたはカーソルの位置が既にインデントされている場合のみアクティブです。

### インデント

![](assets/screen_shot_2018-01-11at141922.png)

カーソルの後に入力したテキストまたはテキストのインデントレベルを上げるために使用します。

### テーブル

![](assets/screen_shot_2018-01-11at141928.png)

テキストにテーブルを挿入するために使用します。このオプションを選択すると、テーブルの詳細を指定するウィンドウが開きます。

![](assets/screen_shot_2018-01-11at142405.png)

* **列** テーブルの列数（必須）
* **行** テーブルの行数（必須）
* **幅** テーブルの幅
* **高さ** テーブルの高さ
* **セルパディング** セルコンテンツの周囲のスペース
* **セル間隔** セル間のスペース
* **テーブル** の境界線線の太さ
* テーブルのヘッダーの場合:
   * 最初の行は、
   * 最初の列は、
   * 最初の行と最初の列は、
   * または、ヘッダーを使用しないでください。
* **キャプション** テーブルのキャプション

### スペルチェック

![](assets/screen_shot_2018-01-11at141935.png)

テキストコンテンツのスペルをチェックするために使用します。スペルミスのあるスペルには、改行された赤い線が引かれています。

Further details about spell checking and customizing spell check dictionaries can be found in the document [Configure the Rich Text Editor Plug-Ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

### Special Characters {#special-characters}

![](assets/screen_shot_2018-01-11at142600.png)

テキストに特殊文字を挿入するために使用します。このオプションを選択すると、使用可能な文字が表示されるウィンドウが開きます。

![](assets/screen_shot_2018-01-11at142635.png)

目的の文字をタップまたはクリックして、カーソルの後のテキストに挿入します。複数文字を挿入できます。&quot;x&quot;をタップまたはクリックして選択ウィンドウを閉じます。

### ソースの編集

![](assets/screen_shot_2018-01-11at142746.png)

テキストのHTMLソースを表示および変更するために使用します。

**ソース編集** アイコンをタップまたはクリックして、書式化されたビューからテキストの内容を変更し、生のHTMLを表示します。このモードでは、その他の書式設定オプションはすべて無効になっています。**ソース編集** アイコンをタップまたはクリックして、形式設定されたビューに戻ります。

>[!CAUTION]
>
>As always the case with access to raw HTML, care must be exercised when using the **Source Edit** option!
>
>HTML entered via **Source Edit** is scanned for XSS risks and any scripts that are inserted are removed and will not appear on the resulting page. **ただし、ソース編集** で入力されたHTMLの形式が正しくない場合、ページのテンプレートが破損し、予期しない書式設定や結果ページのレンダリングができなくなります。

>[!NOTE]
>
>**ソース編集** によって入力されたHTMLはXSSのリスクとスクリプトをスキャンして自動的に削除されるので、実際に保存されたコンテンツは、ソース編集に **入力された内容と異なる可能** 性があります。For this reason, in order to save changes made using **Source Edit**, you must first exit **Source Edit** to view the text in the normal editor before saving.

### 段落書式

![](assets/screen_shot_2018-01-11at142752.png)

選択したテキストまたはカーソルの後に挿入されるテキストに段落書式を適用するために使用します。このオプションを選択すると、段落形式を選択したドロップダウンが開きます。

![](assets/screen_shot_2018-01-11at142828.png)

テキストコンポーネントはインラインでも編集できますが、スペース制限により、すべての書式設定オプションがインラインで使用できるわけではありません。すべてのオプションを表示するには、フルスクリーンモードに切り替えます。

![](assets/screen_shot_2018-01-11at142921.png)

## Design Dialog {#design-dialog}

デザインダイアログでは、テンプレート作成者がコンテンツ作成者が使用できるテキスト書式オプションを定義できます。

### Plugins Tab {#plugins-tab}

「プラグイン」タブを使用して、コンテンツ作成者が使用できる様々なテキスト書式オプションを有効または無効にします。

### 機能 {#features}

![](assets/chlimage_1-28.png)

コンポーネントの次の機能をアクティブ化または非アクティブ化できます。

* プレーンテキストを貼り付け
* 過去の単語
* 検索と置換
* スペルチェッカー
* ソース編集

### 書式設定 {#formatting}

![](assets/chlimage_1-29.png)

コンポーネントの次の形式設定オプションをアクティブ化または非アクティブ化できます。

* テーブル
* リスト
* 整列
* 太字、斜体、下線
* リンク
* サブスクリプト/上付き文字

### 段落スタイル {#paragraph-styles}

![](assets/chlimage_1-30.png)

コンポーネントの段落スタイルをアクティブ化または非アクティブ化できます。アクティベートすると、許可されている形式を定義できます。

* Tap or click the **Add** button to insert a new style.
* 編集ダイアログに表示するスタイルと説明のコードを入力します。
* To remove a style tap or click the **Delete** button.
* 形式の順序を並べ替えるには、をタップまたはクリックしてハンドルをドラッグします。

### Configuring Special Characters {#configuring-special-characters}

![](assets/chlimage_1-31.png)

特殊文字を挿入するオプションは、コンポーネントのアクティブ化または非アクティブ化できます。アクティブ化すると、許可されている文字を定義できます。

* Tap or click the **Add** button to insert a new character.
* 編集ダイアログに表示する文字のHTMLコードと説明を入力します。
* To remove a character tap or click the **Delete** button.
* 文字の順序を並べ替えるには、タップまたはクリックしてハンドルをドラッグします。

## Styles Tab {#styles-tab}

The Text Component supports the AEM [style system](authoring.md#component-styling).