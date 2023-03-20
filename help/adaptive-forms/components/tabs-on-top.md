---
title: アダプティブFormsコアコンポーネント — 上部のタブ
description: 上部のコアコンポーネントで、アダプティブFormsのタブを使用するか、カスタマイズします。
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---


# 上部のタブ {#tabs-on-top-adaptive-forms-core-component}

アダプティブフォームの上部にあるタブレイアウトを使用すると、フォームの関連するフィールドやセクションを別々のタブに整理し、グループ化することができます。 各タブはタブラベルで表され、通常はフォームの上部に配置され、特定のフォームフィールドとセクションのセットが含まれます。 このレイアウトを使用すると、ユーザーはフォームの異なるセクション間を簡単に移動してアクセスでき、ユーザーにとって使いやすく、圧倒的に少ないセクションになります。 これは、通常、フォームに多数のフィールドとセクションが含まれ、それらをより小さく管理しやすいチャンクに分割する必要がある場合に使用されます。 また、障碍のあるユーザーがフォームに簡単にアクセスできるように、キーボードショートカットを使用してフォーム内を移動できるので、タブはアクセシビリティの向上に役立ちます。

**例**

![](/help/adaptive-forms/assets/tabs.png)

## 使用方法 {#reasons-to-use-tab-on-the-top-layout}

アダプティブフォームの上部レイアウトでタブを使用する理由はいくつかあります。

* **組織**:タブを使用して、フォームの様々なセクションを別々のカテゴリに整理し、必要な情報をユーザーが簡単に見つけられるようにします。

* **省スペース**:タブを使用すると、フォームの 1 つのセクションのみを一度に表示できるので、ページ上のスペースを節約できます。

* **ユーザーエクスペリエンスの向上**:タブを使用すると、フォームをより視覚的に訴えかけ、使いやすくすることで、ユーザーエクスペリエンスを向上させることができます。

* **モバイル対応**:タブを使用すると、スクロールを減らし、フィールド間を簡単に切り替えることで、フォームがよりモバイルに適した形式になります。

つまり、タブを使用すると、フォームをより整理し、スペースを効率的に、使いやすく、アクセスしやすくすることができます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブFormsアコーディオンコアコンポーネントは、Cloud Service用コアコンポーネント 2.0.4 の一部として 2023 年 2 月にリリースされ、AEM 6.5.16.0 Forms以降用コアコンポーネント 1.1.12 にリリースされました。 次の表に、サポートされているすべてのバージョン、AEMの互換性、および対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms以降 |
|---|---|---|
| v1 | 互換性あり<br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降 | 互換性あり<br>[リリース 1.1.12](/help/adaptive-forms/version.md) 2.0.0 未満です。 |

コアコンポーネントのバージョンとリリースについて詳しくは、 [コアコンポーネントのバージョン](/help/adaptive-forms/version.md) 文書。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

上部のコアコンポーネントのアダプティブFormsのタブに関する最新情報については、 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/tabsontop/v1/tabsontop). コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けドキュメント](/help/developing/overview.md).

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者に対する上部のエクスペリエンスのタブを簡単にカスタマイズできます。 また、上部のオプションで簡単にタブを定義し、シームレスなユーザーエクスペリエンスを実現できます。

## デザインダイアログ {#design-dialog}
