---
title: aemプロジェクトのアーキタイプのui.appsモジュール
seo-title: aemプロジェクトのアーキタイプのui.appsモジュール
description: aemプロジェクトのアーキタイプのui.appsモジュール
seo-description: aemプロジェクトのアーキタイプのui.appsモジュール
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 3c37b57eb72d1d662cdbd41ca54cdc592919203c

---


# aemプロジェクトのアーキタイプのui.appsモジュール {#uiapps-module}

The ui.apps maven module (`<src-directory>/<project>/ui.apps`) includes all of the rendering code needed for the site beneath `/apps`. これには CSS／JS が含まれ、それらは clientlibs と呼ばれる AEM の形式で保存されます。また、これには動的 HTML をレンダリングするための HTL スクリプトも含まれます。ui.appsモジュールは、JCRの構造に対するマップと考えることができますが、ファイルシステムに保存し、ソース管理にコミットできる形式です。

Apache Jackrabbit FileVault Package プラグイン は、ui.apps モジュールのコンテンツを、AEM にデプロイできる AEM パッケージにコンパイルするために使用されます。プラグインのグローバル設定は親pom.xmlで定義されます。

## 親 POM {#parent-pom}

[親POM](archetype.md#parent-pom) (`<src>/<project>/pom.xml`)には、プロジ `<plugin>` ェクトで使用するプラグインの様々な設定を定義するセクションが含まれます。 これには、Jackrabbit fileVaultパッケージプラグ `filterSource` イン用の設定が含まれます。 The `filterSource` points to the location of the `filter.xml` file that is used to define the jcr paths that are included in the package.

Jackrabbit fileVault Package pluginに加えて、Content Package pluginの定義も使用し、パッケージをAEMにプッシュします。 同じ親POMで定義され `aem.host`たグローバ `aem.port``vault.user``vault.password` ルプロパティに対応する、、、、およびの変数が使用されることに注意してください。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)は、のタグを `embedded` 提供します `filevault-package-maven-plugin`。 The `embedded` tags include the compiled core bundle as part of the ui.apps package and where it will be installed.

core.wcm.components.allおよびcore.wcm.components.examplesパッケージがサブパッケージとして含まれています。 これにより、WKND コードと共に毎回コアコンポーネントのパッケージがデプロイされます。

依存関係リストには、core.wcm.components.allとcore.wcm.components.examplesが依存関係として含まれています。 However as a best practice, versions for dependencies are omitted here and managed in the [parent pom file](archetype.md#core-components).

## filter.xml {#filter}

ui.apps `filter.xml` モジュールのファイルは、にあ `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` り、ui.appsパッケージと共に含まれ、インストールされるパスが含まれています。
