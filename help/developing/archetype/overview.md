---
title: AEM プロジェクトアーキタイプ
description: AEMベースのアプリケーションのテンプレートとして機能するAEMプロジェクトアーキタイプについて説明します。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 8940285f4c5e5870b6a135dac674f06e4c1d8b5a
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 56%

---


# AEM プロジェクトアーキタイプ {#aem-project-archetype}

AEMプロジェクトアーキタイプは、Web サイトの出発点として、ベストプラクティスに基づく最小限のAdobe Experience Manager(AEM) プロジェクトを作成する Maven テンプレートです。 このドキュメントでは、アーキタイプの利点の概要と一般的な使用方法を説明します。 技術的な手順とドキュメントの詳細については、アーキタイプ GitHub リポジトリを参照してください。

>[!TIP]
>
>最新のAEMプロジェクトアーキタイプと関連する技術ドキュメント [は GitHub にあります。](https://github.com/adobe/aem-project-archetype)

## アーキタイプを使用する理由 {#why-use-the-archetype}

AEM プロジェクトのアーキタイプを使用すると、数回のキー操作で、ベストプラクティスベースの AEM プロジェクトを構築するためのパスが設定されます。アーキタイプを使用すると、すべての要素が配置され、結果として生成されるプロジェクトを最小限に抑えながら、AEM の[主要機能](/help/developing/archetype/using.md#what-you-get)すべてが実装されることになります。これにより、必要な作業はその上に構築して拡張するだけとなります。

もちろん、 [成功したAEMプロジェクト](/help/developing/success.md) ただし、AEMプロジェクトアーキタイプの使用は健全な基盤であり、任意のAEMプロジェクトで強くお勧めします。

## 機能 {#features}

* **ベストプラクティス：**&#x200B;アドビの最新の推奨プラクティスをすべて活用して、サイトをブートストラップできます。
* **ローコード（低コード）：**&#x200B;テンプレートの編集、コンテンツの作成、CSS のデプロイを行うと、サイトの運用開始準備が整います。
* **クラウド対応：**&#x200B;必要に応じて、[AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja) を使用して、数日以内に運用を開始でき、スケーラビリティとメンテナンスの向上を図れます。
* **Dispatcher：**&#x200B;プロジェクトには、速度とセキュリティを確実に達成できる [Dispatcher 設定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=ja)が必要です。
* **マルチサイト：**&#x200B;必要に応じて、[マルチ言語およびマルチリージョンセットアップ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html?lang=ja)用のコンテンツ構造がアーキタイプから生成されます。
* **コアコンポーネント：**&#x200B;作成者は、アドビの汎用の[標準コンポーネントセット](/help/introduction.md)を使用して、ほぼどのようなレイアウトでも作成できます。
* **編集可能なテンプレート：**&#x200B;ほとんどすべての[テンプレートをコードなしで](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html?lang=ja)組み立てることができ、作成者による編集が可能な範囲を定義できます。
* **レスポンシブレイアウト：**&#x200B;テンプレートまたは個々のページで、定義されたブレークポイントについて[要素がどのようにリフローするかを定義](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=ja)できます。
* **ヘッダーとフッター：** [コンポーネントのローカライゼーション機能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=ja)を使用して、コードなしで組み立ててローカライズできます。
* **スタイルシステム：**&#x200B;作成者が[様々なスタイルを適用](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html?lang=ja)できるようにすることで、カスタムコンポーネントを作成しないようにすることができます。
* **フロントエンドビルド：** フロントエンド開発者は、次のことができます。 [AEMページのモック作成とクライアントライブラリの作成](front-end.md) Webpack、TypeScript、SASS を含んでいます。
* **Web アプリ対応：** React またはAngularを使用するサイトの場合、 [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html?lang=ja) 保持する [アプリのコンテキスト内オーサリング](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=ja).
* **コマースに対応：**[AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html?lang=ja)を [Magento](https://magento.com/jp) などのコマースソリューションと統合するプロジェクトの場合は、[Commerce コアコンポーネント](https://github.com/adobe/aem-core-cif-components)を使用します。
* **コード例：** HelloWorld コンポーネントのほか、サンプルのモデル、サーブレット、フィルター、スケジューラーをチェックアウトできます。
* **オープンソース：**&#x200B;何か問題がある場合は、改善案を[寄稿](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md)できます。

## 参考情報 {#further-reading}

* **[AEM Project Archetype GitHub](https://github.com/adobe/aem-project-archetype)**  — アーキタイプの完全な使用方法と技術的な詳細については、
* **[アーキタイプの使用](using.md)**  — プロジェクトでのアーキタイプの使用方法と、生成される結果のモジュールの概要
* **[AEMプロジェクトアーキタイプを使用したフロントエンド開発](front-end.md)**  — アーキタイプのフロントエンドモジュールの使用方法
* **次のチュートリアルは、アーキタイプに基づいています。**
   * **[WKND サイト](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=ja)**  — 新しい Web サイトを開始する方法を説明します。
   * **[WKND シングルページアプリ](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=ja)** - AEMで完全にオーサリング可能な React またはAngularWeb アプリを構築する方法を説明します。
