---
title: タブコンポーネント
description: タブコンポーネントを使用すれば、複数のタブを作成してページ上のコンテンツを整理できます。
translation-type: ht
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: ht
source-wordcount: '1027'
ht-degree: 100%

---


# タブコンポーネント {#tabs-component}

コアコンポーネントのタブコンポーネントを使用すれば、コンテンツを複数のタブ上に配置できます。

## 使用方法 {#usage}

タブコンポーネントを使用すれば、コンテンツ作成者はコンテンツを複数のタブ内に配置できます。

[編集ダイアログ](#edit-dialog)では、コンテンツ作成者が、複数のタブを定義したりアクティブなタブを設定したりできます。[デザインダイアログ](#design-dialog)を使用すれば、テンプレート作成者は、タブに追加できるコンポーネントを定義したり、スタイルをカスタマイズしたりできます。

>[!TIP]
>
>ネストされたタブコンポーネント（タブ内のタブ）はサポートされています。
>
>[コンテンツツリー](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)を使用した特定や選択は、単純な（ネストされていない）タブコンポーネントでは可能ですが、ネストされたタブでは不可能です。

## パネルへのディープリンク {#deep-linking}

タブと[アコーディオンコンポーネント](accordion.md)は、コンポーネント内のパネルに直接リンクする機能をサポートしています。

次の手順を実行します。

1. ページエディターで「**[公開されているとおりに表示](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**」オプションを使用して、ページとコンポーネントを表示します。
1. ページのコンテンツを調べ、パネルの ID を特定します。
   * 例：`id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID がアンカーになり、ハッシュ（`#`）を使用して URL に追加できます。
   * 例：`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

パネル ID をアンカーとして使用して指定した URL に移動すると、ブラウザーは特定のコンポーネントまで直接スクロールし、指定したパネルを表示します。デフォルトでパネルが展開されないように設定されている場合は、自動的に展開されます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、タブコンポーネントの現在のバージョン（2018 年 10 月にコアコンポーネントのリリース 2.2.0 で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)を参照してください。

## コンポーネント出力のサンプル {#sample-component-output}

タブコンポーネントを体験したり、その設定オプションの例や、HTML 出力や JSON 出力の例を確認したりするには、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_tabs_jp)を参照してください。

### 技術的詳細 {#technical-details}

タブコンポーネントに関する最新の技術ドキュメントについては、[GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1_jp) を参照してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 編集ダイアログ{#edit-dialog}

編集ダイアログでは、コンテンツ作成者がタブの作成、名前変更、並べ替えをおこなったり、アクティブなタブを定義したりできます。

### 「項目」タブ {#items-tab}

![タブコンポーネントの編集ダイアログの「項目」タブ](/help/assets/tabs-edit-items.png)

タブとして追加するコンポーネントを選択するためのコンポーネントセレクターを開くには、「**追加**」ボタンを使用します。追加が完了すると、以下の列を含むエントリがリストに追加されます。

* **アイコン** - リスト内で簡単に識別できるようにするための、タブのコンポーネントタイプのアイコン。マウスポインターを置くと、完全なコンポーネント名がツールチップとして表示されます。
* **説明** - タブのテキストとして使用される説明。デフォルトでは、タブ用に選択されたコンポーネントの名前に設定されます。
* **削除** - タップまたはクリックすると、タブコンポーネントからタブが削除されます。
* **再配置** - タップまたはクリックしてドラッグすると、タブの順序を並べ替えることができます。

>[!TIP]
>
>ページのビューポートが縮小されて編集ダイアログがフルスクリーンになる場合、「**追加**」ボタンが非表示になります。[コンポーネントブラウザーからページエディターのタブコンポーネントにドラッグ＆ドロップ](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)することで、コンポーネントをタブコンポーネントに追加できます。

### 「プロパティ」タブ {#properties-tab}

![タブコンポーネントの編集ダイアログの「プロパティ」タブ](/help/assets/tabs-edit-properties.png)

* 「**アクティブな項目**」タブでは、コンテンツ作成者はページの読み込み時にアクティブになるタブを定義できます。
   * 「**デフォルト**」オプションの場合、最初のタブが選択されます。
* **ID** - このオプションを使用すると、HTML 内および [データレイヤー](/help/developing/data-layer/overview.md)内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS、JS、およびデータレイヤーのトラッキングに影響を与える可能性があります。

### 「アクセシビリティ」タブ {#accessibility-tab}

![タブコンポーネントの編集ダイアログの「アクセシビリティ」タブ](/help/assets/tabs-edit-accessibility.png)

「**アクセシビリティ**」タブでは、コンポーネントの「[ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)」ラベルの値を設定できます。

* **ラベル** - コンポーネントの ARIA ラベル属性の値

## パネルを選択{#select-panel}

コンポーネントツールバーの「**パネルを選択**」オプションを使用すれば、コンテンツ作成者は編集用に別のパネルに切り替えたり、簡単にタブを並べ替えたりできます。

![「パネルを選択」アイコン](/help/assets/select-panel-icon.png)

コンポーネントツールバーの「**パネルを選択**」オプションを選択すると、設定済みのタブがドロップダウンとして表示されます。

* リスト内のタブは割り当てられた順番で並べられ、その順番が通し番号に反映されます。
* まずタブのコンポーネントタイプが表示され、次にタブの説明が明るい色のフォントで表示されます。

![「パネルを選択」ポップオーバー](/help/assets/select-panel-popover.png)

* ドロップダウン内の 1 つのエントリをタップまたはクリックすると、エディターのビューがそのタブに切り替わります。
* ドラッグハンドルを使用すれば、タブをインプレースで並べ替えることができます。

>[!NOTE]
>
>**編集**&#x200B;モードでは、作成者がタブを選択することはできません。公開されているコンテンツを読者と同じ立場でタブを操作するには、**[](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)プレビュー**&#x200B;モードまたは「**[公開されているとおりに表示](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**」オプションを使用します。

## デザインダイアログ{#design-dialog}

デザインダイアログでは、テンプレート作成者が、タブコンポーネントに項目として追加できるコンポーネントを定義したり、コンテンツ作成者が利用できるカスタムスタイルを定義したりできます。

### 「許可されるコンポーネント」タブ {#allowed-components-tab}

「**許可されるコンポーネント**」タブでは、コンテンツ作成者がタブコンポーネントに項目として追加できるコンポーネントを定義できます。

「許可されるコンポーネント」タブは、[テンプレートエディターでレイアウトコンテナのポリシーやプロパティを定義する](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/templates.html)際の同じ名前のタブと同じように機能します。

### 「スタイル」タブ {#styles-tab}

タブコンポーネントは AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートします。
