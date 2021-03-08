---
product: Adobe Experience Manager
description: Adobe Experience Manager コアコンポーネントのドキュメント
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.ja-JP
index: y
solution-title: AEM の学習とサポート
solution-hub-url: https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/home.html
getting-started-title: AEM 向け開発の手引き
getting-started-url: https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/core-concepts/home.html
tutorials-title: AEM チュートリアル
tutorials-url: https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/cloud-service/overview.html
translation-type: ht
source-git-commit: f109463f1942349c300600acf6b94f268e8aa60e
workflow-type: ht
source-wordcount: '147'
ht-degree: 100%

---


# 内部使用メタデータ

GitHub オーサリングシステムのメタデータは階層的で、次の増加する先例レベルが定義されます。

1. metadata.md
1. 目次
1. 記事

metadata.md ファイルで定義されたメタデータはリポジトリ全体に適用されますが、目次と記事のレベルで上書きできます。メタデータの上書きは、可能な限り低いレベルでおこなう必要があります。

最低限必要なのは、experience-manager-core-components.en リポジトリ内のメタデータです。

metadata.md

* `product`
* `git-repo`
* `index: y`
* `solution-title`
* `solution-hub-url`
* `getting-started-title`
* `getting-started-url`
* `tutorials-title`
* `tutorials-url`

目次

* `sub-product`
* `user-guide-title`

記事

* `title`
* `description`
* `index: n`（以前のバージョンのコンポーネントのみ）

メタデータに関する追加情報は、[内部オーサリングガイド](https://docs.adobe.com/help/ja-JP/collaborative-doc-instructions/collaboration-guide/markdown/metadata.html#solution-metadata)を参照してください。
