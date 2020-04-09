---
title: AEM プロジェクトアーキタイプ
description: AEM ベースのアプリケーション用のプロジェクトテンプレート
translation-type: tm+mt
source-git-commit: 2faa092a075ab0512e9bd5654884534936c0ad53

---


# AEM プロジェクトアーキタイプ {#aem-project-archetype}

AEMプロジェクトのアーキタイプは、Webサイトの出発点として、最小限のベストプラクティスベースのAdobe Experience Manager(AEM)プロジェクトを作成するMavenテンプレートです。

>[!TIP]
>
>最新の AEM プロジェクトアーキタイプは[ GitHub で入手できます](https://github.com/adobe/aem-project-archetype)。

## リソース {#resources}

* **アーキタイプのドキュメント(このドキュメント):** アーキテクチャとその様々なモジュールの概要です。
   * **[アーキタイプの使用：](using.md)**アーキタイプと使用可能なモジュールの使用に関する詳細
   * **[ui.frontend:](uifrontend.md)**フロントエンドビルドモジュールの使用方法
* 次のチュートリアルは、このアーキタイプに基づいています。
   * **[WKNDサイト：](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**新しいWebサイトを開始する方法を説明します。
   * **[WKND単一ページアプリ：](https://helpx.adobe.com/jp/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)**AEMで完全に認証可能なReactまたはAngular Webアプリを作成する方法を説明します。

## 機能 {#features}

* **ベストプラクティス：** アドビの最新の推奨プラクティスをすべて使用して、サイトをブートストラップします。
* **低コード：** テンプレートの編集、コンテンツの作成、CSSのデプロイを行うと、サイトの運用準備が整います。
* **クラウド対応：** 必要に応じて、 [AEMをクラウドサービスとして使用し](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html) 、数日で運用を開始し、スケーラビリティとメンテナンスを容易にします。
* **ディスパッチャー：** プロジェクトは、速度とセキュリティを保証する [Dispatcher設定](https://docs.adobe.com/content/help/ja-JP/experience-manager-dispatcher/using/dispatcher.html) でのみ完了します。
* **マルチサイト：** 必要に応じて、アーキタイプによって、複数言語および複数 [領域の設定用のコンテンツ構造が生成されます](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **コアコンポーネント：** 作成者は、標準化されたコンポーネントの汎用セットを使用して、ほぼ [すべてのレイアウトを作成できま](/help/introduction.md)す。
* **編集可能なテンプレート：** ほとんどすべてのテン [プレートをコードなしで](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)アセンブリし、作成者が編集できる内容を定義します。
* **レスポンシブレイアウト：** テンプレートまたは個々のページで、定義さ [れたブレークポイントの要素の折り返し](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/responsive-layout.html) 方法を定義します。
* **ヘッダーとフッター：** コンポーネントの [ローカライゼーション機能を使用し、コードなしでアセンブリし](https://docs.adobe.com/content/help/ja-JP/experience-manager-core-components/using/get-started/localization.html)、
* **Style System:** 作成者が異なるスタイルを適用できるようにして、カスタムコンポ [ーネントを作成しない](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) でください。
* **フロントエンドビルド：** フロントエンドデバイスは、AEMペ [ージをモックし](uifrontend.md#webpack-dev-server) 、Webpack、TypeScript [](uifrontend.md) 、およびSASSを使用してクライアントライブラリを構築できます。
* **WebApp-Ready:**[React](uifrontend-react.md) またはAngular [を使用するサイトの場合は、](uifrontend-angular.md)SDK SDKを使用して、appSpaのコンテキ [](https://docs.adobe.com/content/help/en/experience-manager-64/developing/headless/spas/spa-architecture.html)[](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)ストオーサリングで保持します。
* **コード例：** HelloWorldコンポーネントと、サンプルモデル、サーブレット、フィルター、スケジューラー。
* **オープンソース：** 必要に応じて何かが変わった場合は、改善点 [にご協力](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) ください。

## 使用方法

プロジェクトを生成するには、次のコマンドラインを必要に応じて調整します。

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.granite.archetypes \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=23 \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* AEMをク `aemVersion=cloud` ラウ [ドサービスとして設定](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html);\
   アドビ `aemVersion=6.5.0` の [Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)、またはオンプレミスに設定します。
コアコンポーネントの依存関係は、非クラウドAEMバージョンに対してのみ追加されます。これは、コアコンポーネントがAEM用にクラウドサービスとしてOOTBを提供するためです。
* Webサイトのタ `appTitle="My Site"` イトルとコンポーネントグループを定義するように調整します。
* Maven artifactId、 `appId="mysite"` コンポーネント、設定、コンテンツのフォルダー名、およびクライアントライブラリ名を定義するように調整します。
* Maven groupIdとJava `groupId="com.mysite"` ソースパッケージを定義するように調整します。
* 使用可能なプロパティのリストを参照して、調整するプロパティの数が多いかどうかを確認します。

## 使用可能なプロパティ

| 名前 | デフォルト値は | 説明 |
--------------------------|----------------|--------------------
| `appTitle` |  | アプリのタイトル。Webサイトのタイトルやコンポーネントグループ( `"My Site"`)。 |
| `appId` |  | 技術的な名前。コンポーネント、設定、コンテンツのフォルダー名、クライアントライブラリ名(例： `"mysite"`)。 |
| `artifactId` | *`${appId}`* | Base Maven artifact ID (e.g. `"mysite"`). |
| `groupId` |  | Base Maven group ID (e.g. `"com.mysite"`). |
| `package` | *`${groupId}`* | Javaソースパッケージ(例： `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | プロジェクトのバージョン(例： `1.0-SNAPSHOT`)。 |
| `aemVersion` | `6.5.0` | ターゲットAEMバージョン(クラウドサ `cloud` ービ [スとしてのAEM用に指定可能](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/landing/home.html)。また `6.5.0`は、 `6.4.4`Adobe Managed Services `6.3.3`[](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) またはオンプレミスの場合)。 |
| `sdkVersion` | `latest` | `aemVersion=cloud` SDKバージョ [ンを指定できる場合](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (例： `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | の値（またはの可能性）に応じて、クラウドまたはAMS/オンプレミスのディスパッチャー設 `aemVersion` 定を含め `y` ます `n`。 |
| `frontendModule` | `none` | クライアントライブラリ（通常のサイトの場合と、通常のサイトの場合）を生成するWebpackフロントエンドビル `general` ドモジュール `none` が含まれています。は、 `angular` または `react`[SPAエディターを実装する単一ページアプリ](https://docs.adobe.com/content/help/en/experience-manager-65/developing/headless/spas/spa-overview.html)用)。 |
| `languageCountry` | `en_us` | Language and country code to create the content structure from (e.g. `en_us`). |
| `singleCountry` | `y` | 言語マスターのコンテンツ構造を含めます(または `y`のいずれか `n`)。 |
| `includeExamples` | `y` | コンポーネン [トライブラリ](https://www.aemcomponents.dev/) のサンプルサイトを含めます( `y`または `n`)。 |
| `includeErrorHandler` | `n` | インスタンス全体に対してグローバルに表示されるカスタム404応答ページを含めます(または `y` 可能 `n`です)。 |

## システム要件

| アーキタイプ | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | AEM 6.3 | Java SE | Maven |
---------|---------|---------|---------|---------|---------|---------
| [23](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-23) | 継続的 | 6.5.0.0 以上 | 6.4.4.0 以上 | 6.3.3.4 以上 | 8、11 | 3.3.9+ |

AEMのローカル開発環境を、クラウドサ [ービスSDKまたは古いバージョンのAEM](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)[として設定します](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

### 既知の問題

When running on Windows and generating the dispatcher configuration, you should be running in an elevated command prompt or the Windows Subsystem for Linux (see [#329](https://github.com/adobe/aem-project-archetype/issues/329)).

インタラクティブモードで(パラメータなしで `-B` )アーキタイプを実行する場合、最終確認を閉じない限り、デフォルト値を持つプロパティは変更できません。その後、質問にデフォルト値を持つプロパティを含めて質問を繰り返します(詳しくは[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) を参照)。

## 参考情報 {#further-reading}

利点、オプション、およびそのモジュールの動作方法を含む、アーキタイプの使用方法の詳細については、「アーキタイプの使用」 [ドキュメントを参照してください。](using.md)