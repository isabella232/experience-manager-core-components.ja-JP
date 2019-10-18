---
title: AEMプロジェクトアーキタイプのコアモジュール
seo-title: AEMプロジェクトアーキタイプのコアモジュール
description: AEMプロジェクトアーキタイプのコアモジュール
seo-description: AEMプロジェクトアーキタイプのコアモジュール
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 683b4f4705c226275439a408423cbf1b23bea66f

---


# AEMプロジェクトアーキタイプのコアモジュール {#core-module}

The core maven module (`<src-directory>/<project>/core`) includes all the Java code needed for the implementation. このモジュールは、すべての Java コードをパッケージ化し、OSGi バンドルとして AEM インスタンスにデプロイします。

`<src-directory>/<project>/core/pom.xml` で定義される Maven Bundle Plugin は、AEM の OSGi コンテナによって認識される OSGi バンドルに Java コードをコンパイルするために使用されます。ここでSlingモデルの場所が定義されます。

上位レベルの環境では、ui.appsモジュールとは別にコアバンドルをデプロイする必要があることはまれですが、ローカルの開発/テスト中は、コアバンドルを直接デプロイすると便利です。 The Maven Sling Plugin allows the core bundle to be deployed to AEM directly leveraging the `autoInstallBundle` profile as defined in the [parent POM](overview.md#parent-pom).

```
mvn -PautoInstallBundle clean install
```

正常に実行されると、にバンデルコンソールが表示されま `http://<host>:<port>/system/console/bundles`す。
