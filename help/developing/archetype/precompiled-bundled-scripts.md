---
title: 事前コンパイル済みバンドルスクリプト
description: OSGi バンドルを使用してコンポーネントスクリプトを Adobe Experience Manager Cloud Service にデプロイする方法を説明します。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: ht
source-wordcount: '335'
ht-degree: 100%

---


# 事前コンパイル済みバンドルスクリプト {#precompiled-bundled-scripts}

AEM as a Cloud Service では、[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#code-packages-%2F-osgi-bundles) コンポーネントスクリプトを事前コンパイル済みバンドルスクリプトとしてデプロイすることができます。これにより、開発者は、ビルド時にスクリプトを事前にコンパイルして、OSGi バンドルとしてパッケージ化することができます。

## OSGi バンドルを使用して事前コンパイル済みスクリプトをデプロイするメリット {#advantages}

スクリプトを事前コンパイル済みバンドルスクリプトとしてデプロイすると、次の利点があります。

+ ビルド時にスクリプトをコンパイルすると、開発者が開発プロセスの早期にエラーを検出できます。
+ Java API スクリプトの依存関係は、`Import-Package` および `Export-Package` バンドルヘッダーを使用して明示的に定義されます。
+ （`sling:resourceSuperType` を使用した）継承および（例えば HTL の `data-sly-resource` ブロック要素や `sling:include` JSP タグなどを使用した）他のリソースタイプへの委任は、バンドルのメタデータを使用してマッピングできます。
+ リソースタイプのバージョン管理を、Java API と同様の方法で適用できます。

## 事前コンパイルとパッケージの読み込み {#precompilation}

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) は HTL スクリプトの構文を検証できますが、HTL スクリプトを Java クラスにトランスパイルする場合にも使用できます。これらは Maven プロジェクトの `generated-sources` フォルダーに追加され、`maven-compiler-plugin` によって選択されます。

[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) を追加して、Java API インポート用に OSGi バンドルのメタデータを生成できます。

## 継承と委任 {#inheritance-delegation}

OSGi フレームワークは、様々なコンポーネント間のコントラクト表現する[要件と機能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies)を定義する強力な方法を提供します。これらはメタデータを使用して記述され、実行時に適用されます。バンドルスクリプトでは、このメカニズムを使用して、継承関係（`sling:resourceSuperType`）と委任（レンダリングプロセスにおける他のリソースタイプを含む）の両方を表現します。

[`ui.apps` によって提供されるスクリプトに対応する要件と機能を抽出するには、[scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) プロジェクトの `bnd` プラグインを使用できます。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#code-packages-%2F-osgi-bundles) コンテンツパッケージ

## AEM プロジェクトアーキタイプのサポート {#support}

バージョン 31 からは、[AEM プロジェクトアーキタイプ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=ja)では、事前コンパイル済みバンドルスクリプトを使用するように AEM as a Cloud Service プロジェクトを正しく設定できます。

さらに、AEM プロジェクトアーキタイプでは、Java パッケージレベルとスクリプトレベルでの依存関係を検証するように [AEM as a Cloud Service SDK の Build Analyzer Maven プラグイン](/help/developing/archetype/build-analyzer-maven-plugin.md)を設定します。
