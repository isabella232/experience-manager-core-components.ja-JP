---
title: AEM プロジェクトアーキタイプの ui.tests モジュール
description: AEM プロジェクトアーキタイプの UI テストの使用方法
feature: コアコンポーネント、AEMプロジェクトアーキタイプ
role: アーキテクト、開発者、管理者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 93%

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
