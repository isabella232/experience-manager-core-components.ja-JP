---
title: アダプティブフォームのコアコンポーネントのカスタマイズ
description: 組織に合わせて調整された機能を実装するための、アダプティブフォームのコアコンポーネントの拡張または作成について説明します。
role: Architect, Developer, Admin
source-git-commit: 9a80b453d6a6cf7b347128654d3b5e673a063505
workflow-type: ht
source-wordcount: '707'
ht-degree: 100%

---


# アダプティブフォームのコアコンポーネントのカスタマイズ

アダプティブフォームのコアコンポーネントをカスタマイズすると、標準機能を特定のニーズに合わせてカスタマイズできます。このガイドでは、これらのコンポーネントをカスタマイズして、よりパーソナライズされたエクスペリエンスを作成するプロセスについて説明します。

## 前提条件

アダプティブフォームのコアコンポーネントのカスタマイズを開始する前に、

* [コアコンポーネントのアーキテクチャ](customizing.md#customizing-the-markup-customizing-the-markup)について学びます。詳しくは、[Adobe Experience Manager コアコンポーネントの公式ドキュメント](customizing.md)を参照してください。これらの包括的なリソースは、カスタマイズプロセス全体を通じてガイドとして機能します。
* 開発環境を設定します。これにより、コアコンポーネントを変更する際のワークフローがスムーズになります。開発環境を設定する際は、最新の AEM アーキタイププロジェクトに基づく AEM アーキタイププロジェクトを使用します。環境に応じて、次の操作を実行できます。

   * [Forms as a Cloud Service 用のローカル開発環境の設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?lang=ja)
   * [AEM 6.5 Forms 用のローカル開発環境を設定](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=ja)

## アダプティブフォームのコアコンポーネントをカスタマイズ

アダプティブフォームのコアコンポーネントの外観、動作、機能を変更するには、次の手順に従います。

1. **コアコンポーネントを識別して複製**

   開発環境を設定する際に、アーキタイプベースのプロジェクトを作成しました。AEMアーキタイププロジェクトで、カスタマイズする特定のコアコンポーネントを識別します。識別したら、AEM アーキタイプベースのプロジェクト内にコンポーネントの複製を作成します。 他のアダプティブフォームのコアコンポーネントと並行して保持します。この手順により、カスタマイズ作業が元のコンポーネントに影響を与えず、自由に実験できるようになります。

1. **コピーしたコンポーネントをカスタマイズ**

   複製したコンポーネントを開き、要件に従って必要な変更を開始します。

   * **HTML 構造をカスタマイズ**：保守可能でスケーラブルなコードを実現するための [BEM（ブロック要素修飾子）](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions)スタイルのプラクティスを遵守しながら、デザインのニーズに合わせて HTML 構造を調整します。
   * **ラベルを更新**：コンポーネントのラベルを更新して、カスタマイズしたバージョンに明確でわかりやすい名前を付けます。一貫性を保つために、提供されている [OOTB（標準）ラベルテンプレート](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html)を参照してください。
   * **ウィジェットをカスタマイズ**：コンポーネント内で使用するウィジェット（ドロップダウン、チェックボックス）を調整して、特定のユースケースに合わせます。詳しくは、[サンプルウィジェット実装](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html)を参照してください。
   * **ヘルプテキストとツールチップ**：コンポーネントに関連付けられたヘルプテキストやツールチップをパーソナライズして、コンテキストやガイダンスをユーザーに提供します。開始点として [OOTB ヘルプテキストテンプレート](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html)を使用します。
   * **データ属性**：必要なすべてのデータ属性をコンポーネントの HTML 要素内に組み込みます。これらの属性は、実行時にコンポーネントを適切に機能させるために重要です。アダプティブフォームのコアコンポーネントのデータ属性の役割を理解するには、[ドキュメント](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput)を参照してください。

1. **バックエンドロジックを実装**

   カスタマイズにバックエンドロジックが必要な場合は、既存の Sling モデルを拡張できます。提供されている[例](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java)を参照して、必要な機能をカスタマイズされたコンポーネントにシームレスに統合します。

1. **コンポーネントのダイアログを設定**

   カスタマイズしたコンポーネントに関連付けられたダイアログを設定します。ドキュメントで提供されているサンプル[コンポーネントダイアログ](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml)を使用して、ユーザーの操作と設定が適切に管理されていることを確認します。

1. **ローカル開発環境でコンポーネントをデプロイしてテスト**

   ローカル開発環境で [Maven を使用してコンポーネントをビルドおよびデプロイ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=ja#building-and-installing)します。コンポーネントをデプロイしたら、アダプティブフォームを作成してカスタムコンポーネントをテストします。

1. **実稼動環境でカスタムコンポーネントをデプロイ**

   ローカル開発環境でコンポーネントをテストしたら、実稼動環境にコンポーネントをデプロイします。

