---
title: 統合と Adobe Client Data Layer
description: Adobe Client Data Layer とカスタムコンポーネントの統合方法のほか、Adobe Analytics や Adobe Target との統合が Web サイトに対するインサイトの取得にどう役に立つかを説明します。
feature: コアコンポーネント、Adobe Client Data Layer
role: Architect, Developer, Administrator
exl-id: 503dd3dc-fe95-4a17-83f5-1f0c1960993d
translation-type: ht
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: ht
source-wordcount: '422'
ht-degree: 100%

---

# Adobe Client Data Layer との統合 {#integrations}

Adobe Client Data Layer は、あらゆるスクリプトのあらゆる種類のデータを表示およびアクセスできる標準化された方法を提供し、Web サイトを測定する際の手間を軽減します。

Adobe Client Data Layer はカスタムコンポーネントと統合でき、Web サイトに対するインサイトを取得するうえで Adobe Analytics や Adobe Target との統合が役に立ちます。

## カスタムコンポーネントへのデータレイヤーの有効化 {#enabling-custom-components}

カスタムコンポーネントをデータレイヤーに自動的に追加するには：

1. 追跡する必要があるカスタムコンポーネントモデルのプロパティを定義します。
1. カスタムコンポーネントの HTL に `data-cmp-data-layer` 属性を追加します。例：`data-cmp-data-layer="${mycomponent.data.json}"`

カスタムコンポーネントの特定の要素がクリックされるたびにデータレイヤーに `cmp:click` イベントを自動的にトリガーさせるには、カスタムコンポーネントの HTL で追跡の対象となる要素に `data-cmp-clickable` 属性を追加します。

`data-cmp-data-layer-enabled` 属性をクライアント側で照会して、データレイヤーが有効かどうかを確認できます。

>[!TIP]
>
>Adobe Client Data Layer とコアコンポーネントの統合に関する技術的な詳細と、カスタムコンポーネントでデータレイヤーを有効にする方法については、コアコンポーネントリポジトリの [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) ファイルを参照してください。

## Adobe Analytics や Adobe Target との統合 {#analytics-target}

Adobe Analytics や Adobe Target との組み合わせることで、Adobe Client Data Layer は非常に強力で柔軟なツールセットの基盤となり、デジタルエクスペリエンスのインサイトを獲得することができます。次のチュートリアルでは、サンプル統合の手順を説明します。

### Adobe Analytics でページデータを収集 {#collect-page-data}

Adobe Client Data Layer の組み込み機能と AEM コアコンポーネントを使用して、Adobe Experience Manager Sites のページに関するデータを収集する方法を説明します。Experience Platform Launch と Adobe Analytics 拡張は、ルールを作成して Adobe Analytics にページデータを送信するために使用されます。

[こちらでチュートリアルをご覧ください。](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### Adobe Analytics を使用してクリックされたコンポーネントを追跡 {#track-clicked-components}

イベント駆動型 Adobe Client Data Layer を AEM コアコンポーネントと共に使用して、Adobe Experience Manager サイト上にある特定のコンポーネントのクリックを追跡します。Experience Platform Launch でルールを使用して、クリックイベントをリッスンし、コンポーネントでフィルタリングして、リンクのトラックビーコンと共にデータを Adobe Analytics に送信する方法について説明します。

[こちらでチュートリアルをご覧ください。](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
