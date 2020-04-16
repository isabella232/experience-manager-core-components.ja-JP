---
title: コアコンポーネントのカスタマイズ
description: コアコンポーネントは、シンプルなスタイル設定から高度な機能の再利用に至るまで、カスタマイズを容易に実施できるパターンをいくつか実装しています。
translation-type: ht
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# コアコンポーネントのカスタマイズ{#customizing-core-components}

[コアコンポーネント](overview.md)は、シンプルなスタイル設定から高度な機能の再利用に至るまで、カスタマイズを容易に実施できるパターンをいくつか実装しています。

## 柔軟なアーキテクチャ {#flexible-architecture}

コアコンポーネントは、柔軟性と拡張性を兼ね備えるように一から設計されました。アーキテクチャの概要を見れば、カスタマイズが可能な場所がわかります。

![コアコンポーネントのアーキテクチャ](/help/assets/screen_shot_2018-12-07at093742.png)

* [デザインダイアログ](/help/get-started/authoring.md#edit-and-design-dialogs)では、編集ダイアログで作成者が実行できる操作や実行できない操作を定義します。
* [編集ダイアログ](/help/get-started/authoring.md#edit-and-design-dialogs)では、使用可能なオプションのみを作成者に表示します。
* [Sling モデル](#customizing-the-logic-of-a-core-component)は、ビューのコンテンツ（テンプレート）を検証して準備します。
* [Sling モデルの結果](#customizing-the-logic-of-a-core-component)は、SPA ユースケース用として JSON 形式にシリアライズできます。
* [HTL は HTML のレンダリング](#customizing-the-markup)を、従来のサーバー側レンダリング用にサーバー側でおこないます。
* [HTML 出力](#customizing-the-markup)は、セマンティックかつアクセシブルで、検索エンジンに最適化されており、容易にスタイルを設定できます。

また、すべてのコアコンポーネントが[スタイルシステム](#styling-the-components)を実装しています。

## AEM プロジェクトアーキタイプ {#aem-project-archetype}

[AEM プロジェクトアーキタイプ](/help/developing/archetype/overview.md)は、最小限の Adobe Experience Manager プロジェクトを独自のプロジェクトの起点として作成します。これには、推奨のプロキシパターンを使用してコアコンポーネントのロジックと適切な実装をおこなうために、SlingModels を使用したカスタム HTL コンポーネントの例が含まれます。

## カスタマイズパターン {#customization-patterns}

### ダイアログのカスタマイズ {#customizing-dialogs}

コアコンポーネントのダイアログ（[デザインダイアログ、編集ダイアログ](/help/get-started/authoring.md)のいずれか）で利用可能な設定オプションのカスタマイズが必要になることがあります。

各ダイアログには一貫したノード構造があります。継承する側のコンポーネントでこの構造を複製することをお勧めします。そうすれば、[Sling Resource Merger](https://helpx.adobe.com/jp/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) や[非表示条件](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/hide-conditions.html)を使用して元のダイアログのセクションの非表示、置換または並べ替えをおこなうことができます。複製する構造は、タブ項目ノードレベルまでのすべて、と定義されます。

現在のバージョンのダイアログに対する変更との互換性を完全に持たせるには、タブ項目レベル配下にある構造に対して変更（非表示、追加、置換、並べ替えなど）を加えないことが非常に重要となります。代わりに、`sling:hideResource` プロパティ（[Sling Resource Merger のプロパティ](https://helpx.adobe.com/jp/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)を参照）を使用して親のタブ項目を非表示にし、カスタム設定フィールドを含む新しいタブ項目を追加してください。必要に応じて、`sling:orderBefore` を使用してタブ項目を並べ替えることもできます。

以下の図では、推奨されるダイアログの構造と、前述した、継承される側のタブを非表示にして置換する方法を示しています。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="https://www.jcp.org/jcr/1.0"
          xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
          xmlns:granite="https://www.adobe.com/jcr/granite/1.0"
          jcr:primaryType="nt:unstructured">
    <content jcr:primaryType="nt:unstructured">
        <items jcr:primaryType="nt:unstructured">
            <tabs jcr:primaryType="nt:unstructured">
                <items jcr:primaryType="nt:unstructured">
                        <originalTab
                                jcr:primaryType="nt:unstructured"
                                sling:hideResource="true"/>
                        </originalTab>
                        <myTab
                               jcr:primaryType="nt:unstructured"
                               jcr:title="My Tab"
                               sling:resourceType="granite/ui/components/coral/foundation/container"/>
                               <!-- myTab content -->
                        </myTab>
                </items>
            </basic>
        </items>
    </content>
</jcr:root>
```

### コアコンポーネントのロジックのカスタマイズ {#customizing-the-logic-of-a-core-component}

コアコンポーネントのビジネスロジックは、Sling モデルで実装されています。このロジックは Sling 委任パターンを使用して拡張できます。

例えば、タイトルコアコンポーネントは、要求されたリソースの `jcr:title` プロパティを使用してタイトルのテキストを提供します。`jcr:title` プロパティが定義されていない場合は、現在のページのタイトルへのフォールバックが実行されます。ここで、現在のページのタイトルを常に表示するように動作を変更したいとします。

コアコンポーネントのモデルの実装が非公開になっているので、委任パターンを使用して拡張する必要があります。

```java
@Model(adaptables = SlingHttpServletRequest.class,
       adapters = Title.class,
       resourceType = "myproject/components/pageHeadline")
public class PageHeadline implements Title {
    @ScriptVariable private Page currentPage;
    @Self @Via(type = ResourceSuperType.class)
    private Title title;
    @Override public String getText() {
        return currentPage.getTitle();
    }
    @Override public String getType() {
        return title.getType();
    }
}
```

委任パターンについて詳しくは、コアコンポーネント GitHub Wiki 記事の「[Delegation Pattern for Sling Models](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)」を参照してください。

### マークアップのカスタマイズ {#customizing-the-markup}

高度なスタイル設定では、マークアップ構造が異なるコンポーネントが必要となることがあります。

変更が必要な HTL ファイルをコアコンポーネントからプロキシコンポーネントにコピーすれば、簡単に実行できます。

パンくずコアコンポーネントの例を再度取り上げます。そのマークアップ出力をカスタマイズするには、`breadcrumb.html` ファイルを、パンくずコアコンポーネントを指す `sling:resourceSuperTypes` を含むサイト固有のコンポーネントにコピーする必要があります。

### コンポーネントのスタイル設定 {#styling-the-components}

カスタマイズの最初の形式は、CSS スタイルを適用することです。

これが簡単になるよう、コアコンポーネントではセマンティックなマークアップをレンダリングし、[Bootstrap](https://getbootstrap.com/) を参考にして標準化された命名規則に従います。また、個々のコンポーネントのスタイルを容易にターゲット化および名前空間化できるよう、各コアコンポーネントは「`cmp`」および「`cmp-<name>`」クラスを持つ DIV 要素内にラップされます。

例えば、v1 パンくずコアコンポーネントの HTL ファイル [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html) を確認すると、要素出力の階層が `ol.breadcrumb > li.breadcrumb-item > a` となっていることがわかります。そのため、CSS ルールをそのコンポーネントのパンくずクラスのみに適用するには、次のようにすべてのルールを名前空間化する必要があります。

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

さらに、各コアコンポーネントは AEM [スタイルシステムの機能](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/sites/authoring/features/style-system.html)を活用しています。スタイルシステムを使用すれば、テンプレート作成者は、ページ作成者がコンポーネントに適用できる追加の CSS クラス名を定義することができます。また、テンプレートごとに、許可されるコンポーネントスタイルのリストと、いずれかのスタイルを同じ種類のすべてのコンポーネントにデフォルトで適用するかどうかを定義できます。

## アップグレード時のカスタマイズの互換性 {#upgrade-compatibility-of-customizations}

次の 3 種類のアップグレードが可能です。

* AEM のバージョンのアップグレード
* コアコンポーネントの新しいマイナーバージョンへのアップグレード
* コアコンポーネントのメジャーバージョンへのアップグレード

一般に、AEM を新しいバージョンにアップグレードしても、コンポーネントが移行先の新しい AEM バージョンもサポートし、[廃止または削除](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)された API がカスタマイズで使用されていなければ、コアコンポーネントやおこなったカスタマイズには何の影響もありません。

コアコンポーネントを新しいメジャーバージョンに切り替えずにアップグレードしても、このページで説明したカスタマイズパターンが使用されている限り、カスタマイズには何の影響もありません。

コアコンポーネントを新しいメジャーバージョンに切り替えた場合、互換性が保たれるのはコンテンツの構造のみであり、カスタマイズはリファクタリングが必要となることがあります。コンポーネントバージョンごとに明瞭な変更ログが公開され、このページで説明した種類のカスタマイズに影響する変更を強調します。

## カスタマイズのサポート {#support-of-customizations}

他の AEM コンポーネントの場合と同様に、カスタマイズに関して注意すべき点がいくつかあります。

1. **コアコンポーネントのコードを直接変更しないでください。**

   そうしてしまうと、コアコンポーネントが完全にサポート対象外となり、将来のコンポーネントのアップデートが困難になってしまいます。代わりに、このページで説明したカスタマイズ方法を使用してください。

1. **カスタムコードはユーザー自身の責任になります。**

   サポートプログラムではカスタムコードはカバーされません。また、[記載どおりに使用](/help/get-started/using.md)された標準のコアコンポーネントで再現できない問題が報告されても、その問題はサポート対象外となります。

1. **廃止された機能や削除された機能を確認してください。**

   新しい AEM バージョンにアップグレードするたびに、[廃止された機能と削除された機能](https://docs.adobe.com/content/help/ja-JP/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)のページに目を通し、使用中のすべての API がまだ有効であることを確認してください。

[コアコンポーネントのサポート](overview.md#core-component-support)の節も参照してください。

**関連項目：**

* [コアコンポーネントの使用](/help/get-started/using.md) - 独自のプロジェクトにコアコンポーネントを導入する方法について説明します。
* [コンポーネントのガイドライン](guidelines.md) - コアコンポーネントの実装パターンについて説明します。
