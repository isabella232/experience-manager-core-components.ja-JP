---
title: Sling のコンテキスト対応設定とコアコンポーネント
description: コアコンポーネントは、特定の機能で、Sling のコンテキスト対応設定を利用します
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Sling のコンテキスト対応設定とコアコンポーネント {#sling-context-aware-configurations}

コンテキスト対応構成は、[Sling の機能](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)です。この機能はコンテンツリソースまたはリソースツリーに関連し、コアコンポーネントでサイト全体の設定を可能にするために利用されます。

## Sling のコンテキスト対応設定 {#context-aware-configurations}

サイトの地域が異なると、異なる設定が必要となることがあります。例えば、一部のパラメーターを共有する場合、ネストされたコンテキストとグローバルなフォールバック値の継承が必要になる場合があります。AEM では、Sling のコンテキスト対応設定を活用することで、これが可能になります。

AEM での設定について詳しくは、[設定と設定ブラウザーのドキュメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html)を参照してください。

## コアコンポーネントでの使用 {#core-components}

多くのコアコンポーネント機能は、コンテキスト対応設定を利用します。これらの設定はすべて次のノードにあります。

* `/conf/<my-site>/sling:configs/<my-configuration>`

個々の設定は、特定のコンポーネントまたは機能に依存します。コンテキスト対応設定を使用するコアコンポーネントの機能は次のとおりです。

* [PDF ビューアコンポーネント](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe Client Data Layer](/help/developing/data-layer/overview.md#installation-activation)
* [AMP のサポート](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
