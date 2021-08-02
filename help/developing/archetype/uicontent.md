---
title: AEM プロジェクトアーキタイプの ui.content モジュール
description: AEM プロジェクトアーキタイプの ui.content モジュール
feature: コアコンポーネント、AEM プロジェクトアーキタイプ
role: Architect, Developer, Admin
exl-id: af019cd8-c733-4b53-bb57-321dd9451178
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '223'
ht-degree: 100%

---

# AEM プロジェクトアーキタイプの ui.content モジュール {#uicontent-module}

ui.content maven モジュール（`<src-directory>/<project>/ui.content` の `/content`）および `/conf` の下には、ベースラインコンテンツおよび設定が含まれています。ui.content は ui.apps と同様、AEM パッケージにコンパイルされます。主な違いは、ui.content に格納されているノードは AEM インスタンスで直接修正できる点です。これには、ページ、DAM アセット、および編集可能テンプレートが含まれます。ui.content モジュールは、クリーンなインスタンスのサンプルコンテンツ、またはソース管理システムで管理されるベースライン設定を格納するために使用できます。

## filter.xml {#filter}

ui.content モジュールの `filter.xml` ファイルは `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` にあり、ui.content パッケージに含まれてインストールされるパスを含みます。`mode="merge"` 属性がパスに追加されます。これにより、コードのデプロイメント時にデプロイされた設定が、AEM インスタンスで直接作成されたコンテンツや設定を自動で上書きすることを回避できます。

## ui.content/pom.xml

ui.content モジュールは、ui.apps モジュールと同様に FileVault Package プラグインを使用します。ただし、ui.content pom（`<src>/<project>/ui.content/pom.xml`）には、`acHandling` という名前で、`merge_preserve` に設定される追加の設定プロパティが含まれます。これは、ui.content モジュールに、テンプレートを編集できるユーザーを決定する権限であるアクセス制御リスト（ACL）が含まれているためです。これらの ACL を AEM に読み込むには、`acHandling` プロパティが必要です。
