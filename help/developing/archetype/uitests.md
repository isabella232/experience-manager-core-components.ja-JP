---
title: AEM プロジェクトアーキタイプの ui.tests モジュール
description: AEMプロジェクトのアーキタイプUIテストの使用方法
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 26%

---


# AEM プロジェクトアーキタイプの ui.tests モジュール {#uitests-module}

プロジェクトには、次の 3 つのレベルのテストが含まれています。

* [単体テスト](core.md#unit-tests)
* [統合テスト](ittests.md)
* UIテスト

この記事では、ui.testsモジュールの一部として使用できるUIテストについて説明します。

## UIテストの実行{#running-tests}

テストするには、次の手順を実行します。

```shell
mvn verify -Pui-tests-local-execution
```

実行後、レポートとログは`target/reports`フォルダーで使用できます。

## 追加のオプション{#additional-options}

UIテストは、ローカルブラウザとDockerイメージに対するヘッドレステストなど、様々なオプションを使用して実行できます。 詳細は、ui.testsモジュール](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests)の[README.mdファイルを参照してください。
