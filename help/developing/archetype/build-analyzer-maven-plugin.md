---
title: AEM asCloud ServiceSDK Build Analyzer Maven Plugin
description: ローカルのMavenビルドアナライザープラグインに関するドキュメント
translation-type: tm+mt
source-git-commit: b95515dba74486add7f50bc8984f4358090e735c
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---


# AEM asCloud ServiceSDK Build Analyzer Maven Plugin {#maven-analyzer-plugin}

Cloud ServiceSDKビルドアナライザーMavenプラグインとしてのAEMは、様々なコンテンツパッケージプロジェクトの構造を分析します。

AEM mavenプロジェクトに [含める方法について詳しくは、](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) Mavenプラグインのドキュメントを参照してください。

以下の表は、この手順の一部として実行されるアナライザーについて説明しています。 <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| モジュール | 関数、例、トラブルシューティング | ローカル SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Mavenプロジェクトに含まれる他のバンドルのエクスポートパッケージ宣言で、すべてのOSGIバンドルのインポートパッケージ宣言が満たされているかどうかを確認します。 次のようなエラーが発生します。 <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>トラブルシューティングを行うには、パッケージを提供するバンドルがデプロイメントに含まれているかどうかを確認するか、エクスポートする予定のバンドルのマニフェストを調べて、誤った名前または誤ったバージョンが使用されたかどうかを確認します。 | はい | はい |
| `requirements-capabilities` | OSGIバンドルで行われたすべての要件宣言が、Mavenプロジェクトに含まれる他のバンドルの機能宣言によって満たされているかどうかを確認します。 次のようなエラーが発生します。 <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> トラブルシューティングを行うには、バンドルのマニフェストで、それが欠落している理由を判断する機能を宣言すると予想されるものを確認するか、必要なバンドルのマニフェストをチェックインして、その要件が正しいかを確認します。 | はい | はい |
| `bundle-content` | バンドルにSling-Initial-Contentで指定された初期コンテンツが含まれる場合に警告を表示します。これは、AEMでCloud Serviceクラスター環境として問題があります。 警告は次のようになります。 <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>初期コンテンツのrepointステートメントへの変換のトラブルシューティングについては、リポイントのドキュメントを参照してください。 | はい | はい |
| `bundle-resources` | バンドルにSling-Bundle-Resourcesヘッダーで指定されたリソースが含まれている場合に警告を表示します。これは、Cloud Serviceクラスタ環境としてAEMで問題を引き起こします。 警告は次のようになります。<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> リソースをrepointステートメントに変換する際のトラブルシューティングについては、リポイントのドキュメ [ント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init)を参照してください。 | はい | はい |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | これらのアナライザーは、Sling機能モデルに準拠するアーティファクトを作成する機能モデル変換プロセス [](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) （コンテンツパッケージに関連する詳細をチェックします）。 エラーが発生した場合は、Adobeカスタマーサポートに報告する必要があります。 | はい | はい |
| `api-regions-crossfeature-dups` | Cloud ServiceのパブリックAPIとしてAEMをオーバーライドするExport-package宣言が顧客のOSGIバンドルにないことを検証します<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>この問題を修正するには、AEMパブリックAPIに含まれるパッケージの書き出しを停止します。 | はい | はい |