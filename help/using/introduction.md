---
title: コアコンポーネントの概要
seo-title: コアコンポーネントの概要
description: '堅牢で拡張可能な基本コンポーネントとして導入されたコアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築されています。 '
seo-description: '堅牢で拡張可能な基本コンポーネントとして導入されたコアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築されています。 '
uuid: b815c7d1-fbb0-4480-bd23-42606ff8b1eb
contentOwner: User
content-type: reference
topic-tags: introduction
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: c44bb0d7-5d91-4659-878e-a0658fe29aa2
translation-type: ht
source-git-commit: 0f84eb6d52b9d6d76a4347d371367acf3d34e58e

---


# コアコンポーネントの概要{#core-components-introduction}

Adobe Experience Manager では、コンポーネントは、オーサリングするページのコンテンツを構成する構造要素です。コンポーネントは常に AEM エクスペリエンスの基本要素となってきました。作成者はコンポーネントを使用することで単純かつ強力にページを作成し、開発者は柔軟かつ拡張可能なコンポーネントを開発できます。

堅牢で拡張可能な基本コンポーネントとして導入されたコアコンポーネントは、最新のテクノロジーとベストプラクティスに基づいて構築されており、アクセシビリティガイドラインと WCAG 2.0 AA 標準に準拠しています。コアコンポーネントにより、ページのオーサリングがより柔軟でカスタマイズ可能なものとなります。開発者は、簡単にコアコンポーネントを拡張してカスタム機能を提供することができます。

## コアコンポーネントを試す

コアコンポーネントをすぐに試してみたい場合は、[コンポーネントライブラリ](http://opensource.adobe.com/aem-core-wcm-components/library.html)にアクセスしてください。コンポーネントライブラリは、ほとんどのコアコンポーネントの現在のバージョンのオンラインショーケースです。ここでは、コンポーネントの様々なバリエーションを操作したり、サンプルの HTML 出力や JSON 出力を確認したりできます。

[We.Retail リファレンスサイト](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/we-retail.html)では、コアコンポーネントの使用方法についても説明しています。

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
| [ローカライズ](localization.md) | スマートリファレンス解決機能により、特定のコンポーネントが対応するローカライズされたコンテンツを自動的に検索してレンダリングできます。 |

## 利用可能なコンポーネント {#available-components}

コアコンポーネントの現在のバージョンには、次のコンポーネントが含まれています。

* [アコーディオン](accordion.md)
* [パンくず](breadcrumb.md)
* [ボタン](button.md)
* [コンテナ](container.md)
* [カルーセル](carousel.md)
* [コンテンツフラグメント](content-fragment-component.md)
* [コンテンツフラグメントリスト](content-fragment-list.md)
* [ダウンロード](download.md)
* [埋め込み](embed.md)
* [エクスペリエンスフラグメント](experience-fragment.md)
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
>コアコンポーネントは、作成者がすぐに使用できるわけではありません。[最初に開発チームがお使いの環境に統合する必要があります](using.md)。統合されると、[テンプレートエディター](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/templates.html)または[デザインモード](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/default-components-designmode.html)で使用できるようになり、事前設定されます。

>[!CAUTION]
>
>個々のコアコンポーネントの一部のバージョンは、特定のバージョンの AEM とのみ互換性があります。
>
>互換性の情報については、特定のコンポーネントに対する個々のヘルプページ（前の一覧にリンクされています）を参照するか、[コアコンポーネントバージョン](versions.md)ドキュメントで詳細を確認してください。

## どのような場合にコアコンポーネントを使用すべきか {#when-to-use-core-components}

コアコンポーネントはまったく新しい技術であり、複数のメリットがあるので、新しい AEM プロジェクトではコアコンポーネントを使用することをお勧めします。既存のプロジェクトでは、リブランディングや全体的なリファクタリングなど、より大きなプロジェクト作業の一環として移行をおこなうようにしてください。

使用に関する具体的な推奨事項については、[どのような場合にコアコンポーネントを使用すべきか](developing.md)（[コアコンポーネントの開発](developing.md)ドキュメント）を参照してください。

## Gems セッションの概要 {#gems-session-overview}

コアコンポーネントとその機能、AEM での活用方法の概要については、AEM Gems セッションの [AEM コアコンポーネント](https://helpx.adobe.com/jp/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/jp/experience-manager/kt/eseminars/gems/aem-index.html) は、アドビのエキスパートによる技術的な詳細の解説シリーズです。製品ドキュメントやその他のあらゆる技術的なチャネルを補完するこのシリーズを利用すれば、開発者は特定のトピックにふれ、深く理解することができます。

## コアコンポーネントを使用した開発 {#developing-core-components}

コアコンポーネントは堅牢で拡張可能なベースコンポーネントを提供します。このコンポーネントは、シンプルなスタイル設定から高度な機能の再利用に至るまで、容易にカスタマイズできるパターンをいくつか実装しています。詳しくは、[コアコンポーネントの開発のドキュメント](developing.md)を参照してください。

コアコンポーネントで AEM Sites の開発を始めるには、[この詳しいチュートリアル](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/getting-started.html)

最新のコアコンポーネントが組み込まれた [AEM プロジェクトアーキタイプ](overview.md)を活用して、お客様独自の AEM プロジェクトを開始するようにしてください。

## コアコンポーネントのサポート {#core-components-support}

コアコンポーネントは AEM に不可欠な部分なので、クイックスタートの一部として提供される場合と同じ条件の下、現状のままでサポートされます。

他の製品機能と同じく、提供終了の一般的なルールは次のようになります。

* コンポーネントは、削除される前に、非推奨になったことが事前に通知されます
* 早ければその通知の後、AEM リリースからコンポーネントが削除されます。

したがって、新しいバージョンのコンポーネントへの移行を検討するユーザーに対し、サポートが終了するまでの期間として少なくとも 1 つのリリースサイクルが与えられることになります。

各コンポーネントのバージョンには、サポートされる AEM バージョンが明記されています。ある AEM バージョンのサポートが停止されると、その AEM バージョンでのコアコンポーネントのサポートも停止されます。

コンポーネントのカスタマイズのサポートについて詳しくは、関連するコアコンポーネントバージョンの[コアコンポーネントのカスタマイズ](customizing.md)ページを参照してください。

## Foundation コンポーネントのサポート {#foundation-component-support}

Foundation コンポーネントは多くのバージョンにわたって様々なプロジェクト開発の基盤として機能しており、今後も当分の間、引き続きサポートされます。

ただし、アドビの開発の重点はコアコンポーネントに移っており、新機能はコアコンポーネントに追加されます。一方、[大部分の Foundation コンポーネントが AEM 6.5 で廃止され](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/default-components-foundation.html)、今後 Foundation コンポーネントに対してはバグ修正のみがおこなわれます。
