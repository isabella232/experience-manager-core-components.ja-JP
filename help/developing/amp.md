---
title: コアコンポーネントの AMP サポート
description: コアコンポーネントは、AMP（Accelerated Mobile Pages）をサポートします
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '558'
ht-degree: 100%

---

# コアコンポーネントの AMP サポート {#amp-support}

コアコンポーネントの[リリース 2.11.0](/help/versions.md) 以降で、[AMP（Accelerated Mobile Pages）](https://developers.google.com/amp)は完全にサポートされます。

このドキュメントでは、AMP のサポート方法の概要と、サイトで AMP を有効にする方法を説明します。ただし、技術的な詳細については、[GitHub 開発者ドキュメント](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)を参照してください。

## AMP とは {#what-is-amp}

Accelerated Mobile Pages（AMP）は、元々 Google がモバイルブラウジング用にページを最適化するために設計したオープンソースフレームワークです。通常、AMP ページは、標準の Web ページよりもさらに速く読み込まれ、優れたモバイルエクスペリエンスを提供します。

## コアコンポーネントの AMP {#amp-in-core-components}

コアコンポーネントでの AMP サポートは、[完全に設定可能です。](#enabling-amp)ページの AMP バージョンは、標準 HTML バージョンと一緒に排他的に提供する、またはまったく提供しないかを設定できます。

コアコンポーネントは、AMP ページをレンダリングするために Sling セレクターとして `amp` を使用します。例えば、`example.html` は通常のページをレンダリングし、`example.amp.html` は AMP バージョンになります。

個々のプロジェクトで AMP を活用するかどうかを決定できます。さらに、AMP と標準の HTML ページは並行して提供できるので、プロジェクトの特定のページでのみ AMP を使用するように選択できます。

## プロジェクトでの AMP サポートの使用の手引き {#getting-started}

AMP サポートは高い柔軟性を提供しますが、これを使い始めるには、いくつかの簡単な手順が必要です。

1. 必要に応じて、AMP サポート拡張機能をインストールします。
   * AEM as a Cloud Service プロジェクトの場合、拡張機能はコアコンポーネントで自動的に使用でき、インストールは必要ありません。
   * On-Premise および AMS プロジェクトの場合、コアコンポーネントのインストール時に、拡張機能を明示的にインストールする必要があります。
1. AMP 拡張機能がインストールされたら、コンポーネント作成者は、単に拡張機能内のスーパータイプを示すだけで済みます。
1. テンプレートレベルまたは個々のページで、[AMP サポートを有効にします](#enabling-amp)。
1. 必要に応じて、インライン [CSS をデプロイします](#css-requirements)。

### ページに対する AMP の有効化 {#enabling-amp}

ページに対して AMP を有効にするには、[ページポリシー](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)で **AMP モード**&#x200B;が選択されている必要があります。

![AMP ページポリシーのオプション](/help/assets/amp-policy.png)

* **AMP なし** - ページは標準の HTML としてのみ提供されます。
* **ペア AMP** - ページは、AMP および HTML として配信されます。
* **AMP のみ** - ページは AMP としてのみ提供されます。

ページの AMP 設定は、個々のページの[ページプロパティ](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)で上書きすることもできます。

![AMP ページプロパティ](/help/assets/amp-page-properties.png)

* **ページテンプレートから継承** - これはデフォルト値で、ページテンプレートのポリシーから設定を取得できます。
* **AMP なし** - ページは標準の HTML としてのみ提供されます。
* **ペア AMP** - ページは、AMP および HTML として配信されます。
* **AMP のみ** - ページは AMP としてのみ提供されます。

### CSS の要件 {#css-requirements}

AMP をコアコンポーネントと共に使用する場合、主な違いは、AMP では、`<head>` 要素内で[すべての CSS をインライン化](including-clientlibs.md#inlining)および最適化する必要があるということです。

これをサポートするために、カスタマイズされたページコンポーネントが使用され、ページに存在するコンポーネントの AMP 固有の CSS のみが読み込まれます。

>[!NOTE]
>
>AMP デザインの制約により、アドビは、ページの AMP バージョンでレスポンシブグリッドを使用することをサポートしません。

その他の要件および技術的な詳細については、[GitHub 開発者ドキュメント](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)を参照してください。
