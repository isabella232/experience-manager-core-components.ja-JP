---
title: コアコンポーネントの使用
seo-title: コアコンポーネントの使用
description: 'null'
seo-description: 「独自のプロジェクトでコアコンポーネントを取得および実行するには、次の3つの手順があります。ダウンロードとインストール、プロキシコンポーネントの作成、コアスタイルの読み込み、テンプレートのコンポーネントの許可」を参照してください。
uuid: a1ef2ACF-8226-4510-838b- f5fae196f9f1
contentOwner: ユーザーは、
content-type: リファレンス
topic-tags: 開発中
products: SG_ PREPERNEMENTMANAGER/COREMENTS- new
discoiquuid: 1703a171-830c-477e- a34f-99caba841ec4
disttype: dist5
gnavtheme: light
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# コアコンポーネントの使用{#using-core-components}

基本的なプロジェクトの [コアコンポーネント](developing.md) を習得するには、以下の4つの手順を個別に説明します。

1. [ダウンロードとインストール](#download-and-install)
1. [プロキシコンポーネントの作成](#create-proxy-components)
1. [コアスタイルの読み込み](#load-the-core-styles)
1. [コンポーネントの有効化](#allow-the-components)

>[!NOTE]
>
>また、プロジェクト設定、編集可能なテンプレート、クライアントライブラリおよびコンポーネントの開発を使用して最初から開始する方法についての大まかな手順については、次のマルチパートチュートリアルを参照してください。\
>[AEM Sites の概要 - WKND チュートリアル](wknd-tutorial.md)

## ダウンロードとインストール {#download-and-install}

中核となるコンポーネントの背後にあるアイデアは柔軟性があります。新しいバージョンのコアコンポーネントをリリースすることで、アドビは新しい機能をより柔軟に配信できるようになります。開発者は、プロジェクトに統合することを選択するコンポーネントと、それらを更新する頻度を柔軟に設定できます。

このため、コアコンポーネントは、実稼働モード（サンプルコンテンツなし）で開始する場合、クイックスタートには含まれません。そのため、最初の手順は、GitHubから最新のコンテンツパッケージを [ダウンロードし、](https://github.com/adobe/aem-core-wcm-components/releases/latest) AEM環境にインストールすることです。

これを自動化する方法はいくつかありますが、インスタンスにコンテンツパッケージをすばやくインストールするには、Package Managerを使用することが必要です。パッケージ [のインストールを参照](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)してください。また、発行インスタンスも実行すると、そのパッケージを発行者に複製する必要があります。パッケージ [の複製を参照](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)してください。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## プロキシコンポーネントの作成 {#create-proxy-components}

[「プロキシコンポーネントパターン](guidelines.md#proxy-component-pattern) 」セクションで説明している理由により、コアコンポーネントをコンテンツから直接参照することはできません。そうしないと、すべてが非表示のコンポーネントグループ（ `.core-wcm``.core-wcm-form`または）に属しているので、直接エディターに表示されなくなります。

代わりに、サイト固有のコンポーネントを作成して、ページ作成者に表示するコンポーネントの名前とグループを定義し、それぞれのスーパータイプとしてコアコンポーネントを参照する必要があります。これらのサイト固有のコンポーネントは、「プロキシコンポーネント」と呼ばれることもあります。これらのコンポーネントは、何も含まれなくても、サイトに使用するコンポーネントのバージョンを定義するためにほぼ必要となります。[ただし、コアコンポーネント](customizing.md)をカスタマイズする場合、これらのプロキシコンポーネントは、マークアップと論理のカスタマイズに不可欠な役割を果たします。

したがって、サイトで使用する必要があるコアコンポーネントごとに、以下のことが必要です。

1. サイトのcomponentsフォルダー内に対応するプロキシコンポーネントを作成します。

   **「タイプのタイトルノードを作成**する」の下 `/apps/my-site/components` の例 `cq:Component`

1. スーパータイプを持つ対応するコアコンポーネントバージョンをポイントします。

   **例**次のプロパティを追加します。\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. コンポーネントのグループ、タイトル、およびオプションの説明を定義します。これらの値はプロジェクト固有で、コンポーネントが作成者に与える公開方法を示します。

   **例**次のプロパティを追加します。

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例えば、We. Retailリファレンスサイトの [タイトルコンポーネントを見てみましょう。](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)これは、その方法を構築したプロキシコンポーネントの好例です。

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

1. まだ実行していない場合は、サイトに必要なCSSおよびJSファイルをすべて含む [クライアントライブラリ](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html) を作成します。
1. サイトのクライアントライブラリで、必要なコアコンポーネントに依存性を追加します。これは `embed` 、プロパティを追加することで行います。

   例えば、すべてのv1Core Componentsのクライアントライブラリを含めるには、追加するプロパティは次のようになります。

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

次のセクションに移動する前に、プロキシコンポーネントとクライアントライブラリがAEM環境にデプロイされていることを確認してください。

## コンポーネントの許可 {#allow-the-components}

[テンプレートエディターでは、次の手順が実行](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)されます。

1. テンプレートエディターで、レイアウトコンテナを選択し、そのポリシーを開きます。
1. 許可されているコンポーネントのリストで、以前に作成したプロキシコンポーネントを選択します。これは、割り当てられているコンポーネントグループの下に表示されます。完了したら、変更を適用します。
1. オプションとして、デザインダイアログを持つコンポーネントの場合は、事前に設定できます。

これで問題ありません。編集したテンプレートから作成されたページで、新しく作成したコンポーネントを使用できるようになります。

**関連項目：**

* [コアコンポーネントのカスタマイズ](customizing.md) -コアコンポーネントのスタイル設定とカスタマイズ方法について説明します。
* [コンポーネントガイドライン](guidelines.md) -コアコンポーネントの実装パターンを学習します。
