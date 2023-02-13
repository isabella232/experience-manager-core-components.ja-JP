---
title: AEM Adaptive Formsコアコンポーネントの概要
description: アダプティブFormsコアコンポーネントの柔軟性を利用して、魅力的な登録エクスペリエンス（フォーム）を作成し、Adobe Experience Managerの機能を活用して提供します。
role: Architect, Developer, Admin, User
source-git-commit: b378fbd5695f82b8fc9de3a2d53a8387099ae33b
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 13%

---


# アダプティブFormsコアコンポーネントの概要 {#adaptive-forms-core-components-introduction}

Adobe Experience ManagerのアダプティブFormsコアコンポーネントを使用すると、使用可能な柔軟性とカスタマイズオプションを利用して、魅力的な登録エクスペリエンスを作成できます。

## コアコンポーネント  {#overview}

Adobe Experience Manager(AEM) では、コンポーネントは、ページやフォームの作成に使用される構築ブロックです。 作成者がコンテンツを作成および管理するためのシンプルで強力な方法を提供すると同時に、開発者には、カスタムコンポーネントの作成に必要な柔軟性と拡張性も提供します。 これらは、Web サイトやフォームの開発時間を短縮し、メンテナンスコストを削減するように設計されており、柔軟性が高く、Web サイトやフォームの特定のニーズに合わせて容易にカスタマイズできます。

また、コアコンポーネントは、レスポンシブに設計され、デスクトップ、タブレット、スマートフォンなど様々なデバイスをサポートします。 また、最新の Web 標準とベストプラクティスに準拠し、Web コンテンツを作成するための堅牢で信頼性の高いソリューションです。

全体的に、コアコンポーネントはAEMで Web コンテンツを作成および管理するための不可欠なツールで、開発時間と保守コストの削減に役立ち、Web サイト訪問者に優れたユーザーエクスペリエンスを提供します。

## アダプティブFormsコアコンポーネント

アダプティブFormsコアコンポーネントは、Adobe Experience Manager WCM コアコンポーネントの基盤上に構築された、24 のオープンソースの BEM 準拠コンポーネントのセットです。 これらは、アダプティブFormsの作成に使用するように特別に設計されています。アダプティブフォームとは、ユーザーのデバイス、ブラウザー、画面サイズに応じたフォームです。

これらのコンポーネントは、テキストフィールド、チェックボックス、ドロップダウンメニューなど、様々なフォームフィールドオプションを提供することで、例外的なデータ取得および登録エクスペリエンスを作成するために使用できます。 また、検証、条件付きロジック、レスポンシブデザインなどの機能も含まれ、使いやすく使いやすいフォームを作成するのに使用できます。

さらに、これらのコンポーネントはオープンソースなので、開発者は、組織の特定のニーズに合わせてコンポーネントを簡単にカスタマイズおよび拡張できます。 また、これらのコンポーネントは、拡張性と保守性を確保する BEM 手法に基づいて構築されます。

![](assets/sample-adaptive-form.png)

## 機能 {#features}

