---
title: Adobeクライアントデータレイヤーの拡張
description: Adobeクライアントデータレイヤーは、いくつかの基本的なパターンに従って拡張できます
translation-type: tm+mt
source-git-commit: 896ed679ed3351cb309a34b38bf97fe81adc2cfe
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---


# Adobeクライアントデータレイヤーの拡張 {#extending-acdl}

コアコンポーネントは、カスタムダイアログオプションを使用して拡張できます。このオプションを使用すると、コンテンツ作成者はデータレイヤーに関連する追加情報を入力できます。

これらのフィールドをコアコンポーネントが提供するデータレイヤーに含めるには、独自のデータレイヤーメソッドを実装するコンポーネントのモデルを拡張する必要があります。

## 例：タイトルコンポーネント {#example}

「 [Title」コンポーネントのようなコアコンポーネントは](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) 、デフォルトで返される [メソッドを持つComponent](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) を拡張 `getData`[`ComponentData`します。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` コンポーネントに実装できる事前定義済みのフィールド（およびなど） `getDataLayerLinkUrl` をシリアル化 `getDataLayerTitle` し [`TitleImpl`ます。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

したがって、カスタムSlingモデルには、より多くのフィールドを返すように拡張するオブジェクトを返す `getData` メソッド `ComponentData` がある場合があります。

この操作を行うと、データレイヤーに入力されるデータのJSONを使用して、コンポーネントのHTML要素に `data-cmp-data-layer` 属性を追加します。 この時点で、このデータをリッスンするスクリプトや関連するイベントを実装できます。
