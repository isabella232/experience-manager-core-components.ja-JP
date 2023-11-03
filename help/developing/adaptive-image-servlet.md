---
title: アダプティブ画像サーブレット
description: コアコンポーネントで画像配信にアダプティブ画像サーブレットを使用する方法と、その使用を最適化する方法について説明します。
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: 785aa82930e3bcf6ef16d7a1cdc614d230e8daa8
workflow-type: ht
source-wordcount: '410'
ht-degree: 100%

---

# アダプティブ画像サーブレット {#adaptive-image-servlet}

コアコンポーネントで画像配信にアダプティブ画像サーブレットを使用する方法と、その使用を最適化する方法について説明します。

## アダプティブ画像サーブレットまたは web に最適化された画像配信 {#options}

画像コアコンポーネントでは、2 とおりの方法で画像を配信できます。

* アダプティブ画像サーブレットがデフォルトです。
* [Web に最適化された画像配信](/help/developing/web-optimized-image-delivery.md)は AEMaaCS で使用でき、ダウンロードサイズを平均で 25%削減します。

このドキュメントでは、デフォルトのアダプティブ画像サーブレットについて説明します。

## 概要 {#overview}

デフォルトでは、画像コンポーネントは、コアコンポーネントのアダプティブ画像サーブレットを使用して画像を配信します。[アダプティブ画像サーブレット](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet)は、画像処理とストリーミングを担当し、開発者が[コアコンポーネントのカスタマイズ](/help/developing/customizing.md)に活用できます。

## レンディションの選択 {#rendition-selection}

アダプティブ画像サーブレットは、表示されるコンテナのサイズに応じて、表示する最も適切なレンディションを自動的に選択します。レンディション選択のプロセスは次のとおりです。

1. アダプティブ画像サーブレットは、画像アセットの使用可能なすべてのレンディションをレビューします。
1. 元の参照先アセットと同じ MIME タイプのものだけが選択されます。
   * 例えば、元のアセットが PNG の場合、PNG レンディションのみ考慮されます。
1. これらのレンディションの寸法が考慮されて、画像を表示するコンテナのサイズと比較されます。
   1. レンディションがコンテナサイズ以上の場合、候補レンディションのリストに追加されます。
   1. レンディションがコンテナサイズより小さい場合は無視されます。
   1. これらの条件により、レンディションはアップスケールされなくなります。アップスケールされると、画質に影響が出るおそれがあります。
1. アダプティブ画像サーブレットは、候補リストから最も小さいファイルサイズのレンディションを選択します。

## レンディション選択の最適化 {#optimizing-rendition-selection}

アダプティブ画像サーブレットは、要求された画像サイズおよびタイプに最適なレンディションを選択しようとします。アダプティブ画像サーブレットで処理をできるだけ少なくするために、DAM レンディションと画像コンポーネントで許可される幅を同期して定義することをお勧めします。

これにより、パフォーマンスが向上し、ベースとなる画像処理ライブラリで一部の画像が正しく処理されない問題を回避できます。

## Last-Modified ヘッダーの使用 {#last-modified}

`Last-Modified` ヘッダーを介した条件付き要求は、アダプティブ画像サーブレットでサポートされますが、`Last-Modified` ヘッダーのキャッシュを[ Dispatcher で有効にする必要があります](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=ja#caching-http-response-headers)。

[AEM プロジェクトアーキタイプ](/help/developing/archetype/overview.md)のサンプル Dispatcher 設定には、既にこの設定が含まれています。
