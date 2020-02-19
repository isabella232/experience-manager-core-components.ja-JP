---
title: コアコンポーネントの概要
description: '堅牢で拡張可能な基本コンポーネントとして導入されたコアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築されています。 '
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# コアコンポーネントの概要{#core-components-introduction}

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。コンポーネントは常に AEM エクスペリエンスの基本要素となってきました。作成者はコンポーネントを使用することで単純かつ強力にページを作成し、開発者は柔軟かつ拡張可能なコンポーネントを開発できます。

堅牢で拡張可能な基本コンポーネントとして導入されたコアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築されており、アクセシビリティガイドラインと WCAG 2.0 AA 標準に準拠しています。コアコンポーネントにより、ページのオーサリングがより柔軟でカスタマイズ可能なものとなります。開発者は、簡単にコアコンポーネントを拡張してカスタム機能を提供することができます。

## コアコンポーネントを試す

コアコンポーネントをすぐに試してみたい場合は、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library)にアクセスしてください。コンポーネントライブラリは、ほとんどのコアコンポーネントの現在のバージョンのオンラインショーケースです。ここでは、コンポーネントの様々なバリエーションを操作したり、サンプルの HTML 出力や JSON 出力を確認したりできます。

The [WKND tutorial](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) also illustrates how the core components can be used.

## コアコンポーネント - コア機能 {#core-components-core-features}

コアコンポーネントには以下の特徴があります。

|  |  |
|--- |--- |
| 事前設定可能 | テンプレートでは、ページ作成者による使用方法を定義できます。 |
| 用途が広い | 作成者は、ほとんどの種類のコンテンツを作成できます。 |
| 使いやすい | 作成者は、コンテンツの作成や管理を効率的におこなえます。 |
| 本番で使用可能 | そのまま使用できます。堅牢でテスト済みであり、パフォーマンスも優れています。 |
| 高いアクセシビリティ | WCAG 2.0 標準に準拠し、ARIA ラベルを提供し、キーボードナビゲーションをサポートします。 |
| スタイル設定が容易 | コンポーネントはスタイルシステムを実装し、マークアップは BEM CSS の命名規則に従っています。 |
| SEO フレンドリー | HTML 出力はセマンティックであり、schema.org マイクロデータ注釈を提供します。 |
| PWA／SPA／App に対応 | 合理化された JSON 出力は、クライアント側のレンダリングにも使用できます。 |
| 拡張可能 | 一から始めなくてもカスタムに対応するニーズに対応できるよう、あらゆる機能を拡張可能です。 |
| オープンソース | 何か問題が見つかった場合は、GitHub（Apache License）で改善にご協力ください。 |
| バージョン管理 | ユーザーに影響が及ぶ可能性のある機能を改善しても、コアコンポーネントを使用したサイトが動かなくなることはありません。 |
| [ローカライズ](get-started/localization.md) | スマートリファレンス解決機能により、特定のコンポーネントが対応するローカライズされたコンテンツを自動的に検索してレンダリングできます。 |

## 利用可能なコンポーネント {#available-components}

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

* [アコーディオン](components/accordion.md)
* [パンくず](components/breadcrumb.md)
* [ボタン](components/button.md)
* [コンテナ](components/container.md)
* [カルーセル](components/carousel.md)
* [コンテンツフラグメント](components/content-fragment-component.md)
* [コンテンツフラグメントリスト](components/content-fragment-list.md)
* [ダウンロード](components/download.md)
* [埋め込み](components/embed.md)
* [エクスペリエンスフラグメント](components/experience-fragment.md)
* [フォームボタン](components/forms/form-button.md)
* [フォームコンテナ](components/forms/form-container.md)
* [フォーム非表示](components/forms/form-hidden.md)
* [フォームオプション](components/forms/form-options.md)
* [フォームテキスト](components/forms/form-text.md)
* [画像](components/image.md)
* [言語ナビゲーション](components/language-navigation.md)
* [リスト](components/list.md)
* [ナビゲーション](components/navigation.md)
* [ページ](components/page.md)
* [クイック検索](components/quick-search.md)
* [区切り文字](components/separator.md)
* [ソーシャルメディア共有](components/sharing.md)
* [タブ](components/tabs.md)
* [テキスト](components/text.md)
* [タイトル](components/title.md)

