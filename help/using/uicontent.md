---
title: aemプロジェクトのアーキタイプのui.contentモジュール
seo-title: aemプロジェクトのアーキタイプのui.contentモジュール
description: aemプロジェクトのアーキタイプのui.contentモジュール
seo-description: aemプロジェクトのアーキタイプのui.contentモジュール
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 3c37b57eb72d1d662cdbd41ca54cdc592919203c

---


# aemプロジェクトのアーキタイプのui.contentモジュール {#uicontent-module}

The ui.content maven module (`<src-directory>/<project>/ui.content`) includes baseline content and configurations beneath `/content` and `/conf`. ui.content は ui.apps と同様、AEM パッケージにコンパイルされます。主な違いは、ui.content に格納されているノードは AEM インスタンスで直接修正できる点です。これには、ページ、DAM アセット、および編集可能テンプレートが含まれます。ui.contentモジュールは、クリーンインスタンス用のサンプルコンテンツを保存したり、ソース管理で管理されるいくつかのベースライン設定を作成したりするために使用できます。

## filter.xml {#filter}

ui.content `filter.xml` モジュールのファイルは、にあり、ui.contentパッ `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` ケージと共に含まれ、インストールされるパスが含まれています。 Notice that a `mode="merge"` attribute is added to the path. これにより、コードのデプロイメントを使用してデプロイされた設定が、AEMインスタンスで直接作成されたコンテンツや設定を自動的に上書きすることはありません。

## ui.content/pom.xml

ui.appsモジュールと同様に、ui.contentモジュールはFileVaultパッケージプラグインを使用します。 ただし、ui.content pom (`<src>/<project>/ui.content/pom.xml`)には、という名前の追加の設定プロパティ `acHandling`が含まれ、に設定されま `merge_preserve`す。 これは、ui.contentモジュールに、テンプレートを編集できるユーザーを決定する権限であるアクセス制御リスト(ACL)が含まれているためです。 In order for these ACLs to be imported into AEM the `acHandling` property is needed.
