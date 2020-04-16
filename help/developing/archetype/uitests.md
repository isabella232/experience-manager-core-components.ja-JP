---
title: AEM プロジェクトアーキタイプの ui.tests モジュール
description: AEM プロジェクトアーキタイプの JUnit テストの使用方法
translation-type: ht
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# AEM プロジェクトアーキタイプの ui.tests モジュール {#uitests-module}

プロジェクトには、次の 3 つのレベルのテストが含まれています。

## 単体テスト {#unit-tests}

[コアモジュール](core.md)での単体テストは、バンドルに含まれるコードの従来のユニットテストを示しています。テストするには、次の手順を実行します。

```
mvn clean test
```

## 統合テスト {#integration-tests}

サーバーサイドの統合テストを使用すると、AEM 環境（AEM サーバー上など）でユニット型のテストを実行できます。テストするには、次の手順を実行します。

```
mvn clean verify -PintegrationTests
```

## クライアントサイドテスト {#client-side-tests}

`client-side Hobbes.js` テストは、ブラウザーサイドの動作を検証する JavaScript ベースのブラウザーサイドテストです。

テストするには、テストする AEM ページをブラウザーで表示しているときに左のパネルを開いて、ページを&#x200B;**開発者モード**&#x200B;で開き、「**テスト**」タブに切り替えて、生成された **MyName Tests** を見つけて実行します。
