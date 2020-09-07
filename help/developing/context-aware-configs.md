---
title: Sling のコンテキスト対応設定とコアコンポーネント
description: コアコンポーネントは、特定の機能で、Sling のコンテキスト対応設定を利用します
translation-type: ht
source-git-commit: 24a810ff634f8846881dfa0095e879476d0f16f0
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---


# Sling のコンテキスト対応設定とコアコンポーネント {#sling-context-aware-configurations}

コンテキスト対応設定は Sling の機能です。この機能はコンテンツリソースまたはリソースツリーに関連し、コアコンポーネントでサイト全体の設定を可能にするために利用されます。

## Sling のコンテキスト対応設定 {#context-aware-configurations}

サイトの地域が異なると、異なる設定が必要となることがあります。例えば、一部のパラメーターが共有される場合、ネストされたコンテキストとグローバルなフォールバック値の継承が必要になる場合があります。Sling コンテキスト対応設定で、これを有効にします。

Sling のコンテキスト対応設定の詳細については、[Apache のドキュメントを参照](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)してください。

## コアコンポーネントでの使用 {#core-components}

多くのコアコンポーネント機能は、コンテキスト対応設定を利用します。これらの設定はすべて次のノードにあります。

* `/conf/<my-site>/sling:configs/<my-configuration>`

個々の設定は、特定のコンポーネントまたは機能に依存します。コンテキスト対応設定を使用するコアコンポーネントの機能は次のとおりです。

* [PDF ビューアコンポーネント](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe Client Data Layer](/help/developing/data-layer/overview.md#installation-activation)
* [AMP のサポート](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
