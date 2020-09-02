---
title: Slingのコンテキスト対応設定とコアコンポーネント
description: コアコンポーネントは、特定の機能に対してSlingのコンテキスト対応設定を利用します
translation-type: tm+mt
source-git-commit: 24a810ff634f8846881dfa0095e879476d0f16f0
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 12%

---


# Slingのコンテキスト対応設定とコアコンポーネント {#sling-context-aware-configurations}

コンテキスト対応設定はSlingの機能で、コンテンツリソースまたはリソースツリーに関連し、コアコンポーネントでサイト全体の設定を可能にするために利用される設定です。

## Slingコンテキスト対応設定 {#context-aware-configurations}

サイトに必要な設定は、例えば、一部のコンテキストーが共有される場合に、ネストされたパラメーターとグローバルなフォールバック値の継承が必要になる場合など、サイトの地域ごとに異なる場合があります。 Slingコンテキスト対応の設定で、これを有効にします。

Slingのコンテキスト対応設定の詳細については、Apacheのドキュメントを [参照してください。](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)

## Use in the Core Components {#core-components}

多くのコアコンポーネント機能は、コンテキストに応じた設定を利用します。 このような設定はすべて次のノードにあります。

* `/conf/<my-site>/sling:configs/<my-configuration>`

個々の設定は、特定のコンポーネントまたは機能に依存します。 コンテキスト対応設定を使用するコアコンポーネントの機能は次のとおりです。

* [PDF ビューアコンポーネント](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe Client Data Layer](/help/developing/data-layer/overview.md#installation-activation)
* [AMP のサポート](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
