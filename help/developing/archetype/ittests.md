---
title: AEM プロジェクトアーキタイプの it.tests モジュール
description: AEM プロジェクトアーキタイプの統合テストの使用方法
feature: コアコンポーネント、AEM プロジェクトアーキタイプ
role: Architect, Developer, Admin
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 100%

---

# AEM プロジェクトアーキタイプの it.tests モジュール {#ittests-module}

プロジェクトには、次の 3 つのレベルのテストが含まれています。

* [単体テスト](core.md#unit-tests)
* 統合テスト
* [UI テスト](uitests.md)

この記事では、it.tests モジュールの一部として使用できる統合テストについて説明します。

## 統合テストの実行 {#running-tests}

サーバーサイドの統合テストを使用すると、AEM 環境（AEM サーバー上など）でユニット型のテストを実行できます。テストするには、次のコマンドを実行します。

```
mvn clean verify -PintegrationTests
```
