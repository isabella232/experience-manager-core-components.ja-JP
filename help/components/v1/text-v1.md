---
title: テキストコンポーネント（v1）
description: テキストコンポーネントは、インプレース編集機能を備えたリッチテキスト編集および作成用コンポーネントです。
index: n
role: 設計者、開発者、管理者、業務担当者
translation-type: ht
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: ht
source-wordcount: '1662'
ht-degree: 100%

---


# テキストコンポーネント（v1） {#text-component-v}

テキストコンポーネントは、インプレース編集機能を備えたリッチテキスト編集および作成用コンポーネントです。

## 使用方法 {#usage}

テキストコンポーネントは、シンプルなインラインエディターでもフルスクリーン形式でも容易にテキスト編集をおこなえる堅牢なリッチテキストエディターを提供します。

[編集ダイアログ](#edit-dialog)には、限定的なオプションのみのインライン編集機能と、すべての機能を利用できるフルスクリーン編集機能が用意されています。[デザインダイアログ](#design-dialog)では、見出し、特殊文字、段落スタイルなどのテキスト書式設定オプションをコンテンツ作成者のテンプレートに設定できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、AEM 6.3 に付属しているコアコンポーネントのリリース 1.0.0 で最初に導入されたテキストコンポーネント v1 について説明します。

テキストコンポーネント v1 の互換性を次の表に示します。

| AEM のバージョン | テキストコンポーネント v1 |
|--- |--- |
| 6.3 | 互換性あり |
| 6.4 | 互換性あり |

>[!CAUTION]
>
>このドキュメントでは、テキストコンポーネント v1 について説明します。
>
>テキストコンポーネントの現在のバージョンについて詳しくは、[テキストコンポーネント](/help/components/text.md)のドキュメントを参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

以下は [We.Retail](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html) から取得したサンプルです。

### スクリーンショット {#screenshot}

![](/help/assets/chlimage_1-27.png)

### HTML {#html}

```
<div class="cmp cmp-text aem-GridColumn aem-GridColumn--default--12">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.<br />
</p>
</div>
```

### JSON {#json}

```
"text": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "text": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.</p>\n",
              "richText": true,
              ":type": "weretail/components/content/text"
            }
```

>[!NOTE]
>
>コアコンポーネントからの JSON エクスポートには、コアコンポーネントのリリース 1.1.0 が必要です。詳しくは、[コアコンポーネント v1 の互換性情報](/help/versions.md)を参照してください。

## 編集ダイアログ {#edit-dialog}

編集ダイアログには、テキストの作成を支援する標準のリッチテキスト書式設定ツールが用意されています。

![](/help/assets/chlimage_1-52.png)

* 太字

   ![](/help/assets/chlimage_1-53.png)

   選択したテキストに太字書式を適用したり、カーソルの後に入力したテキストに太字書式を設定したりするために使用します。

   **Ctrl + B** をキーボードショートカットとして使用できます。

* 斜体

   ![](/help/assets/chlimage_1-54.png)

   選択したテキストに斜体書式を適用したり、カーソルの後に入力したテキストに斜体書式を設定したりするために使用します。

   **Ctrl + I** をキーボードショートカットとして使用できます。

* 下線

   ![](/help/assets/chlimage_1-55.png)

   選択したテキストに下線書式を適用したり、カーソルの後に入力したテキストに下線書式を設定したりするために使用します。

   **Ctrl + U** をキーボードショートカットとして使用できます。

* 下付き文字

   ![](/help/assets/chlimage_1-56.png)

   選択したテキストまたはカーソルの後に入力したテキストを下付き文字として書式設定するために使用します。

* 上付き文字

   ![](/help/assets/chlimage_1-57.png)

   選択したテキストまたはカーソルの後に入力したテキストを上付き文字として書式設定するために使用します。

* テキストとして貼り付け

   ![](/help/assets/chlimage_1-58.png)

   コピーしたテキストを書式設定のないプレーンテキストとして貼り付けます。

   このオプションを選択すると、ウィンドウが開き、テキストを書式設定のないプレーンテキストとして貼り付けた状態を、実際に挿入する前にプレビューできます。続行する場合はチェックマークをタップまたはクリックし、キャンセルする場合は「x」をタップまたはクリックします。

   ![](/help/assets/chlimage_1-59.png)

* Word から貼り付け

   ![](/help/assets/chlimage_1-60.png)

   このオプションを選択すると、ウィンドウが開き、書式設定を維持しながらテキストを貼り付けた状態を、実際に挿入する前にプレビューできます。続行する場合はチェックマークをタップまたはクリックし、キャンセルする場合は「x」をタップまたはクリックします。

   ![](/help/assets/chlimage_1-61.png)

* ハイパーリンク

   ![](/help/assets/chlimage_1-62.png)

   このオプションを使用すれば、選択したテキストをハイパーリンクに変換したり、定義済みのリンクを変更したりできます。このオプションは、テキストが既に選択されている場合にのみ有効で、選択すると、リンクを設定するための追加オプションのウィンドウが開きます。

   ![](/help/assets/chlimage_1-63.png)

   * 場所を入力します

      * 「選択ダイアログを開く」を使用して、AEM 内のパスを選択します
      * リンクが AEM 内にない場合は、絶対 URL を入力します（絶対パス以外のパスは AEM に対する相対パスと解釈されます）
   * リンクの説明用代替テキストを入力します
   * リンクの動作を選択します

      * ターゲット
      * 同じタブ
      * 新しいタブ
      * 親フレーム
      * トップフレーム

   リンクを適用する場合はチェックマークをタップまたはクリックし、キャンセルする場合は「x」をタップまたはクリックします。

* リンク解除

   ![](/help/assets/chlimage_1-64.png)

   選択したテキストに既に適用されているリンクを削除する場合は、このオプションを使用します。このオプションは、リンクが既に選択されている場合にのみ有効です。

* 検索

   ![](/help/assets/chlimage_1-65.png)

   指定した文字列をテキスト内で検索する場合は、このオプションを使用します。このオプションを選択すると、検索オプションを指定するためのウィンドウが開きます。

   ![](/help/assets/chlimage_1-66.png)

   検索するテキストを入力し、「**検索**」をタップまたはクリックして検索を開始します。キャンセルする場合は、「x」をクリックまたはタップします。

   大文字と小文字を区別して完全一致検索をおこなう場合は、「**大文字小文字を区別して一致**」オプションを選択してから検索を開始します。

   一致する文字列が見つかった場合は、それが強調表示され、検索ダイアログが淡色表示になります。一致する次の文字列を検索するには、淡色表示のダイアログで「**検索**」ボタンを再度タップまたはクリックします。

   ![](/help/assets/chlimage_1-67.png)

   一致する文字列がそれ以上見つからない場合は、メッセージが表示され、テキストの先頭から検索が再開されます。

   ![](/help/assets/chlimage_1-68.png)

* 置換

   ![](/help/assets/chlimage_1-69.png)

   指定した文字列をテキスト内で検索し、一致する文字列を別の文字列に置き換える場合は、このオプションを使用します。このオプションを選択すると、検索および置換オプションを指定するためのウィンドウが開きます。

   ![](/help/assets/chlimage_1-70.png)

   検索する文字列と置換後の文字列を入力します。

   検索を開始するには、「**検索**」をタップまたはクリックします。キャンセルする場合は、「x」をタップまたはクリックします。

   大文字と小文字を区別して完全一致検索をおこなう場合は、「**大文字小文字を区別して一致**」オプションを選択してから検索を開始します。

   一致する文字列が見つかった場合は、それが強調表示され、検索ダイアログが淡色表示になります。一致する次の文字列を検索するには、淡色表示のダイアログで「**検索**」ボタンを再度タップまたはクリックします。強調表示されている一致文字列を置き換えるには、「**置換**」ボタンをタップまたはクリックします。なお、「**置換**」ボタンは、一致する文字列が見つかった場合にのみ有効になります。

   「**すべてを置換**」をタップまたはクリックすると、一致するすべての文字列が一度に置換されます。

* テキストを左揃え

   ![](/help/assets/chlimage_1-71.png)

   テキストを左マージンに揃えます。

* テキストを中央揃え

   ![](/help/assets/chlimage_1-72.png)

   テキストを中央に揃えます。

* テキストを右揃え

   ![](/help/assets/chlimage_1-73.png)

   テキストを右マージンに揃えます。

* 箇条書き

   ![](/help/assets/chlimage_1-74.png)

   選択したテキストを箇条書きリストとして書式設定するか、カーソルの後に箇条書きリストを挿入するために使用します。

   箇条書きリストを終了するには、「**箇条書き**」ボタンをタップまたはクリックするか、キャリッジリターンを 2 回入力します。

* 番号付き

   ![](/help/assets/chlimage_1-75.png)

   選択したテキストを番号付きリストとして書式設定するか、カーソルの後に番号付きリストを挿入するために使用します。

   番号付きリストを終了するには、「**番号付き**」ボタンをタップまたはクリックするか、キャリッジリターンを 2 回入力します。

* アウトデント

   ![](/help/assets/chlimage_1-76.png)

   選択したテキストまたはカーソルの後に入力するテキストのインデントレベルを減らすために使用します。

   選択したテキストまたはカーソルの位置が既にインデントされている場合にのみ有効です。

* インデント

   ![](/help/assets/chlimage_1-77.png)

   選択したテキストまたはカーソルの後に入力するテキストのインデントレベルを増やすために使用します。

* テーブル

   ![](/help/assets/chlimage_1-78.png)

   テキストにテーブルを挿入するために使用します。このオプションを選択すると、テーブルの詳細を指定するためのウィンドウが開きます。

   ![](/help/assets/chlimage_1-79.png)

   * **列** - テーブルの列数（必須）
   * **行** - テーブルの行数（必須）
   * **幅** - テーブルの幅
   * **高さ** - テーブルの高さ
   * **セル内の余白** - セルコンテンツの周囲の空白
   * **セルの間隔** - セル間の空白
   * **ボーダー** - テーブルの罫線の太さ
   * テーブルの見出しについては次の選択肢があります。

      * 最初の行を使用する
      * 最初の列を使用する
      * 最初の行と最初の列を使用する
      * 見出しを使用しない
   * **キャプション** - テーブルのキャプション


* スペルチェック

   ![](/help/assets/chlimage_1-80.png)

   テキストコンテンツのスペルをチェックするために使用します。スペルミスの可能性がある場合は、赤い破線が該当箇所の下に引かれます。

* 特殊文字

   ![](/help/assets/chlimage_1-81.png)

   テキストに特殊文字を挿入するために使用します。このオプションを選択するとウィンドウが開き、使用可能な文字が表示されます。

   ![](/help/assets/chlimage_1-82.png)

   目的の文字をタップまたはクリックすると、テキストのカーソルの後に文字が挿入されます。複数の文字を挿入できます。「x」をタップまたはクリックすると、選択ウィンドウが閉じます。

* ソース編集

   ![](/help/assets/chlimage_1-83.png)

   テキストの HTML ソースを表示および変更するために使用します。

   **ソース編集**&#x200B;アイコンをタップまたはクリックすると、テキストの内容が、書式設定された表示から HTML コードの表示に変わります。このモードでは、他の書式設定オプションはすべて無効になっています。**ソース編集**&#x200B;アイコンを再度タップまたはクリックすると、書式設定された表示に戻ります。

   >[!CAUTION]
   >
   >生の HTML コードにアクセスする場合は常にそうですが、「**ソース編集**」オプションを使用する際には注意する必要があります。
   >
   >
   >**ソース編集**&#x200B;で入力した HTML コードはスキャンされて、XSS のリスクがないか確認されます。スクリプトを挿入してもすべて削除され、生成されるページには出現しません。ただし、**ソース編集**&#x200B;で入力した HTML コードの形式が正しくない場合は、ページのテンプレートが破損して、予期しない書式設定になったり、生成されるページが使用できなくなるおそれがあります。

* 段落書式

   ![](/help/assets/chlimage_1-84.png)

   選択したテキストまたはカーソルの後に挿入されるテキストに段落書式を適用するために使用します。このオプションを選択すると、段落形式を選択するためのドロップダウンが開きます。

   ![](/help/assets/chlimage_1-85.png)

テキストコンポーネントはインラインでも編集できますが、スペースの制限により、必ずしもすべての書式設定オプションがインラインで使用できるわけではありません。すべてのオプションを表示するには、フルスクリーンモードに切り替えます。

![](/help/assets/chlimage_1-86.png)

## デザインダイアログ {#design-dialog}

デザインダイアログでは、コンテンツ作成者が使用できるテキスト書式設定オプションをテンプレート作成者が定義できます。

### 機能 {#features}

![](/help/assets/chlimage_1-28.png)

コンポーネントに対して次の機能を有効または無効にすることができます。

* プレーンテキストを貼り付け
* Word から貼り付け
* 検索と置換
* スペルチェッカー
* ソース編集

### 書式設定 {#formatting}

![](/help/assets/chlimage_1-29.png)

コンポーネントに対して次の書式設定オプションを有効または無効にすることができます。

* テーブル
* リスト
* 整列
* 太字、斜体、下線
* リンク
* 下付き／上付き文字

### 段落スタイル {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

コンポーネントに対して段落スタイルを有効または無効にすることができます。有効にすると、使用できる書式を定義できます。

* 「**追加**」ボタンをタップまたはクリックすると、新しいスタイルを挿入できます。
* スタイルのコードと、編集ダイアログに表示される説明を入力します。
* スタイルを削除するには、「**削除**」ボタンをタップまたはクリックします。
* 書式の順序を並べ替えるには、ハンドルをタップまたはクリックしてドラッグします。

### 特殊文字 {#special-characters}

![](/help/assets/chlimage_1-31.png)

コンポーネントに対して、特殊文字を挿入するオプションを有効または無効にすることができます。有効にすると、使用できる文字を定義できます。

* 「**追加**」ボタンをタップまたはクリックすると、新しい文字を挿入できます。
* 文字の HTML コードと、編集ダイアログに表示される説明を入力します。
* 文字を削除するには、「**削除**」ボタンをタップまたはクリックします。
* 文字の順序を並べ替えるには、ハンドルをタップまたはクリックしてドラッグします。

## 技術的詳細 {#technical-details}

テキストコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text) を参照してください。

コアコンポーネントプロジェクト全体を GitHub からダウンロードできます。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。
