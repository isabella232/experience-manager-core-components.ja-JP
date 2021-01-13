---
title: AEM as a Cloud Service SDK Build Analyzer Maven プラグイン
description: ローカルの Maven Build Analyzer プラグインに関するドキュメント
translation-type: ht
source-git-commit: b95515dba74486add7f50bc8984f4358090e735c
workflow-type: ht
source-wordcount: '416'
ht-degree: 100%

---


# AEM as a Cloud Service SDK Build Analyzer Maven プラグイン {#maven-analyzer-plugin}

AEM as a Cloud Service SDK Build Analyzer Maven プラグインは、様々なコンテンツパッケージプロジェクトの構造を分析します。

AEM Maven プロジェクトに含める方法については、[Maven プラグインのドキュメント](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)を参照してください。

以下の表は、この手順の一部として実行されるアナライザーについて説明しています。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| モジュール | 機能、例、トラブルシューティング | ローカル SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Maven プロジェクトに含まれる他のバンドルのエクスポートパッケージ宣言で、すべての OSGI バンドルのインポートパッケージ宣言が満たされているかどうかを確認します。次のようなエラーが発生します。 <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>トラブルシューティングをおこなうには、パッケージを提供するバンドルがデプロイメントに含まれているかどうかを確認するか、エクスポートする予定のバンドルのマニフェストを調べて、誤った名前または誤ったバージョンが使用されたかどうかを確認します。 | 可 | 可 |
| `requirements-capabilities` | OSGI バンドルでおこなわれたすべての要件宣言が、Maven プロジェクトに含まれる他のバンドルでの機能宣言によって満たされているかどうかを確認します。次のようなエラーが発生します。 <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> トラブルシューティングをおこなうには、バンドルのマニフェストで、それが欠落している理由を判断する機能を宣言すると予想されるものを確認するか、必要なバンドルのマニフェストをチェックインして、その要件が正しいかを確認します。 | 可 | 可 |
| `bundle-content` | バンドルに Sling-Initial-Content で指定された初期コンテンツが含まれる場合に警告を表示します。これは、AEM as a Cloud Service クラスター環境では問題となります。警告は次のようになります。 <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>初期コンテンツの repoinit ステートメントへの変換のトラブルシューティングについては、Repoinit のドキュメントを参照してください。 | 可 | 可 |
| `bundle-resources` | バンドルに Sling-Bundle-Resources ヘッダーで指定されたリソースが含まれている場合に警告を表示します。これは、AEM as a Cloud Service クラスターでは問題となります。警告は次のようになります。<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> リソースを repoinit ステートメントに変換する際のトラブルシューティングについては [Repoinit ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=ja#repo-init)を参照してください。 | 可 | 可 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | これらのアナライザーは、Sling 機能モデルに準拠するアーティファクトを作成する[コンテンツパッケージを機能モデル変換プロセス](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=ja#deploying)に関連付けた詳細をチェックします。エラーが発生した場合は、Adobe カスタマーサポートに報告する必要があります。 | 可 | 可 |
| `api-regions-crossfeature-dups` | AEM as a Cloud Service のパブリック API をオーバーライドする Export-package 宣言が顧客の OSGI バンドルにないことを検証します。<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>この問題を修正するには、AEM パブリック API に含まれるパッケージの書き出しを停止します。 | 可 | 可 |