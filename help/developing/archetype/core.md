---
title: AEM プロジェクトアーキタイプのコアモジュール
description: AEM プロジェクトアーキタイプのコアモジュール
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
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

コアモジュールでの単体テストは、バンドルに含まれるコードの従来のユニットテストを示しています。テストするには、次の手順を実行します。

```shell
mvn clean test
```
