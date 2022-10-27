---
title: AEM プロジェクトアーキタイプの ui.apps モジュール
description: AEM プロジェクトアーキタイプの ui.apps モジュール
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 19bceb1d8ba07c70798f2e7203db957d3e8b3d03
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 100%

---

# AEM プロジェクトアーキタイプの ui.apps モジュール {#uiapps-module}

ui.apps maven モジュール（`<src-directory>/<project>/ui.apps`）には、`/apps` 配下のサイトで必要となるすべてのレンダリングコードが含まれます。これには CSS／JS が含まれ、それらは [clientlibs と呼ばれる AEM の形式で保存されます。](uifrontend.md#clientlibs)また、これには動的 HTML をレンダリングするための HTL スクリプトも含まれます。ui.apps モジュールは、ファイルシステムに保存でき、ソース管理に対してコミットできる、JCR 内の構造とのマッピングと考えることができます。

Apache Jackrabbit FileVault Package プラグインは、ui.apps モジュールのコンテンツを、AEM にデプロイできる AEM パッケージにコンパイルするために使用されます。プラグインのグローバル設定は、parent pom.xml で定義されます。

## 親 POM {#parent-pom}

[親 POM](/help/developing/archetype/using.md#parent-pom)（`<src>/<project>/pom.xml`）には、プロジェクトで使用するプラグインの様々な設定を定義する `<plugin>` セクションが含まれます。これには、Jackrabbit FileVault Package プラグインの `filterSource` 用の設定が含まれます。`filterSource` はファイルの場所を指定しています。`filter.xml` ファイルは、パッケージに含まれる jcr パスを定義するために使用されます。

さらに、Jackrabbit FileVault Package プラグインには Content Package プラグインの定義があり、これはその後、パッケージを AEM にプッシュする際に使用されます。同じ親 POM で定義されたグローバルなプロパティに対応する `aem.host`、`aem.port`、`vault.user`、および `vault.password` の変数が使用されます。

## ui.apps/pom.xml {#uiapps-pom}

core.wcm.components.all および core.wcm.components.examples パッケージがサブパッケージとして含まれています。これにより、WKND コードと共に毎回コアコンポーネントのパッケージがデプロイされます。

依存関係リストには、core.wcm.components.all と core.wcm.components.examples が依存関係として含まれます。ただし、ベストプラクティスとしては、依存関係のバージョンを[親 pom ファイル](/help/developing/archetype/using.md#core-components)で管理することが推奨されます。

## filter.xml {#filter}

ui.apps モジュールの `filter.xml` ファイルは `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` にあり、ui.apps パッケージに含まれてインストールされるパスを含みます。
