---
title: バンドル済みスクリプトの事前コンパイル
description: OSGiバンドルを介してコンポーネントスクリプトをAdobe Experience Manager Serverにデプロイする方法を説明します。Cloud Service
source-git-commit: 56464decc8d6ae3cef68d62bfe459bceda0539ef
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# バンドル済みスクリプトの事前コンパイル

AEM as aCloud Serviceは、事前にコンパイルされたバンドルされたスクリプトとして、[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)コンポーネントスクリプトのデプロイメントをサポートしています。 これにより、開発者は、ビルド時にスクリプトを事前にコンパイルし、OSGiバンドルとしてパッケージ化できます。

## OSGiバンドルを介して事前コンパイル済みスクリプトをデプロイするメリット

スクリプトを事前コンパイル済みのバンドルスクリプトとしてデプロイすると、次の利点があります。

+ ビルド時にスクリプトをコンパイルすることで、開発者は開発プロセスの早い段階でエラーを発見できます
+ Java APIスクリプトの依存関係は、`Import-Package`および`Export-Package`バンドルヘッダーを介して明示的に定義されます
+ 継承（`sling:resourceSuperType`を介）と他のリソースタイプ（HTLの`data-sly-resource`ブロック要素や`sling:include` JSPタグなどを介）への委任は、バンドルのメタデータを介してマッピングできます
+ リソースタイプのバージョン管理は、Java APIと同様の方法で適用できます

## プリコンパイルとパッケージのインポート

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html)は、HTLスクリプトの構文を検証できますが、HTLスクリプトをJavaクラスに転送するためにも使用できます。 これらはMavenプロジェクトの`generated-sources`フォルダーに追加され、`maven-compiler-plugin`によって取得されます。

[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin)を追加して、Java APIの読み込み用にOSGiバンドルのメタデータを生成できます。

## 継承と委任

OSGiフレームワークは、様々なコンポーネント間の契約を表す[要件と機能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies)を定義する強力な手段を提供します。 これらはメタデータを使用して記述され、実行時に適用されます。 バンドルされたスクリプトは、継承の関係(`sling:resourceSuperType`)と委任（レンダリングプロセスの他のリソースタイプを含む）の両方を表すために、このメカニズムを使用します。

[scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html)プロジェクトの`bnd`プラグインを使用して、[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)コンテンツパッケージで提供されるスクリプトに対応する要件と機能を抽出できます。

## AEMプロジェクトアーキタイプのサポート

バージョン31以降、 [AEMプロジェクトアーキタイプ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html)を使用して、事前にコンパイルされたバンドルされたスクリプトを使用するCloud ServiceプロジェクトとしてAEMを正しく設定できます。 さらに、AEMプロジェクトのアーキタイプで、[AEMをCloud ServiceSDK Build Analyzer Maven Plugin](/help/developing/archetype/build-analyzer-maven-plugin.md)として設定し、Javaパッケージレベルとスクリプトレベルの依存関係を検証します。
