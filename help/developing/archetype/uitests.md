---
title: AEM プロジェクトアーキタイプの ui.tests モジュール
description: AEM プロジェクトアーキタイプの UI テストの使用方法
feature: コアコンポーネント、AEM プロジェクトアーキタイプ
role: Architect, Developer, Administrator
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 100%

---

# AEM プロジェクトアーキタイプの ui.tests モジュール {#uitests-module}

プロジェクトには、次の 3 つのレベルのテストが含まれています。

* [単体テスト](core.md#unit-tests)
* [統合テスト](ittests.md)
* UI テスト

この記事では、ui.tests モジュールの一部として使用できる UI テストについて説明します。

## UI テストの実行 {#running-tests}

テストするには、次のコマンドを実行します。

```shell
mvn verify -Pui-tests-local-execution
```

実行後、レポートとログは `target/reports` フォルダーで入手できます。

## その他のオプション {#additional-options}

UI テストは、ローカルブラウザー対するヘッドレステストや Docker イメージ形式のヘッドレステストを指定するオプションなど、様々なオプションを使用して実行できます。詳しくは、[ui.tests モジュールの README.md ファイル](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests)を参照してください。
