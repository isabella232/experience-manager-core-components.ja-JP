---
title: it.tests AEMプロジェクトのアーキタイプのモジュール
description: AEMプロジェクトのアーキタイプ統合テストの使用方法
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 46%

---


# it.tests AEMプロジェクトのアーキタイプ{#ittests-module}のモジュール

プロジェクトには、次の 3 つのレベルのテストが含まれています。

* [単体テスト](core.md#unit-tests)
* 統合テスト
* [UIテスト](uitests.md)

この記事では、it.testsモジュールの一部として使用できる統合テストについて説明します。

## 統合テストの実行{#running-tests}

サーバーサイドの統合テストを使用すると、AEM 環境（AEM サーバー上など）でユニット型のテストを実行できます。テストするには、次の手順を実行します。

```
mvn clean verify -PintegrationTests
```
