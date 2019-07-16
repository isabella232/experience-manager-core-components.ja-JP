---
title: コアコンポーネントの使用
seo-title: コアコンポーネントの使用
description: 'null'
seo-description: '"独自のプロジェクトにコアコンポーネントを導入するには、4 つの手順（ダウンロードとインストール、プロキシコンポーネントの作成、コアスタイルの読み込み、テンプレートでのコンポーネントの有効化）に従います。"'
uuid: a1ef2acf-8226-4510-838b-f5fae196f9f1
contentOwner: ユーザー
content-type: reference
topic-tags: developing
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 1703a171-830c-477e-a34f-99caba841ec4
disttype: dist5
gnavtheme: light
index: y
internal: n
snippet: y
translation-type: ht
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# コアコンポーネントの使用{#using-core-components}

独自のプロジェクトに[コアコンポーネント](developing.md)を導入するには、次の 4 つの手順に従います。以下では、それぞれの手順について詳しく説明します。

1. [ダウンロードとインストール](#download-and-install)
1. [プロキシコンポーネントの作成](#create-proxy-components)
1. [コアスタイルの読み込み](#load-the-core-styles)
1. [コンポーネントの有効化](#allow-the-components)

>[!NOTE]
>
>また、プロジェクト設定、コアコンポーネント、編集可能テンプレート、クライアントライブラリおよびコンポーネント開発にゼロから取り組む方法についての広範な手順については、複数パートから成る次のチュートリアルを参照してください。\
>[AEM Sites の概要 - WKND チュートリアル](wknd-tutorial.md)

## ダウンロードとインストール {#download-and-install}

コアコンポーネントの背後にある基本的な考え方は柔軟性です。新しいバージョンのコアコンポーネントを頻繁にリリースすることで、アドビは新しい機能をより柔軟に配信できるようになります。一方、開発者は、プロジェクトに統合するコンポーネントとそれらの更新頻度を柔軟に設定できます。

このため、実稼働モード（サンプルコンテンツなし）で開始する場合、コアコンポーネントはクイックスタートには含まれません。したがって、[リリースされた最新のコンテンツパッケージを GitHub からダウンロード](https://github.com/adobe/aem-core-wcm-components/releases/latest)して AEM 環境にインストールすることが最初の手順になります。

これを自動化する方法はいくつかありますが、コンテンツパッケージをインスタンスにすぐにインストールするには、パッケージマネージャーを使用する方法が最も簡単です。詳しくは、[パッケージのインストール](https://helpx.adobe.com/jp/experience-manager/6-5/sites/administering/using/package-manager.html)を参照してください。また、パブリッシュインスタンスも実行する場合は、そのパブリッシュインスタンスにパッケージをレプリケートする必要があります。詳しくは、[パッケージのレプリケーション](https://helpx.adobe.com/jp/experience-manager/6-5/sites/administering/using/package-manager.html)を参照してください。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## プロキシコンポーネントの作成 {#create-proxy-components}

[プロキシコンポーネントパターン](guidelines.md#proxy-component-pattern)で説明している理由により、コアコンポーネントをコンテンツから直接参照することは禁止されています。直接参照を避けるために、すべてのコアコンポーネントは非表示コンポーネントグループ（`.core-wcm` または `.core-wcm-form`）に属しているので、エディターには直接表示されません。

代わりに、サイト固有のコンポーネントを作成する必要があります。そのコンポーネントで、ページ作成者に表示する適切なコンポーネントの名前とグループを定義し、それぞれのスーパータイプとしてコアコンポーネントを参照します。これらのサイト固有のコンポーネントは、「プロキシコンポーネント」と呼ばれることもあります。これらのコンポーネントは、コンテンツが不要で、主に、サイトに使用するコンポーネントのバージョンを定義する役目を果たすからです。ただし、[コアコンポーネント](customizing.md)をカスタマイズする場合、これらのプロキシコンポーネントはマークアップとロジックのカスタマイズに不可欠です。

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

例えば、[We.Retail 参照サイトのタイトルコンポーネント](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)をご覧ください。これは、このような方法で作成されるプロキシコンポーネントの好例です。

## コアスタイルの読み込み {#load-the-core-styles}

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:57:16.414-0400

Styles is odd in that most Core Components do not have CSS; very few even have structural CSS (breadcrumbs, list) It may be more apt to title this section: Load the Core JavaScript and CSS or Load the Core Client Libraries ?

 -->

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:41:37.115-0400

This section seems to cover the "sites" clientlibs for core components; Do we need a section for ensuring the editor clientlibs are loaded in the Page Editor? Pending: https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/issues/15

 -->

<!-- 

Comment Type: annotation
Last Modified By: cotescu
Last Modified Date: 2018-03-09T10:45:52.812-0500

Load the Core Client Libraries sounds way better

 -->

1. サイトに必要な CSS および JS ファイルをすべて含んだ[クライアントライブラリ](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/clientlibs.html)を作成します（まだ作成していない場合）。
1. サイトのクライアントライブラリで、必要なコアコンポーネントへの依存関係を追加します。これをおこなうには、`embed` プロパティを追加します。

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

## コンポーネントの有効化 {#allow-the-components}

[テンプレートエディター](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/templates.html)で以下をおこないます。

1. テンプレートエディターで、レイアウトコンテナを選択し、そのポリシーを開きます。
1. 「許可されるコンポーネント」のリストで、作成済みのプロキシコンポーネントを選択します。これは、プロキシコンポーネントに割り当てられているコンポーネントグループの下に表示されます。操作が完了したら、変更を適用します。
1. オプションとして、デザインダイアログを持つコンポーネントの場合は、事前に設定できます。

これで作業は完了です。編集したテンプレートから作成したページで、新しく作成したコンポーネントを使用できるようになります。

**関連項目：**

* [コアコンポーネントのカスタマイズ](customizing.md) - コアコンポーネントのスタイル設定とカスタマイズの方法について説明します。
* [コンポーネントのガイドライン](guidelines.md) - コアコンポーネントの実装パターンについて説明します。
