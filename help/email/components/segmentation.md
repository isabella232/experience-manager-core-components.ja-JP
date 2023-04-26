---
title: メールセグメント化コンポーネント
description: メールセグメント化コンポーネント
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---


# メールセグメント化コンポーネント {#email-segmentation-component}

メールセグメント化コンポーネントでは、Adobe Campaign の変数を使用して、コンテンツの受信者に基づいてコンテンツの表示と非表示を切り替えます。

## 使用方法 {#usage}

メールセグメント化コンポーネントを使用すると、Adobe Campaign から提供される、受信者に関する変数が満たす条件に基づいて、コンテンツ作成者がコンテンツの表示と非表示を切り替えることができます。このようにして、セグメント化に基づいてコンテンツが受信者に表示されます。

* テンプレート作成者は、[デザインダイアログ](#design-dialog)を使用して、セグメントとして追加できるコンポーネントを定義できます。
* コンテンツ作成者は[設定ダイアログ](#configure-dialog)を使用して、コンポーネントをセグメントとして追加し、表示するセグメントを Adobe Campaign 変数に基づいて設定することができます。

設定ダイアログを使用する代わりに、メールセグメント化コンポーネントをコンテンツページに追加したら、コンテンツ作成者は、追加のコンポーネントをメールセグメント化コンポーネントにドラッグ＆ドロップして新しいセグメントを作成することもできます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、メールセグメント化コンポーネントの現在のバージョン（2022年10月にメールコアコンポーネントのリリース x で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | - |

### 技術的詳細 {#technical-details}

メールティーザーコンポーネントに関する最新の技術ドキュメントについては、[GitHub を参照](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)してください。

コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けドキュメント](/help/developing/overview.md)を参照してください。

## 設定ダイアログ {#configure-dialog}

編集ダイアログでは、コンテンツ作成者がセグメントの作成、名前変更、並べ替えを行ったり、アクティブなセグメントを定義したりできます。メールセグメント化コンポーネントでは、セグメントは、コンテンツの受信者が満たす条件に基づいて表示／非表示が切り替わる別のコンポーネントにすぎません。これを[コアコンポーネントタブコンポーネント](/help/components/tabs.md)になぞらえることができますが、セグメント化コンポーネントでは、条件が満たされるタブのコンテンツのみが表示されます。

### 「項目」タブ {#items-tab}

![メールセグメント化コンポーネントの設定ダイアログの「項目」タブ](/help/email/assets/email-segmentation-configure-items.png)

「**セグメントを追加**」ボタンを使用してコンポーネントセレクターを開くと、セグメントとして追加するコンポーネントを選択できます。追加が完了すると、以下の要素を含んだエントリがリストに追加されます。

* **アイコン** - セグメントのコンポーネントタイプのアイコンで、リスト内で識別しやすくするためのものです。マウスポインターを置くと、完全なコンポーネント名がツールチップとして表示されます。
* **条件** - このセグメントがコンテンツの受信者に表示されるために満たする必要がある条件。
   * 使用可能な条件は、[デザインダイアログ](#design-dialog)で定義されます。
   * **デフォルト** - 他の条件を満たさない場合に表示するデフォルトのセグメントを定義します
   * **カスタム** - 条件を作成者が定義できるようにします
      * 条件は、Adobe Campaign のパーソナライゼーション変数に基づきます
      * [Adobe Campaign Standard のパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?lang=ja)
      * [Adobe Campaign Classic のパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=ja)
* **削除** - タップまたはクリックすると、メールセグメント化コンポーネントからセグメントを削除できます。
* **並べ替え** - タップまたはクリックしてドラッグすると、セグメントを並べ替えることができます。

>[!TIP]
>
>コンテンツのビューポートを縮小して編集ダイアログが全画面表示になるようにすると、「**追加**」ボタンが非表示になります。[コンポーネントブラウザーからコンテンツエディターのメールセグメント化コンポーネントにドラッグ＆ドロップ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=ja#inserting-a-component)することで、コンポーネントをメールセグメント化コンポーネントに追加することはできます。

### 「プロパティ」タブ {#properties-tab}

![メールセグメント化コンポーネントの設定ダイアログの「プロパティ」タブ](/help/email/assets/email-segmentation-configure-properties.png)

* **ID** - このオプションを使用すると、HTML 内のコンポーネントの一意の ID を制御できます。
   * これを空白のままにした場合、一意の ID が自動的に生成されます。生成された ID は結果のページを調べることで確認できます。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS に影響を与える可能性があります。

### 「アクセシビリティ」タブ {#accessibility-tab}

![メールセグメント化コンポーネントの設定ダイアログの「アクセシビリティ」タブ](/help/email/assets/email-segmentation-configure-accessibility.png)

「**アクセシビリティ**」タブでは、コンポーネントの「[ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)」ラベルの値を設定できます。

* **ラベル** - コンポーネントの ARIA ラベル属性の値

### 「スタイル」タブ {#styles-tab-edit}

メールセグメント化コンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

ドロップダウンを使用して、コンポーネントに適用するスタイルを選択します。編集ダイアログでの選択項目は、コンポーネントツールバーから選択した項目と同じ効果があります。

このタブを使用するには、[デザインダイアログ](#design-dialog)でこのコンポーネントのスタイルを設定する必要があります。

## パネルを選択 {#select-panel}

コンポーネントツールバーの「**パネルを選択**」オプションを使用すれば、コンテンツの作成者は、編集用に別のセグメントに切り替えたり、簡単にセグメントを並べ替えたりできます。

![「パネルを選択」アイコン](/help/email/assets/select-panel-icon.png)

コンポーネントツールバーの「**パネルを選択**」オプションを選択すると、設定済みのセグメントがドロップダウンとして表示されます。

* リスト内のセグメントは割り当てられた順序で並べられ、その順番が通し番号に反映されます。
* まずセグメントのコンポーネントタイプが表示され、次にセグメントの説明が薄いフォントで表示されます。

![「パネルを選択」ポップオーバー](/help/email/assets/select-panel-popover.png)

* ドロップダウン内の 1 つのエントリをタップまたはクリックすると、エディターのビューがそのセグメントに切り替わります。
* ドラッグハンドルを使用すれば、セグメントをインプレースで並べ替えることができます。

>[!NOTE]
>
>セグメントはページエディター内のタブとしてレンダリングされ、最終的なコンテンツに対して複数のオプションがあることを示します。作成者がページエディター内でこれらのタブを選択することはできません。選択パネルを使用すると、表示するセグメントを切り替えることができます。

## デザインダイアログ {#design-dialog}

デザインダイアログでは、テンプレート作成者が、メールセグメント化コンポーネントにセグメントとして追加できるコンポーネントを定義したり、コンテンツ作成者が利用できるカスタムスタイルを定義したりできます。

### 「許可されたコンポーネント」タブ {#allowed-components-tab}

「**許可されたコンポーネント**」タブでは、コンテンツ作成者がメールセグメント化コンポーネントにセグメントとして追加できるコンポーネントを定義できます。

「**許可されたコンポーネント**」タブは、[テンプレートエディターでレイアウトコンテナのポリシーやプロパティを定義する](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)際の同じ名前のタブと同じように機能します。

### 「スタイル」タブ {#styles-tab}

メールセグメント化コンポーネントでは、AEM [スタイルシステム](/help/get-started/authoring.md#component-styling)をサポートしています。

### 「定義済み条件」タブ {#defined-conditions}

「**定義済み条件**」タブを使用すると、テンプレートエディターで、セグメントの作成時にコンテンツ作成者が選択できる条件を定義できます。

![デザインダイアログの「定義済み条件」タブ](/help/email/assets/email-segmentation-design-defined-conditions.png)

「**追加**」ボタンをタップまたはクリックすると、新しい条件を作成できます。

* **セグメント条件名** - 条件の説明
* **セグメント条件** - Adobe Campaign のパーソナライゼーション変数に基づいて、満たす必要がある実際の条件
   * [Adobe Campaign Standard のパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?lang=ja)
   * [Adobe Campaign Classic のパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/
* **削除** - タップしてクリックすると、条件を削除できます
* **並べ替え** - タップまたはクリックしてドラッグすると、順序を並べ替えることができます
