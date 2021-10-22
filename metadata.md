---
product: adobe experience manager
solution: Experience Manager, Experience Manager Sites
type: Documentation
description: Adobe Experience Manager コアコンポーネントのドキュメント
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.ja-JP
index: y
source-git-commit: 2fbf593dee19f22b87a0f7e98d8a1f0c9252e7e7
workflow-type: ht
source-wordcount: '112'
ht-degree: 100%

---


# 内部使用メタデータ

GitHub オーサリングシステムのメタデータは階層的で、次の増加する先例レベルが定義されます。

1. metadata.md
1. 目次
1. 記事

metadata.md ファイルで定義されたメタデータはリポジトリ全体に適用されますが、目次と記事のレベルで上書きできます。メタデータの上書きは、可能な限り低いレベルで行う必要があります。

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

メタデータに関する追加情報は、[内部オーサリングガイド](https://experienceleague.adobe.com/docs/authoring-guide-exl/using/authoring/features/metadata.html?lang=ja#solution)を参照してください。
