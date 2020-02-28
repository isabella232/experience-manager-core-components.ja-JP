---
product: Adobe Experience Manager
git-repo: https://github.com/AdobeDocs/experience-manager-core-components.en
index: y
solution-title: AEM の学習とサポート
solution-hub-url: https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/home.html
getting-started-title: AEM 向け開発の手引き
getting-started-url: https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/core-concepts/home.html
tutorials-title: AEM チュートリアル
tutorials-url: https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/cloud-service/overview.html
translation-type: ht
source-git-commit: a3085d266baf32649fda528a7f4703e133d03ab7

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

メタデータに関する追加情報は、[内部オーサリングガイド](https://docs.adobe.com/help/en/collaborative-doc-instructions/collaboration-guide/markdown/metadata.html#solution-metadata)を参照してください。
