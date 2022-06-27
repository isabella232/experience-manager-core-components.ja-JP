---
title: アダプティブ画像サーブレット
description: コアコンポーネントで画像配信にアダプティブ画像サーブレットを使用する方法と、その使用を最適化する方法について説明します。
role: Architect, Developer, Admin, User
source-git-commit: 3ff1343ab4ef7a52f910984a0bcd8fc4201441bf
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 58%

---


# アダプティブ画像サーブレット {#adaptive-image-servlet}

コアコンポーネントで画像配信にアダプティブ画像サーブレットを使用する方法と、その使用を最適化する方法について説明します。

## アダプティブ画像サーブレットと Web に最適化された画像配信のどちらが使用されますか？ {#options}

画像コアコンポーネントでは、2 つの方法で画像を配信できます。

* アダプティブ画像サーブレットがデフォルトです。
* [Web に最適化された画像配信](/help/developing/web-optimized-image-delivery.md) は AEMaaCS で利用でき、ダウンロードサイズを平均で 25%削減します。

このドキュメントでは、デフォルトのアダプティブ画像サーブレットについて説明します。

## 概要 {#overview}

デフォルトでは、画像コンポーネントは、コアコンポーネントのアダプティブ画像サーブレットを使用して画像を配信します。 [アダプティブ画像サーブレット](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet)は、画像処理とストリーミングを担当し、開発者は[コアコンポーネントのカスタマイズ](/help/developing/customizing.md)に活用できます。

## レンディション選択の最適化 {#optimizing-rendition-selection}

アダプティブ画像サーブレットは、要求された画像サイズおよびタイプに最適なレンディションを選択しようとします。アダプティブ画像サーブレットで処理をできるだけ少なくするために、DAM レンディションと画像コンポーネントで許可される幅を同期して定義することをお勧めします。

これにより、パフォーマンスが向上し、ベースとなる画像処理ライブラリで一部の画像が正しく処理されない問題を回避できます。

## 最終変更ヘッダーの使用 {#last-modified}

`Last-Modified` ヘッダーを介した条件付き要求は、アダプティブ画像サーブレットでサポートされますが、`Last-Modified` ヘッダーのキャッシュを[ Dispatcher で有効にする必要があります](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=ja#caching-http-response-headers)。

[AEM プロジェクトアーキタイプ](/help/developing/archetype/overview.md)のサンプル Dispatcher 設定には、既にこの設定が含まれています。
