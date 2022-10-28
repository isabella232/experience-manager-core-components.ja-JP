---
title: 電子メールセグメントコンポーネント
description: 電子メールのセグメント化コンポーネント
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 15%

---


# 電子メールセグメントコンポーネント {#email-segmentation-component}

電子メールセグメント化コンポーネントは、Adobe Campaignの変数を使用して、コンテンツの受信者に基づいてコンテンツの表示と非表示を切り替えます。

## 使用方法 {#usage}

電子メールセグメントコンポーネントを使用すると、Adobe Campaignが提供する受信者に関して変数が満たした条件に基づいて、コンテンツ作成者がコンテンツの表示と非表示を切り替えることができます。 この方法では、コンテンツの受信者に対し、セグメント化に基づいてコンテンツが表示されます。

* テンプレート作成者は、 [デザインダイアログ](#design-dialog) を使用して、セグメントとして追加できるコンポーネントを定義します。
* コンテンツ作成者は、 [設定ダイアログ](#configure-dialog) コンポーネントをセグメントとして追加し、Adobe Campaign変数に基づいて表示するセグメントを設定するには、次の手順を実行します。

設定ダイアログを使用する代わりに、コンテンツ作成者が電子メールセグメントコンポーネントをコンテンツページに追加したら、コンテンツ作成者は、追加のコンポーネントを電子メールセグメントコンポーネントにドラッグ&amp;ドロップして新しいセグメントを作成できます。

## バージョンと互換性 {#version-and-compatibility}

このドキュメントでは、電子メールセグメントコンポーネントの現在のバージョン（2022 年 10 月に電子メールコアコンポーネントのリリース x で導入された v1）について説明します。

コンポーネントのすべてのサポート対象バージョン、コンポーネントの各バージョンと互換性のある AEM バージョン、以前のバージョンのドキュメントへのリンクを次の表に示します。

| コンポーネントのバージョン | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 互換性あり | 互換性あり |

## コンポーネント出力のサンプル {#sample-component-output}

電子メールセグメントコンポーネントを実際に体験し、その設定オプションやHTMLおよび JSON 出力の例を確認するには、 [コンポーネントライブラリ。](https://adobe.com/go/aem_cmp_library_email_segmentation)

### 技術的詳細 {#technical-details}

電子メールティーザーコンポーネントに関する最新の技術ドキュメント [は GitHub にあります。](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメントです。](/help/developing/overview.md)

## 設定ダイアログ {#configure-dialog}

設定ダイアログでは、コンテンツ作成者がセグメントの作成、名前変更、並べ替えをおこなったり、アクティブなセグメントを定義したりできます。 電子メールセグメント化コンポーネントでは、セグメントは、コンテンツの受信者が満たした条件に基づいて非表示になる、または表示される、単なる別のコンポーネントです。 これを [「コアコンポーネント」タブコンポーネント](/help/components/tabs.md) ただし、セグメント化コンポーネントでは、条件が満たされたタブの内容のみが表示されます。

### 「項目」タブ {#items-tab}

![メールセグメントコンポーネントの設定ダイアログの「項目」タブ](/help/email/assets/email-segmentation-configure-items.png)

以下を使用： **セグメントを追加** ボタンをクリックして、セグメントとして追加するコンポーネントを選択するためのコンポーネントセレクターを開きます。 追加すると、次の要素を含むエントリがリストに追加されます。

* **アイコン**  — リスト内で識別しやすくするための、セグメントのコンポーネントタイプのアイコン。 マウスポインターを置くと、完全なコンポーネント名がツールチップとして表示されます。
* **条件**  — このセグメントがコンテンツの受信者に表示されるために満たされる必要がある条件。
   * 使用可能な条件は、 [デザインダイアログ。](#design-dialog)
   * **デフォルト**  — 他の条件を満たさない場合に表示するデフォルトのセグメントを定義します
   * **カスタム**  — 作成者が条件を定義できるようにします
      * 条件は、Adobe Campaignのパーソナライゼーション変数に基づきます
      * [Adobe Campaign Standardのパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [Adobe Campaign Classicのパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **削除**  — タップまたはクリックすると、電子メールセグメントコンポーネントからセグメントが削除されます。
* **並べ替え**  — タップまたはクリックしてドラッグすると、セグメントを並べ替えることができます。

>[!TIP]
>
>コンテンツのビューポートが縮小されて編集ダイアログがフルスクリーンになる場合、 **追加** ボタンが非表示になります。 コンポーネントは、引き続き、 [コンポーネントブラウザーからドラッグし、コンテンツエディターの E メールセグメントコンポーネントにドロップします。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=ja#inserting-a-component)

### 「プロパティ」タブ {#properties-tab}

![電子メールセグメントコンポーネントの設定ダイアログの「プロパティ」タブ](/help/email/assets/email-segmentation-configure-properties.png)

* **ID**  — このオプションを使用すると、HTML内のコンポーネントの一意の識別子を制御できます。
   * 空白のままにした場合、一意の ID が自動的に生成され、結果のコンテンツを調べることで見つかります。
   * ID を指定した場合、作者はその ID が一意であることを確認する必要があります。
   * ID を変更すると、CSS に影響を与える可能性があります。

### 「アクセシビリティ」タブ {#accessibility-tab}

![電子メールセグメントコンポーネントの設定ダイアログの「アクセシビリティ」タブ](/help/email/assets/email-segmentation-configure-accessibility.png)

「**アクセシビリティ**」タブでは、コンポーネントの「[ARIA アクセシビリティ](https://www.w3.org/WAI/standards-guidelines/aria/)」ラベルの値を設定できます。

* **ラベル** - コンポーネントの ARIA ラベル属性の値

### 「スタイル」タブ {#styles-tab-edit}

電子メールセグメントコンポーネントは、AEM [スタイルシステム。](/help/get-started/authoring.md#component-styling)

ドロップダウンを使用して、コンポーネントに適用するスタイルを選択します。編集ダイアログでの選択項目は、コンポーネントツールバーから選択した項目と同じ効果があります。

スタイルは、内のこのコンポーネントに対して設定する必要があります [デザインダイアログ](#design-dialog) 」をクリックします。

## パネルを選択 {#select-panel}

コンテンツ作成者は、 **パネルを選択** 」オプションを使用すると、セグメントを簡単に並べ替えることができます。

![「パネルを選択」アイコン](/help/email/assets/select-panel-icon.png)

選択後、 **パネルを選択** オプションがコンポーネントツールバーに表示されると、設定済みのセグメントがドロップダウンとして表示されます。

* リスト内のセグメントは割り当てられた順番で並べられ、その順番が通し番号に反映されます。
* 最初にセグメントのコンポーネントタイプが表示され、次にセグメントの説明が薄いフォントで表示されます。

![「パネルを選択」ポップオーバー](/help/email/assets/select-panel-popover.png)

* ドロップダウン内の 1 つのエントリをタップまたはクリックすると、エディターのビューがそのセグメントに切り替わります。
* ドラッグハンドルを使用すると、セグメントをインプレースで並べ替えることができます。

>[!NOTE]
>
>セグメントはページエディター内のタブとしてレンダリングされ、最終的なコンテンツに対して複数のオプションがあることを示します。 作成者がページエディター内でこれらのタブを選択することはできません。 選択パネルを使用して、表示するセグメントを切り替えます。

## デザインダイアログ {#design-dialog}

デザインダイアログでは、テンプレート作成者が、E メールセグメント化コンポーネントにセグメントとして追加できるコンポーネントを定義したり、コンテンツ作成者が使用できるカスタムスタイルを定義したりできます。

### 「許可されるコンポーネント」タブ {#allowed-components-tab}

この **許可されたコンポーネント** 「 」タブでは、コンテンツ作成者が電子メールセグメントコンポーネントにセグメントとして追加できるコンポーネントを定義できます。

この **許可されたコンポーネント** タブは、 [テンプレートエディターでのレイアウトコンテナのポリシーとプロパティの定義](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=ja)

### 「スタイル」タブ {#styles-tab}

電子メールセグメントコンポーネントは、AEM [スタイルシステム。](/help/get-started/authoring.md#component-styling)

### 「定義済み条件」タブ {#defined-conditions}

の使用 **定義済みの条件** 「 」タブでは、テンプレートエディターで、セグメントの作成時にコンテンツ作成者が選択できる条件を定義できます。

![[ デザイン ] ダイアログ [ 定義された条件 ] タブ](/help/email/assets/email-segmentation-design-defined-conditions.png)

をタップまたはクリックします。 **追加** ボタンをクリックして新しい条件を作成します。

* **セグメント条件名**  — 条件の説明
* **セグメント条件** - Adobe Campaignのパーソナライゼーション変数に基づいて、満たす必要がある実際の条件
   * [Adobe Campaign Standardのパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [Adobe Campaign Classicのパーソナライゼーションリソースについては、こちらを参照してください。](https://experienceleague.adobe.com/docs/)
* **削除**  — クリックして条件を削除
* **並べ替え**  — タップまたはクリックしてドラッグすると、条件を並べ替えることができます
