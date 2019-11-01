---
title: AEM プロジェクトアーキタイプのコアモジュール
seo-title: AEM プロジェクトアーキタイプのコアモジュール
description: AEM プロジェクトアーキタイプのコアモジュール
seo-description: AEM プロジェクトアーキタイプのコアモジュール
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: ht
source-git-commit: 683b4f4705c226275439a408423cbf1b23bea66f

---


# AEM プロジェクトアーキタイプのコアモジュール {#core-module}

コア maven モジュール（`<src-directory>/<project>/core`）には、実装で必要となるすべての Java コードが含まれます。このモジュールは、すべての Java コードをパッケージ化し、OSGi バンドルとして AEM インスタンスにデプロイします。

`<src-directory>/<project>/core/pom.xml` で定義される Maven Bundle Plugin は、AEM の OSGi コンテナによって認識される OSGi バンドルに Java コードをコンパイルするために使用されます。Sling Model の場所もここで定義されます。

上位レベルの環境では、ui.apps モジュールとは別にコアバンドルをデプロイする必要があることはまれですが、ローカルの開発／テスト中は、コアバンドルを直接デプロイすると便利です。Maven Sling プラグインにより、`autoInstallBundle` プロファイル（[親 POM](overview.md#parent-pom) で定義される）を使用してコアバンドルを AEM に直接デプロイできるようになります。

```
mvn -PautoInstallBundle clean install
```

正常に実行されると、`http://<host>:<port>/system/console/bundles` に Bundels コンソールが表示されます。
