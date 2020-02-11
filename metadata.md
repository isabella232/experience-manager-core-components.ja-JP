---
product: Adobe Experience Manager
git-repo: https://github.com/AdobeDocs/experience-manager-core-components.en
index: y
solution-title: AEMの学習とサポート
solution-hub-url: https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/home.html
getting-started-title: AEM向け開発の手引き
getting-started-url: https://docs.adobe.com/content/help/en/experience-manager-cloud-service/core-concepts/home.html
tutorials-title: AEM チュートリアル
tutorials-url: https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/overview.html
translation-type: tm+mt
source-git-commit: a3085d266baf32649fda528a7f4703e133d03ab7

---


# 内部使用メタデータ

GitHubオーサリングシステムのメタデータは階層的で、次の上位レベルの前例が定義されています。

1. metadata.md
1. ToC
1. 記事

metadata.mdファイルで定義されたメタデータはリポジトリ全体に適用されますが、ToCと記事のレベルで上書きできます。 メタデータの上書きは、可能な限り低いレベルで行う必要があります。

最低限必要なのは、experience-manager-core-components.enリポジトリ内のメタデータです。

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

ToCs

* `sub-product`
* `user-guide-title`

記事

* `title`
* `description`
* `index: n` （以前のバージョンのコンポーネントのみ）

メタデータに関する追加情報は、内部オーサリングガ [イドを参照してください。](https://docs.adobe.com/help/en/collaborative-doc-instructions/collaboration-guide/markdown/metadata.html#solution-metadata)