>[!NOTE]
>
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](get-started/using.md)。統合されると、[テンプレートエディター](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)で使用できるようになり、事前設定されます。

>[!CAUTION]
>
>個々のコアコンポーネントの一部のバージョンは、特定のバージョンの AEM とのみ互換性があります。
>
>互換性の情報については、特定のコンポーネントに対する個々のヘルプページ（前の一覧にリンクされています）を参照するか、[コアコンポーネントバージョン](versions.md)ドキュメントで詳細を確認してください。

## どのような場合にコアコンポーネントを使用すべきか {#when-to-use-core-components}

コアコンポーネントはまったく新しい技術であり、複数のメリットがあるので、新しい AEM プロジェクトではコアコンポーネントを使用することをお勧めします。既存のプロジェクトでは、リブランディングや全体的なリファクタリングなど、より大きなプロジェクト作業の一環として移行をおこなうようにしてください。

使用に関する具体的な推奨事項については、[どのような場合にコアコンポーネントを使用すべきか](developing/overview.md#when-to-use-the-core-components)（[コアコンポーネントの開発](developing/overview.md)ドキュメント）を参照してください。

## Gems セッションの概要 {#gems-session-overview}

コアコンポーネントとその機能、AEM での活用方法の概要については、AEM Gems セッションの [AEM コアコンポーネント](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) は、アドビのエキスパートによる技術的な詳細の解説シリーズです。製品ドキュメントやその他のあらゆる技術的なチャネルを補完するこのシリーズを利用すれば、開発者は特定のトピックにふれ、深く理解することができます。

## コアコンポーネントを使用した開発 {#developing-core-components}

コアコンポーネントは堅牢で拡張可能なベースコンポーネントを提供します。このコンポーネントは、シンプルなスタイル設定から高度な機能の再利用に至るまで、容易にカスタマイズできるパターンをいくつか実装しています。詳しくは、[コアコンポーネントの開発のドキュメント](developing/overview.md)を参照してください。

Get started developing AEM Sites with Core Components by following [the WKND tutorial.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

最新のコアコンポーネントが組み込まれた [AEM プロジェクトアーキタイプ](developing/archetype/overview.md)を活用して、お客様独自の AEM プロジェクトを開始するようにしてください。

## コアコンポーネントのサポート {#core-components-support}

コアコンポーネントは AEM に不可欠な部分なので、クイックスタートの一部として提供される場合と同じ条件の下、現状のままでサポートされます。

他の製品機能と同じく、提供終了の一般的なルールは次のようになります。

* コンポーネントは、削除される前に、非推奨になったことが事前に通知されます
* 早ければその通知の後、AEM リリースからコンポーネントが削除されます。

したがって、新しいバージョンのコンポーネントへの移行を検討するユーザーに対し、サポートが終了するまでの期間として少なくとも 1 つのリリースサイクルが与えられることになります。

各コンポーネントのバージョンには、サポートされる AEM バージョンが明記されています。ある AEM バージョンのサポートが停止されると、その AEM バージョンでのコアコンポーネントのサポートも停止されます。

コンポーネントのカスタマイズのサポートについて詳しくは、関連するコアコンポーネントバージョンの[コアコンポーネントのカスタマイズ](developing/customizing.md)ページを参照してください。

## Foundation コンポーネントのサポート {#foundation-component-support}

Foundation コンポーネントは多くのバージョンにわたって様々なプロジェクト開発の基盤として機能しており、今後も当分の間、引き続きサポートされます。

ただし、アドビの開発の重点はコアコンポーネントに移っており、新機能はコアコンポーネントに追加されます。一方、[大部分の Foundation コンポーネントが AEM 6.5 で廃止され](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html)、今後 Foundation コンポーネントに対してはバグ修正のみがおこなわれます。
