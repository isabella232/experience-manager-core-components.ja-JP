---
title: コアコンポーネントのAMPサポート
description: コアコンポーネントは、AMP — 高速化モバイルページをサポートします
translation-type: tm+mt
source-git-commit: 905096d909d4fbf624152ba3b5cbc1d80637245f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---


# コアコンポーネントのAMPサポート {#amp-support}

コアコンポーネントの [リリース2.11.0](/help/versions.md) 以降、 [AMP - Accelerated Mobile Pages](https://developers.google.com/amp) — は完全にサポートされます。

このドキュメントでは、AMPのサポート方法の概要と、サイトでAMPを有効にする方法を説明します。 ただし、技術的な詳細については、GitHub開発者ドキュメントを参照して [ください。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## AMPとは {#what-is-amp}

Accelerated Mobile Pages(AMP)は、元々Googleがモバイルブラウジング用にページを最適化するために設計したオープンソースフレームワークです。 通常、AMPページは、標準のWebページよりもずっと速く読み込まれ、より優れたモバイルエクスペリエンスを提供します。

## コアコンポーネントのAMP {#amp-in-core-components}

コアコンポーネントでのAMPのサポートは、 [完全に設定可能です。](#enabling-amp) ページのAMPバージョンは、標準HTMLバージョンと一緒に排他的に提供するか、まったく提供しないかができます。

コアコンポーネントは、AMPページをレンダリングす `amp` るためにSlingセレクターとして使用します。 例えば、通常のページ `example.html` をレンダリングし、AMPバージョン `example.amp.html` になります。

### 要件 {#requirements}

AMPをコアコンポーネントと共に使用する場合、主な違いは、AMPでは、最適化と共に、すべてのCSSが `<head>` 要素内でインライン化される必要があるということです。

これをサポートするために、カスタマイズされたページコンポーネントが使用され、ページに存在するコンポーネントのAMP固有のCSSのみが読み込まれます。

その他の要件および技術的な詳細については、GitHub開発者ドキュメントを参照して [ください。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

### コアコンポーネントでのAMPの使用 {#using-amp}

個々のプロジェクトは、AMPを活用するかどうかを決定できます。 実際、AMPと標準のHTMLページは並行して配信できるので、プロジェクトは、プロジェクトの特定のページでのみAMPを使用するように選択できます。

### AMPサポートのインストール {#installing-amp}

AMPはオプションなので、コアコンポーネントに拡張として配信されます。

* Cloud ServiceプロジェクトとしてのAEMの場合、拡張機能は自動的に使用可能になります。
* オンプレミスおよびAMSプロジェクトの場合、コアコンポーネントのインストール時に、拡張機能を明示的にインストールする必要があります。

拡張機能がインストールされたら、コンポーネント作成者は、単に拡張機能内のスーパータイプを指すだけで済みます。

### ページに対するAMPの有効化 {#enabling-amp}

ページに対してAMPを有効にするには、 **AMPモード** が [ページポリシーで選択されている必要があります。](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html#editingatemplatepagepolicies)

![AMPページポリシーのオプション](/help/assets/amp-policy.png)

* **AMPなし** — ページは標準のHTMLとしてのみ配信されます。
* **ペアAMP** — ページは、AMPとHTMLとして配信されます。
* **AMPのみ** — ページはAMPとしてのみ配信されます。

ページのAMP設定は、個々のページの [ページプロパティ](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/authoring/editing-page-properties.html) で上書きすることもできます。

![AMPページのプロパティ](/help/assets/amp-page-properties.png)

* **「ページテンプレートから継承** 」 — これはデフォルト値で、ページテンプレートのポリシーから設定を取得できます。
* **AMPなし** — ページは標準のHTMLとしてのみ配信されます。
* **ペアAMP** — ページは、AMPとHTMLとして配信されます。
* **AMPのみ** — ページはAMPとしてのみ配信されます。
