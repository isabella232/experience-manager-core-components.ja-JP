---
title: AEM プロジェクトアーキタイプのコアモジュール
seo-title: AEM プロジェクトアーキタイプのコアモジュール
description: AEM プロジェクトアーキタイプのコアモジュール
seo-description: AEM プロジェクトアーキタイプのコアモジュール
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: ca7a47d8ac91516659c115a3f27c09f0ee4b8b33

---


# AEM プロジェクトアーキタイプのコアモジュール {#core-module}

コア maven モジュール（`<src-directory>/<project>/core`）には、実装で必要となるすべての Java コードが含まれます。このモジュールは、すべての Java コードをパッケージ化し、OSGi バンドルとして AEM インスタンスにデプロイします。

`<src-directory>/<project>/core/pom.xml` で定義される Maven Bundle Plugin は、AEM の OSGi コンテナによって認識される OSGi バンドルに Java コードをコンパイルするために使用されます。Sling Model の場所もここで定義されます。

上位レベルの環境では、ui.apps モジュールとは別にコアバンドルをデプロイする必要があることはまれですが、ローカルの開発／テスト中は、コアバンドルを直接デプロイすると便利です。Maven Sling プラグインにより、`autoInstallBundle` プロファイル（[親 POM](overview.md#parent-pom) で定義される）を使用してコアバンドルを AEM に直接デプロイできるようになります。

```
mvn -PautoInstallBundle clean install
```

Once successfully executed, you should be able to see the Bundles Console at `http://<host>:<port>/system/console/bundles`.
