---
title: コアコンポーネントの紹介
seo-title: コアコンポーネントの紹介
description: '最新のテクノロジーおよびベストプラクティスに基づいて構築された堅牢で拡張性のあるベースコンポーネントを提供するために、コアコンポーネントが導入されました。 '
seo-description: '最新のテクノロジーおよびベストプラクティスに基づいて構築された堅牢で拡張性のあるベースコンポーネントを提供するために、コアコンポーネントが導入されました。 '
uuid: b815c7d1- fbb0-4480- bd23-42606ff8b1eb
contentOwner: User
content-type: リファレンス
topic-tags: 概要
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: c44bb0d7-5d91-4659-878e- a0658fe29aa2
translation-type: tm+mt
source-git-commit: 7130f4ae8add8c8dc3cdfcc4addd0621722b89f7

---


# Core Components Introduction{#core-components-introduction}

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。コンポーネントは、常にAEMエクスペリエンスの基本要素となってきましたが、ページ作成者にとってはシンプルで強力なものであり、開発者向けに柔軟性と拡張性のあるコンポーネントを開発しています。

コアコンポーネントが導入され、最新のテクノロジーとベストプラクティスに基づいて構築され、アクセシビリティガイドラインに基づいて構築され、アクセシビリティガイドラインに準拠し、WCAG2.0AA標準に準拠しています。コアコンポーネントでは、ページオーサリングが柔軟でカスタマイズ可能で、カスタム機能を提供するために拡張されています。これらのコンポーネントは開発者にとって簡単です。

## コアコンポーネントを試す

If you want to get started straight away trying out the Core Components, head over to the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html). コンポーネントライブラリは、ほとんどのコアコンポーネントの現在のバージョンのオンラインショーケースであり、コンポーネントのバリエーションと、サンプルHTMLおよびJSON出力を表示できます。

[We. Retailリファレンスサイト](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html) では、コアコンポーネントの使用方法も説明しています。

## Core Components - Core Features {#core-components-core-features}

コアコンポーネントは次のとおりです。

|  |  |
|--- |--- |
| 事前設定可能 | テンプレートでは、ページ作成者がどのように使用できるかを定義できます。 |
| 用途が広い | 作成者は、最も多くの種類のコンテンツを作成できます。 |
| 使いやすい使いやすい | 作成者は、コンテンツを効率的に作成および管理できます。 |
| Production- Ready | 使用可能な機能です。これらは堅牢でテスト済みで、パフォーマンスも優れています。 |
| アクセシビリティ | WCAG2.0標準に準拠し、ARIAラベルを提供し、キーボードナビゲーションをサポートします。 |
| スタイルが容易 | コンポーネントはスタイルシステムを実装し、マークアップはBEM CSSの命名に従っています。 |
| SEOフレンドリ化 | HTML出力はセマンティックであり、schema.orgマイクロデータ注釈を提供します。 |
| PWA/SPA/アプリ準備完了 | 合理化されたJSON出力は、クライアント側のレンダリングにも使用できます。 |
| 拡張可能 | カスタムニーズをカバーするには、一から始めないですべて拡張できます。 |
| ソースを開く | 必要でない場合は、GitHub（Apache License）の機能強化を行います。 |
| バージョン管理 | 影響を受ける可能性のある機能を改善する際に、コアコンポーネントはサイトを中断しません。 |

## Available Components {#available-components}

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

* [アコーディオン](accordion.md)
* [パンくず](breadcrumb.md)
* [ボタン](button.md)
* [コンテナ](container.md)
* [カルーセル](carousel.md)
* [コンテンツフラグメント](content-fragment-component.md)
* [コンテンツフラグメントリスト](content-fragment-list.md)
* [ダウンロード](download.md)
* [フォームボタン](form-button.md)
* [フォームコンテナ](form-container.md)
* [フォーム非表示](form-hidden.md)
* [フォームオプション](form-options.md)
* [フォームテキスト](form-text.md)
* [画像](image.md)
* [言語ナビゲーション](language-navigation.md)
* [リスト](list.md)
* [ナビゲーション](navigation.md)
* [ページ](page.md)
* [クイック検索](quick-search.md)
* [区切り文字](separator.md)
* [ソーシャルメディア共有](sharing.md)
* [タブ](tabs.md)
* [テキスト](text.md)
* [タイトル](title.md)

>[!NOTE]
>
>Core Components are not immediately available to authors, the [development team must first integrate them to your environment](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) or in [design mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html).

>[!CAUTION]
>
>一部のコアコンポーネントの一部のバージョンは、特定のバージョンのAEMとのみ互換性があります。
>
>See the individual help page (linked to in the previous list) for the specific component for compatibility information or reference the [Core Components Versions](versions.md) document for more information.

## When to Use Core Components {#when-to-use-core-components}

コアコンポーネントはまったく新規であり、複数のメリットがあるので、新しいAEMプロジェクトで使用することをお勧めします。既存のプロジェクトでは、リブランディングや全体的なリファクタリングなど、より大きなプロジェクト作業の一環として移行を行う必要があります。

For specific use recommendations, see [When to Use the Core Components?](developing.md)[を参照してください。](developing.md)

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) は、アドビのエキスパートによる技術的な詳細な解説シリーズです。このシリーズは、製品ドキュメントとその他の技術的なチャネルを補完し、開発者が特定のトピックを詳細に調べ、詳細に調べます。

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step by step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Core Components Support {#core-components-support}

コアコンポーネントは、AEMの不可欠な構成要素であり、同じ条件と条件の中で、クイックスタートの一部として配信されたかのように条件を満たしています。

他の製品機能と同様に、提供終了の一般的なルールは次のとおりです。

* 削除される前に、コンポーネントは最初に廃止されるように通知されます
* その後、お知らせの後のAEMリリースから削除されます。

これにより、サポートを終了する前に、少なくとも1つのリリースサイクルを新しいバージョンのコンポーネントに移行できます。

各コンポーネントのバージョンは、サポートされているAEMバージョンを明確に状態させます。サポートがAEMのバージョンで停止すると、そのバージョンのAEMのコアコンポーネントのサポートが実行されます。

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page of the relevant Core Components Version.

## Foundation Component Support {#foundation-component-support}

Foundationコンポーネントは多数のバージョンにわたるプロジェクト開発の基盤として提供されているため、今後も今後も引き続きサポートされます。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
