---
title: コアコンポーネントの使用
description: 「独自のプロジェクトにコアコンポーネントを導入するには、4 つの手順（ダウンロードとインストール、プロキシコンポーネントの作成、コアスタイルの読み込み、テンプレートでのコンポーネントの有効化）に従います。」
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '977'
ht-degree: 100%

---

# コアコンポーネントの使用{#using-core-components}

独自のプロジェクトにコアコンポーネントを導入するには、次の 4 つの手順に従います。以下では、それぞれの手順について詳しく説明します。

1. [ダウンロードとインストール](#download-and-install)
1. [プロキシコンポーネントの作成](#create-proxy-components)
1. [コアスタイルの読み込み](#load-the-core-styles)
1. [コンポーネントの有効化](#allow-the-components)

>[!TIP]
>
>プロジェクト設定、コアコンポーネント、編集可能テンプレート、クライアントライブラリおよびコンポーネント開発にゼロから取り組む方法についての広範な手順については、複数パートから成る次のチュートリアルを参照してください。\
>[AEM Sites の概要 - WKND チュートリアル](https://docs.adobe.com/content/help/ja-JP/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>[AEM プロジェクトアーキタイプ](/help/developing/archetype/overview.md)を使用する場合、コアコンポーネントは、アドビのベストプラクティスの推奨事項に基づいて、プロジェクトに自動的に組み込まれます。

## ダウンロードとインストール {#download-and-install}

コアコンポーネントの背後にある基本的な考え方は柔軟性です。新しいバージョンのコアコンポーネントを頻繁にリリースすることで、アドビは新しい機能をより柔軟に配信できるようになります。一方、開発者は、プロジェクトに統合するコンポーネントとそれらの更新頻度を柔軟に設定できます。この結果、AEM とコアコンポーネントの両方で別々のリリースプロセスになります。

したがって、AEM as a Cloud Service を実行しているか、オンプレミスの AEM を実行しているかによって、インストール手順が決まります。

### AEM as a Cloud Service {#aemaacs}

手順 1 はありません。AEM as a Cloud Service には、コアコンポーネントの最新バージョンが自動的に搭載されています。AEM as a Cloud Service では AEM の最新機能が提供されますが、同時に、コアコンポーネントの最新バージョンも自動的に使用できます。

AEM as a Cloud Service でコアコンポーネントを使用する際には、次の点に留意してください。

* コアコンポーネントは `/libs` に含まれています。
* コアコンポーネントが `/apps` にも含まれている場合は、プロジェクトビルドパイプラインでログに警告が出力され、プロジェクトの一部として組み込まれているバージョンが無視されます。
   * 今後のリリースでは、コアコンポーネントを再度組み込むと、パイプラインのビルドが失敗します。
* 既にプロジェクトが `/apps` にコアコンポーネントを含んでいる場合は、[プロジェクトの調整が必要になる可能性があります。](/help/developing/overview.md#via-aemaacs)
* 今はコアコンポーネントが `/libs` に含まれるようになっていますが、同じパスのオーバーレイを `/apps` に作成することはお勧めしません。コンポーネントの一部をカスタマイズする必要がある場合は、代わりに[プロキシコンポーネントパターン](/help/developing/guidelines.md#proxy-component-pattern)を使用してください。

### AEM 6.5 以前 {#aem-65}

実稼動モード（サンプルコンテンツなし）で開始する場合、コアコンポーネントはクイックスタートには含まれません。したがって、[リリースされた最新のコンテンツパッケージを GitHub からダウンロード](https://github.com/adobe/aem-core-wcm-components/releases/latest)して AEM 環境にインストールすることが最初の手順になります。

これを自動化する方法はいくつかありますが、コンテンツパッケージをインスタンスにすぐにインストールするには、パッケージマネージャーを使用する方法が最も簡単です。詳しくは、[パッケージのインストール](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)を参照してください。また、パブリッシュインスタンスも実行する場合は、そのパブリッシュインスタンスにパッケージをレプリケートする必要があります。詳しくは、[パッケージのレプリケーション](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)を参照してください。

## プロキシコンポーネントの作成 {#create-proxy-components}

[プロキシコンポーネントパターン](/help/developing/guidelines.md#proxy-component-pattern)で説明している理由により、コアコンポーネントをコンテンツから直接参照することは禁止されています。直接参照を避けるために、すべてのコアコンポーネントは非表示コンポーネントグループ（`.core-wcm` または `.core-wcm-form`）に属しているので、エディターには直接表示されません。

代わりに、サイト固有のコンポーネントを作成する必要があります。そのコンポーネントで、ページ作成者に表示する適切なコンポーネントの名前とグループを定義し、それぞれのスーパータイプとしてコアコンポーネントを参照します。これらのサイト固有のコンポーネントは、「プロキシコンポーネント」と呼ばれることもあります。これらのコンポーネントは、コンテンツが不要で、主に、サイトに使用するコンポーネントのバージョンを定義する役目を果たすからです。ただし、[コアコンポーネント](/help/developing/customizing.md)をカスタマイズする場合、これらのプロキシコンポーネントはマークアップとロジックのカスタマイズに不可欠です。

そのため、サイトに使用する必要があるコアコンポーネントごとに、以下が必要になります。

1. 対応するプロキシコンポーネントをサイトの components フォルダー内に作成します。

   **例** - `/apps/my-site/components` 内に `cq:Component` タイプのタイトルノードを作成します

1. 対応するコアコンポーネントバージョンをスーパータイプで参照します。

   **例** - 次のプロパティを追加します。\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. コンポーネントのグループ、タイトルのほか、オプションで説明を定義します。これらの値はプロジェクト固有で、作成者に対するコンポーネントの表示を指定します。

   **例** - 次のプロパティを追加します。

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例えば、[WKND サイトのタイトルコンポーネント](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)をご覧ください。これは、このような方法で作成されるプロキシコンポーネントの好例です。

## コアスタイルの読み込み {#load-the-core-styles}

1. サイトに必要な CSS および JS ファイルをすべて含んだ[クライアントライブラリ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=ja)を作成します（まだ作成していない場合）。
1. サイトのクライアントライブラリで、必要なコアコンポーネントへの依存関係を追加します。それには、`embed` プロパティを追加します。

   例えば、すべての v1 コアコンポーネントのクライアントライブラリを組み込むには、追加するプロパティは次のようになります。

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

次の手順に進む前に、プロキシコンポーネントとクライアントライブラリが AEM 環境にデプロイされていることを確認してください。

## コンポーネントの許可 {#allow-the-components}

[テンプレートエディター](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/templates.html)では、次の手順を実行します。

1. テンプレートエディターで、レイアウトコンテナを選択し、そのポリシーを開きます。
1. 「許可されるコンポーネント」のリストで、作成済みのプロキシコンポーネントを選択します。これは、プロキシコンポーネントに割り当てられているコンポーネントグループの下に表示されます。操作が完了したら、変更を適用します。
1. オプションとして、デザインダイアログを持つコンポーネントの場合は、事前に設定できます。

これで作業は完了です。編集したテンプレートから作成したページで、新しく作成したコンポーネントを使用できるようになります。

**関連項目：**

* [コアコンポーネントのカスタマイズ](/help/developing/customizing.md) - コアコンポーネントのスタイル設定とカスタマイズの方法について説明します。
* [コンポーネントのガイドライン](/help/developing/guidelines.md) - コアコンポーネントの実装パターンについて説明します。
