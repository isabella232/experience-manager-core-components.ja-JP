---
title: 事前コンパイル済みバンドルスクリプト
description: OSGi バンドルを使用してコンポーネントスクリプトを Adobe Experience Manager Cloud Service にデプロイする方法を説明します。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 53%

---


# 事前コンパイル済みバンドルスクリプト {#precompiled-bundled-scripts}

AEM as a Cloud Service では、[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#code-packages-%2F-osgi-bundles) コンポーネントスクリプトを事前コンパイル済みバンドルスクリプトとしてデプロイすることができます。これにより、開発者は、ビルド時にスクリプトを事前にコンパイルして、OSGi バンドルとしてパッケージ化することができます。

## OSGi バンドルを介してプリコンパイル済みスクリプトをデプロイするメリット {#advantages}

スクリプトを事前コンパイル済みバンドルスクリプトとしてデプロイすると、次の利点があります。

+ ビルド時にスクリプトをコンパイルすると、開発プロセスの初期段階でエラーを検出できます。
+ Java API スクリプトの依存関係は、 `Import-Package` および `Export-Package` バンドルヘッダー。
+ 継承 ( `sling:resourceSuperType`) や他のリソースタイプへのデリゲーション (HTL の `data-sly-resource` ブロック要素または経由 `sling:include` JSP タグなど ) は、バンドルのメタデータを介してマッピングできます。
+ リソースタイプのバージョン管理は、Java API と同様の方法で適用できます。

## プリコンパイルとパッケージの読み込み {#precompilation}

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) は HTL スクリプトの構文を検証できますが、HTL スクリプトを Java クラスにトランスパイルする場合にも使用できます。これらは Maven プロジェクトの `generated-sources` フォルダーに追加され、`maven-compiler-plugin` によって選択されます。

[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) を追加して、Java API インポート用に OSGi バンドルのメタデータを生成できます。

## 継承と委任 {#inheritance-delegation}

OSGi フレームワークは、 [要件と機能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) 様々な部品間の契約を表す。 これらはメタデータを使用して記述され、実行時に適用されます。バンドルスクリプトでは、このメカニズムを使用して、継承関係（`sling:resourceSuperType`）と委任（レンダリングプロセスにおける他のリソースタイプを含む）の両方を表現します。

The `bnd` プラグイン [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) プロジェクトを使用して、 [`ui.apps`.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#code-packages-%2F-osgi-bundles) コンテンツパッケージ

## AEMプロジェクトのアーキタイプのサポート {#support}

バージョン 31 以降、 [AEM Project Archetype](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=ja) を使用して、事前にコンパイルされたバンドルされたスクリプトを使用するAEMas a Cloud Serviceプロジェクトを正しく設定できます。

さらに、AEM プロジェクトアーキタイプでは、Java パッケージレベルとスクリプトレベルでの依存関係を検証するように [AEM as a Cloud Service SDK の Build Analyzer Maven プラグイン](/help/developing/archetype/build-analyzer-maven-plugin.md)を設定します。
