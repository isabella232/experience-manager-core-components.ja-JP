---
title: 統合とAdobeクライアントデータレイヤー
description: Adobeクライアントデータレイヤーがカスタムコンポーネントと統合する方法、およびAdobe AnalyticsやAdobe Targetとの統合がWebサイトに対する洞察を得る方法について説明します。
translation-type: tm+mt
source-git-commit: ea7a0e08ea1b769b400fce275c8ce7e0db6f9407
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 53%

---


# Adobe Client Data Layer との統合 {#integrations}

Adobe Client Data Layer は、あらゆるスクリプトのあらゆる種類のデータを表示およびアクセスできる標準化された方法を提供し、Web サイトを測定する際の手間を軽減します。

Adobeクライアントデータレイヤーは、カスタムコンポーネントと統合でき、Adobe AnalyticsおよびAdobe Targetとの統合によって、Webサイトに対する洞察を得ることができます。

## カスタムコンポーネント用のデータレイヤーの有効化 {#enabling-custom-components}

カスタムコンポーネントをデータレイヤーに自動的に追加するには：

1. 追跡する必要があるカスタムコンポーネントモデルのプロパティを定義します。
1. カス追加タムコンポーネントのHTLの属性。 `data-cmp-data-layer` E.g. `data-cmp-data-layer="${mycomponent.data.json}"`.

カスタムコンポーネントの特定の要素をクリックするたびに、データレイヤーが `cmp:click` イベントを自動的にトリガーするようにするには、カスタムコンポーネントのHTLで追跡する要素に `data-cmp-clickable` 属性を追加します。

この `data-cmp-data-layer-enabled` 属性をクエリーして、クライアント側でデータレイヤーが有効かどうかを確認できます。

>[!TIP]
>
>Adobeクライアントデータレイヤーとコアコンポーネントの統合の技術的な詳細、およびカスタムコンポーネントでデータレイヤーを有効にする方法については、コアコンポーネントリポジトリの [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) ファイルを参照してください。

## Adobe Analytics、Adobe Targetとの統合 {#analytics-target}

Adobe Analytics や Adobe Target との組み合わせることで、Adobe Client Data Layer は非常に強力で柔軟なツールセットの基盤となり、デジタルエクスペリエンスのインサイトを獲得することができます。次のチュートリアルでは、サンプル統合の手順を説明します。

### Adobe Analytics でページデータを収集 {#collect-page-data}

Adobe Client Data Layer の組み込み機能と AEM コアコンポーネントを使用して、Adobe Experience Manager Sites のページに関するデータを収集する方法を説明します。Experience Platform Launch と Adobe Analytics 拡張は、ルールを作成して Adobe Analytics にページデータを送信するために使用されます。

[こちらでチュートリアルをご覧ください。](https://docs.adobe.com/content/help/jp/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### Adobe Analytics を使用してクリックされたコンポーネントを追跡 {#track-clicked-components}

イベント駆動型 Adobe Client Data Layer を AEM コアコンポーネントと共に使用して、Adobe Experience Manager サイト上にある特定のコンポーネントのクリックを追跡します。Experience Platform Launch でルールを使用して、クリックイベントをリッスンし、コンポーネントでフィルタリングして、リンクのトラックビーコンと共にデータを Adobe Analytics に送信する方法について説明します。

[こちらでチュートリアルをご覧ください。](https://docs.adobe.com/content/help/jp/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
