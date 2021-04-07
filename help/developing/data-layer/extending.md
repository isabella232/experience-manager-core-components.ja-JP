---
title: Adobe Client Data Layer の拡張
description: Adobe Client Data Layer は、いくつかの基本的なパターンに従って拡張できます
feature: コアコンポーネント、Adobe Client Data Layer
role: 設計者、開発者、管理者
translation-type: ht
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: ht
source-wordcount: '285'
ht-degree: 100%

---


# Adobe Client Data Layer の拡張 {#extending-acdl}

コアコンポーネントは、カスタムダイアログオプションで拡張できます。このオプションを使用すると、コンテンツ作成者はデータレイヤーに関連する追加情報を入力できます。

これらのフィールドをコアコンポーネントが提供するデータレイヤーに含めるには、独自のデータレイヤーメソッドを実装するコンポーネントのモデルを拡張する必要があります。

## 例：タイトルコンポーネント {#example}

[タイトルコンポーネント](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)などのコアコンポーネントは、デフォルトで [`ComponentData`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java) を返す `getData` メソッドを持つ[コンポーネント](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)を拡張します。

`ComponentData` は、コンポーネントが実装できる事前定義済みのフィールド（[`TitleImpl`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java) に対して `getDataLayerLinkUrl` や `getDataLayerTitle` など）をシリアル化します。

したがって、カスタム Sling モデルには、より多くのフィールドを返すように `ComponentData` を拡張するオブジェクトを返す `getData` メソッドがある場合があります。

これにより、データレイヤーに入力されるデータの JSON を使用して、コンポーネントの HTML 要素に `data-cmp-data-layer` 属性が追加されます。この時点で、このデータをリッスンするスクリプトや関連するイベントを実装できます。

>[!TIP]
>
>データレイヤーの柔軟性をさらに詳しく調べるには、カスタムコンポーネントでデータレイヤーを有効にする方法などの統合オプションについて確認してください。
