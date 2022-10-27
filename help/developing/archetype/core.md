---
title: AEM プロジェクトアーキタイプのコアモジュール
description: AEM プロジェクトアーキタイプのコアモジュール
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 531a7858dd26d32ef189c459c5e7035b6ae0b524
workflow-type: ht
source-wordcount: '182'
ht-degree: 100%

---

# AEM プロジェクトアーキタイプのコアモジュール {#core-module}

コア maven モジュール（`<src-directory>/<project>/core`）には、実装で必要となるすべての Java コードが含まれます。このモジュールは、すべての Java コードをパッケージ化し、OSGi バンドルとして AEM インスタンスにデプロイします。

`<src-directory>/<project>/core/pom.xml` で定義される Maven Bundle Plugin は、AEM の OSGi コンテナによって認識される OSGi バンドルに Java コードをコンパイルするために使用されます。Sling Model の場所もここで定義されます。

上位レベルの環境では、ui.apps モジュールとは別にコアバンドルをデプロイする必要があることはまれですが、ローカルの開発／テスト中は、コアバンドルを直接デプロイすると便利です。Maven Sling プラグインにより、`autoInstallBundle` プロファイル（[親 POM](/help/developing/archetype/using.md#parent-pom) で定義される）を使用してコアバンドルを AEM に直接デプロイできるようになります。

```shell
mvn -PautoInstallBundle clean install
```

正常に実行されると、`http://<host>:<port>/system/console/bundles` にバンドルコンソールが表示されます。

## 単体テスト {#unit-tests}

コアモジュールでの単体テストは、バンドルに含まれているコードの従来の単体テストを示しています。テストするには、次のコマンドを実行します。

```shell
mvn clean test
```
