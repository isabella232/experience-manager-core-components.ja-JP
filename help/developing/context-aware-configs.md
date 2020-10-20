---
title: Sling のコンテキスト対応設定とコアコンポーネント
description: コアコンポーネントは、特定の機能で、Sling のコンテキスト対応設定を利用します
translation-type: tm+mt
source-git-commit: 11e2c6da0fa93084b601437fd45fd65dd8d73231
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 83%

---


# Sling のコンテキスト対応設定とコアコンポーネント {#sling-context-aware-configurations}

コンテキスト対応設定は Sling の機能です。この機能はコンテンツリソースまたはリソースツリーに関連し、コアコンポーネントでサイト全体の設定を可能にするために利用されます。

## Sling のコンテキスト対応設定 {#context-aware-configurations}

サイトの地域が異なると、異なる設定が必要となることがあります。例えば、一部のパラメーターが共有される場合、ネストされたコンテキストとグローバルなフォールバック値の継承が必要になる場合があります。AEMでは、Slingのコンテキスト対応設定が利用され、これによりこの可能性が可能になります。

AEMでの設定について詳しくは、設定と設定ブラウザーのドキュメントを [参照してください。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)

## コアコンポーネントでの使用 {#core-components}

多くのコアコンポーネント機能は、コンテキスト対応設定を利用します。これらの設定はすべて次のノードにあります。

* `/conf/<my-site>/sling:configs/<my-configuration>`

個々の設定は、特定のコンポーネントまたは機能に依存します。コンテキスト対応設定を使用するコアコンポーネントの機能は次のとおりです。

* [PDF ビューアコンポーネント](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe Client Data Layer](/help/developing/data-layer/overview.md#installation-activation)
* [AMP のサポート](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
