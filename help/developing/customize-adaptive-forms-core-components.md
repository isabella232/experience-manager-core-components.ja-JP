---
title: アダプティブFormsコアコンポーネントのカスタマイズ
description: 組織に合わせてカスタマイズされた機能を実装するための、アダプティブFormsコアコンポーネントの拡張または作成について説明します。
role: Architect, Developer, Admin
source-git-commit: 9a80b453d6a6cf7b347128654d3b5e673a063505
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 4%

---


# アダプティブFormsコアコンポーネントのカスタマイズ

アダプティブFormsコアコンポーネントのカスタマイズを使用すると、既製の機能を特定のニーズに合わせてカスタマイズできます。 このガイドでは、これらのコンポーネントをカスタマイズして、よりパーソナライズされたエクスペリエンスを作成するプロセスについて説明します。

## 前提条件

アダプティブFormsコアコンポーネントのカスタマイズを開始する前に、

* 詳しくは、 [コアコンポーネントのアーキテクチャ](customizing.md#customizing-the-markup-customizing-the-markup) そして [公式のAdobe Experience Managerコアコンポーネントドキュメント](customizing.md). これらの包括的なリソースは、カスタマイズプロセス全体を通じてガイドとして機能します。
* 開発環境の設定コアコンポーネントをスムーズに変更できるワークフローを実現します。 開発環境を設定する際に、最新のAEMアーキタイププロジェクトに基づくAEMアーキタイププロジェクトを使用します。 環境に応じて、次の操作を実行できます。

   * [Forms as a Cloud Serviceのローカル開発環境の設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html).
   * [AEM 6.5 Formsのローカル開発環境の設定](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=ja)

## アダプティブFormsコアコンポーネントのカスタマイズ

アダプティブFormsコアコンポーネントの外観、動作、機能を変更するには、以下の手順に従います。

1. **コアコンポーネントの識別と複製**

   開発環境を設定する際に、アーキタイプベースのプロジェクトを作成しました。 AEMアーキタイププロジェクトで、カスタマイズする特定のコアコンポーネントを特定します。 特定されたら、AEMアーキタイプベースのプロジェクト内でコンポーネントの複製を作成します。 他のアダプティブFormsコアコンポーネントと並行して使用します。 この手順により、カスタマイズ作業が元のコンポーネントに影響を与えないようにし、自由に試すことができます。

1. **コピーしたコンポーネントをカスタマイズする**

   複製したコンポーネントを開き、必要に応じて必要な変更を加えます。

   * **構造をカスタマイズHTML**：デザインニーズに合わせてHTML構造を調整し、 [BEM（ブロック要素修飾子）](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions) メンテナンス可能でスケーラブルなコードのスタイル設定方法。
   * **ラベルを更新**：カスタマイズされたバージョンのわかりやすい名前を指定するために、コンポーネントのラベルを更新します。 提供されたを参照します。 [OOTB（標準）ラベルテンプレート](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html) 一貫性を保つために。
   * **ウィジェットをカスタマイズ**：コンポーネント内で使用されるウィジェット（ドロップダウン、チェックボックス）を、特定のユースケースに合わせて調整します。 詳しくは、 [サンプルウィジェット実装](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html) 参照用。
   * **ヘルプテキストとツールチップ**：コンポーネントに関連付けられたヘルプテキストやツールチップをパーソナライズして、コンテキストやガイダンスをユーザーに提供します。 以下を使用します。 [OOTB ヘルプテキストテンプレート](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html) を出発点として使用します。
   * **データ属性**：必要なすべてのデータ属性をコンポーネントのHTML要素に組み込みます。 これらの属性は、実行時にコンポーネントを適切に機能させるために非常に重要です。 詳しくは、 [ドキュメント](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput) を参照して、アダプティブFormsコアコンポーネントでのデータ属性の役割を理解してください。

1. **バックエンドロジックの実装**

   カスタマイズにバックエンドのロジックが必要な場合は、既存の Sling モデルを拡張できます。 提供されたを参照します。 [例](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java) 必要な機能をカスタマイズされたコンポーネントにシームレスに統合できます。

1. **コンポーネントのダイアログの設定**

   カスタマイズしたコンポーネントに関連付けられたダイアログを設定します。 例を使用 [コンポーネントダイアログ](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml) ユーザーの操作と設定を適切に管理するために、ドキュメントに記載されています。

1. **コンポーネントをローカル開発環境にデプロイおよびテストする**

   用途 [maven でコンポーネントをビルドおよびデプロイします。](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html#building-and-installing) をローカル開発環境で使用します。 コンポーネントをデプロイした後、アダプティブフォームを作成してカスタムコンポーネントをテストします。

1. **実稼動環境にカスタムコンポーネントをデプロイする**

   ローカル開発環境でコンポーネントをテストした後、実稼動環境にコンポーネントをデプロイします。