|  |  |
|---|---|
| 本番で使用可能 | アダプティブFormsコアコンポーネントは、24 個の堅牢な WCM コンポーネントです。 |
| クラウド対応 | 使用可能  [AEM Formsas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| 用途が広い | コンポーネントは、Forms作成者がほとんどあらゆるレイアウトを組み立てることができる汎用概念を表します。 |
| 設定可能 | テンプレートレベル [コンテンツポリシー](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html?lang=ja#content-policies) 使用できるフィーチャと使用できないフィーチャを定義します。 |
| 高いアクセシビリティ | ARIA ラベルを提供し、キーボードナビゲーション ([既知の問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle))、および支援テクノロジー用のテキスト（スクリーンリーダーなど）。 |
| テーマテーブル | コンポーネントは[スタイルシステム](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=ja)を実装し、マークアップは [BEM CSS の命名規則](https://getbem.com/)に従っています。 |
| カスタマイズ可能 | いくつかのパターンが用意されているので、HTML の調整から高度な機能の再利用まで、カスタマイズが容易になっています。 |
| バージョン管理 | [バージョン管理ポリシー](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)が設定されているので、影響を受ける可能性のある改善の際にも、コアコンポーネントが原因でサイトが機能しなくなることはありません。 |
| オープンソース | 何か問題がある場合は、改善案を寄稿します。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## メリット {#benefits}

データキャプチャのエクスペリエンスは、リードの生成と登録にとって重要です。アダプティブFormsコアコンポーネントは、データキャプチャ用に最適化されたフォームを作成するための強力なソリューションです。 コアコンポーネントを使用して、基盤コンポーネントを介してこれらのエクスペリエンスを作成する理由には、次のようなものがあります。

* **GitHub での入手可否と包括的なドキュメント**:AEMアダプティブFormsコアコンポーネントはオープンソースで、GitHub で利用できます。詳細なドキュメントも用意されています。 これにより、開発者はコンポーネントとその動作を理解し、開発に貢献することが容易になります。 この [aemcomponents.dev](https://www.aemcomponents.dev/) web サイトはまた、開発者がコンポーネントの動作を確認し、詳細なドキュメントにアクセスできる、貴重なリソースです。

* **スタイル設定の BEM モデル**:コアコンポーネントは、スタイル設定に BEM（ブロック要素修飾子）モデルに従います。BEM は、CSS を整理するための、広く使用されている確立された手法です。 これにより、開発者はスタイルの編成方法と、特定のニーズに合わせてスタイルを変更する方法を理解しやすくなります。

* **サードパーティライブラリとの依存なし**:コアコンポーネントの利点の 1 つは、JQuery や Underscore など、サードパーティの JavaScript ライブラリに依存しない点です。 これにより、コンポーネントの処理が高速で軽量になり、既存のAEM実装に統合しやすくなります。

* **パフォーマンスとアクセシビリティに重点を置く**:コアコンポーネントは、パフォーマンスとアクセシビリティを考慮して構築され、Google Lighthouse の高いスコアと Web 仮想スコアに反映されます。 これにより、開発者はアクセシブルでパフォーマンスの高い Web ページを容易に作成できます。これは、現在のデジタル環境でますます重要になっています。

* **Sites 30 のテンプレートおよびテーマのフォームコンポーネント**:コアコンポーネントは、Sites 30 のテンプレートおよびテーマでフォームコンポーネントをサポートし、AEM内でフォームを簡単に作成およびカスタマイズできるようにします。

* **スタイル設定が容易**:コアコンポーネントは、基盤コンポーネントとは異なり、スタイル設定が容易です。 テーマの作成プロセスは Sites に似ていますが、同じテーマ/CSS を親の Sites ページから継承できます。 さらに、スタイル設定の BEM モデルを使用すると、スタイルを理解および変更しやすくなります。

* **アクセシビリティ**:アダプティブFormsコアコンポーネントは、障碍のあるユーザー（スクリーンリーダーなどの支援テクノロジーを使用しているユーザーを含む）がフォームを確実に使用できるように、アクセシビリティ標準およびガイドラインをサポートしています


<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->



## 要件 {#requirements}

アダプティブFormsコアコンポーネントには、次の要件があります。

| AEM | AEM Formsアドオン | コアコンポーネント |
|---|---|---|
| AEM as a Cloud Service | Forms - デジタル登録 | [リリース 2.20.8](/help/versions.md)+ |


## アダプティブFormsコアコンポーネント {#components}

以下を使用できます。 [アダプティブFormsエディター](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) コアコンポーネントを作成するために、アダプティブFormsをベースにします。 アダプティブFormsコアコンポーネントの現在のバージョンでは、次のコンポーネントを使用できます。

* アコーディオン
* ボタン
* チェックボックス グループ
* 日付選択
* ドロップダウンリスト
* 電子メール入力
* フォームコンテナ
* ファイル添付
* フッター
* ヘッダー
* 水平タブ
* 画像
* 数値入力
* パネルコンテナー
* ラジオボタン
* リセットボタン
* 送信ボタン
* 電話入力
* テキスト入力
* テキスト
* タイトル
* ウィザード

