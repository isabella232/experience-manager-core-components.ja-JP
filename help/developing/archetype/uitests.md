---
title: aemプロジェクトのアーキタイプのui.testsモジュール
description: AEMプロジェクトアーキタイプJUnitテストの使用方法
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# ui.tests Module of the AEM Project Archetype {#uitests-module}

プロジェクトには、次の3つのレベルのテストが含まれています。

## Unit Tests {#unit-tests}

The unit test in the [core module](core.md) showcases classic unit testing of the code contained in the bundle. テストするには、次の手順を実行します。

```
mvn clean test
```

## 統合テスト {#integration-tests}

サーバー側の統合テストを使用すると、AEM環境（AEMサーバー上など）でユニット型のテストを実行できます。 テストするには、次の手順を実行します。

```
mvn clean verify -PintegrationTests
```

## クライアント側テスト {#client-side-tests}

テスト `client-side Hobbes.js` は、ブラウザー側の動作を検証するJavaScriptベースのブラウザー側テストです。

テストするには、テストするAEMページをブラウザーで表示しているときに、左のパネルを開いて **Developer** （開発者）モードでページを開き、「 **Tests** （テスト）」タブに切り替えて、生成された **MyNameテストを見つけて実行します** 。
