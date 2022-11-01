---
title: AEM as a Cloud Service SDK Build Analyzer Maven プラグイン
description: ローカルの Maven Build Analyzer プラグインに関するドキュメント
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: be66739084334120158eda96b830a7b6216ef5cd
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 97%

---

# AEM as a Cloud Service SDK Build Analyzer Maven プラグイン {#maven-analyzer-plugin}

AEM as a Cloud Service SDK Build Analyzer Maven プラグインは、様々なコンテンツパッケージプロジェクトの構造を分析します。

AEM Maven プロジェクトに含める方法については、[Maven プラグインのドキュメント](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)を参照してください。

>[!NOTE]
>
>Maven 中央リポジトリ https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/ にある最新バージョンのプラグインを参照するよう、Maven プロジェクトを更新することをお勧めします。

プラグインは、プロジェクトで設定したものではなく、利用可能な最新の SDK を使用します。

以下の表は、この手順の一部として実行されるアナライザーについて説明しています。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| モジュール | 機能、例、トラブルシューティング | ローカル SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Maven プロジェクトに含まれる他のバンドルのエクスポートパッケージ宣言で、すべての OSGI バンドルのインポートパッケージ宣言が満たされているかどうかを確認します。次のようなエラーが発生します。 <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>トラブルシューティングをおこなうには、パッケージを提供するバンドルがデプロイメントに含まれているかどうかを確認するか、エクスポートする予定のバンドルのマニフェストを調べて、誤った名前または誤ったバージョンが使用されたかどうかを確認します。 | はい | はい |
| `requirements-capabilities` | OSGI バンドルでおこなわれたすべての要件宣言が、Maven プロジェクトに含まれる他のバンドルでの機能宣言によって満たされているかどうかを確認します。次のようなエラーが発生します。 <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> トラブルシューティングをおこなうには、バンドルのマニフェストで、それが欠落している理由を判断する機能を宣言すると予想されるものを確認するか、必要なバンドルのマニフェストをチェックインして、その要件が正しいかを確認します。 | はい | はい |
| `bundle-content` | バンドルに Sling-Initial-Content で指定された初期コンテンツが含まれる場合に警告を表示します。これは、AEM as a Cloud Service クラスター環境では問題となります。警告は次のようになります。 <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>初期コンテンツの repoinit ステートメントへの変換のトラブルシューティングについては、Repoinit のドキュメントを参照してください。 | はい | はい |
| `bundle-resources` | バンドルに Sling-Bundle-Resources ヘッダーで指定されたリソースが含まれている場合に警告を表示します。これは、AEM as a Cloud Service クラスターでは問題となります。警告は次のようになります。<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> リソースを repoinit ステートメントに変換する際のトラブルシューティングについては [Repoinit ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#repo-init)を参照してください。 | はい | はい |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | これらのアナライザーは、Sling 機能モデルに準拠するアーティファクトを作成する[コンテンツパッケージを機能モデル変換プロセス](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=ja#deploying)に関連付けた詳細をチェックします。エラーが発生した場合は、Adobe カスタマーサポートに報告する必要があります。 | はい | はい |
| `api-regions-crossfeature-dups` | AEM as a Cloud Service のパブリック API をオーバーライドする Export-package 宣言が顧客の OSGI バンドルにないことを検証します。<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>この問題を修正するには、AEM パブリック API に含まれるパッケージの書き出しを停止します。 | はい | はい |
| `repoinit` | すべての repoinit セクションの構文を確認します | はい | はい |
| `bundle-nativecode` | OSGI バンドルがネイティブコードをインストールしないことを検証します。 | はい | はい |
| `configuration-api` | 重要な OSGi 設定を検証します。 <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | はい | はい |
| `region-deprecated-api` | [非推奨の api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html?lang=ja) が使用されているかどうかを確認します <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | はい | はい |
| `artifact-rules` | バンドルやコンテンツパッケージなどの依存関係を検証して、アーティファクトの既知の問題を防ぎます。<p> </p>`[WARNING] [artifact-rules] com.adobe.acs:acs-aem-commons-bundle:5.0.4: Use at least version 5.0.10 (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | はい | はい |
| `aem-env-var` | 次の条件に従って環境変数の使用状況をチェックします。 [変数命名ガイド](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#variable-naming)<p> </p>`[ERROR] Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Value for property 'port' must not use env vars prefixed with INTERNAL_ or ADOBE_ (com.mysite1:my-site-1.all:1.0.0-SNAPSHOT\|com.mysite1:my-site-1.ui.config:1.0.0-SNAPSHOT)` | はい | はい |
| `content-package-validation` | filevault のバリデータを実行します。デフォルトでは、jackrabbit-docviewparser が有効になっており、デプロイ時にインストールされるパッケージ内にある xml の整形式のコンテンツ構文をチェックします。<p> </p>`[main] WARN org.apache.sling.feature.analyser.task.impl.CheckContentPackages - ValidationViolation: "jackrabbit-docviewparser: Invalid XML found: The reference to entity "se" must end with the ';' delimiter.", filePath=jcr_root/apps/somename/configs/com.adobe.test.Invalid.xml, nodePath=/apps/somename/configs/com.adobe.test.Invalid`<p> </p>修正するには、アナライザーで指定されたファイルで xml の問題を確認します。 | はい | はい |

{style=&quot;table-layout:auto&quot;}

## 既知の問題

Build Analyzer Maven プラグイン使用時の既知の問題のリストを以下に示します。

### ローカル SDK で Build Analyzer Maven プラグインを実行できない

バージョン `1.1.2` より前の Build Analyzer の Maven プラグインでローカル SDK を使用する場合、プラグインを実行すると、次のエラーが発生する可能性があります。この場合、プロジェクトを最新バージョンのプラグインに更新します。

```txt
[ERROR] Failed to execute goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse (default-analyse) on project mysite.analyse: Execution default-analyse of goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse failed: arraycopy: source index -1 out of bounds for char[65536] -> [Help 1]
```

AEM プロジェクトアーキタイプを使用してプロジェクトを設定する場合は、ルート Mavenの `pom.xml` のプロパティを次のように調整してください。

```xml
   ...
   <properties>
      ...
      <aemanalyser.version>1.1.2</aemanalyser.version> <!-- Make sure to use the latest release -->
      ...
   </properties>
```
