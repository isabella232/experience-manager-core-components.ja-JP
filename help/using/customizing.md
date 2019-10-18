---
title: コアコンポーネントのカスタマイズ
seo-title: コアコンポーネントのカスタマイズ
description: コアコンポーネントは、シンプルなスタイル設定から高度な機能の再利用に至るまで、カスタマイズを容易に実施できるパターンをいくつか実装しています。
seo-description: AEM コアコンポーネントは、シンプルなスタイル設定から高度な機能の再利用に至るまで、カスタマイズを容易に実施できるパターンをいくつか実装しています。
uuid: 38d22b85-4867-4716-817a-10ee2f8de6f5
contentOwner: ユーザー
content-type: reference
topic-tags: developing
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 3c9e0ade-1ce0-4e34-ae04-8da63f9b6c4f
translation-type: tm+mt
source-git-commit: e3b5eb14a8172c2172b936dd8713befd17f17524

---


# コアコンポーネントのカスタマイズ{#customizing-core-components}

[コアコンポーネント](developing.md)は、シンプルなスタイル設定から高度な機能の再利用に至るまで、カスタマイズを容易に実施できるパターンをいくつか実装しています。

## 柔軟なアーキテクチャ {#flexible-architecture}

コアコンポーネントは、柔軟性と拡張性を兼ね備えるように一から設計されました。アーキテクチャの概要を見れば、カスタマイズが可能な場所がわかります。

![コアコンポーネントのアーキテクチャ](assets/screen_shot_2018-12-07at093742.png)

* [デザインダイアログ](authoring.md#edit-and-design-dialogs)では、編集ダイアログで作成者が実行できる操作や実行できない操作を定義します。
* [編集ダイアログ](authoring.md#edit-and-design-dialogs)では、使用可能なオプションのみを作成者に表示します。
* [Sling モデル](#customizing-the-logic-of-a-core-component)は、ビューのコンテンツ（テンプレート）を検証して準備します。
* [Sling モデルの結果](#customizing-the-logic-of-a-core-component)は、SPA ユースケース用として JSON 形式にシリアライズできます。
* [HTL は HTML のレンダリング](#customizing-the-markup)を、従来のサーバー側レンダリング用にサーバー側でおこないます。
* [HTML 出力](#customizing-the-markup)は、セマンティックかつアクセシブルで、検索エンジンに最適化されており、容易にスタイルを設定できます。

また、すべてのコアコンポーネントが[スタイルシステム](customizing.md)を実装しています。

## AEM プロジェクトアーキタイプ {#aem-project-archetype}

[AEM Project Archetypeは、推奨のプロキシパターンを使用したコアコンポーネントのロジックと適切な実装のためのSlingModelsを使用したカスタムHTLコンポーネントのhelloworld例を含む、最小限のAdobe Experience Managerプロジェクトを独自のプロジェクトの起点として作成します。](archetype.md)

## カスタマイズパターン {#customization-patterns}

### ダイアログのカスタマイズ {#customizing-dialogs}

コアコンポーネントのダイアログ（[デザインダイアログ、編集ダイアログ](authoring.md)のいずれか）で利用可能な設定オプションのカスタマイズが必要になることがあります。

各ダイアログには一貫したノード構造があります。It is recommended that this structure is replicated in an inheriting component so that [Sling Resource Merger](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) and [Hide Conditions](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) can be used to hide, replace, or reorder sections of the original dialog. 複製する構造は、タブ項目ノードレベルまでのすべて、と定義されます。

現在のバージョンのダイアログに対して行われる変更との互換性を完全に持たせるには、タブ項目レベルの下にある構造に対して変更（非表示、追加、置換、並べ替えなど）をおこなわないことが非常に重要となります。Instead, a tab item from the parent should be hidden via the `sling:hideResource` property (see [Sling Resource Merger Properties](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)), and new tab items added that contain the bespoke configuration fields. 必要に応じて、`sling:orderBefore` を使用してタブ項目を並べ替えることもできます。

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

For further details about the delegation pattern see the Core Components GitHub Wiki article [Delegation Pattern for Sling Models](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models).

### マークアップのカスタマイズ {#customizing-the-markup}

高度なスタイル設定では、マークアップ構造が異なるコンポーネントが必要となることがあります。

変更が必要な HTL ファイルをコアコンポーネントからプロキシコンポーネントにコピーすれば、簡単に実行できます。

パンくずコアコンポーネントの例を再度取り上げます。そのマークアップ出力をカスタマイズするには、`breadcrumb.html` ファイルを、パンくずコアコンポーネントを指す `sling:resourceSuperTypes` を含むサイト固有のコンポーネントにコピーする必要があります。

### コンポーネントのスタイル設定 {#styling-the-components}

カスタマイズの最初の形式は、CSS スタイルを適用することです。

これが簡単になるよう、コアコンポーネントではセマンティックなマークアップをレンダリングし、[Bootstrap](https://getbootstrap.com/) / を参考にして標準化された命名規則に従います。また、個々のコンポーネントのスタイルを容易にターゲット化および名前空間化できるよう、各コアコンポーネントは「`cmp`」および「`cmp-<name>`」クラスを持つ DIV 要素内にラップされます。

For instance, looking at the HTL file of the v1 Core Breadcrumb Component: [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html), we see that the hierarchy of elements output are `ol.breadcrumb > li.breadcrumb-item > a`. そのため、CSS ルールをそのコンポーネントのパンくずクラスのみに適用するには、次のようにすべてのルールを名前空間化する必要があります。

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

Additionally, each of the Core Components leverage the AEM [Style System feature](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) that allows template authors to define additional CSS class names that can be applied to the component by the page authors. また、テンプレートごとに、許可されるコンポーネントスタイルのリストと、いずれかのスタイルを同じ種類のすべてのコンポーネントにデフォルトで適用するかどうかを定義できます。

## アップグレード時のカスタマイズの互換性 {#upgrade-compatibility-of-customizations}

次の 3 種類のアップグレードが可能です。

* AEM のバージョンのアップグレード
* コアコンポーネントの新しいマイナーバージョンへのアップグレード
* コアコンポーネントのメジャーバージョンへのアップグレード

Generally, upgrading AEM to a new version won't impact the Core Components or the customizations done, provided that the components' versions also support the new AEM version that is being migrated to, and that customizations don't use APIs that have been [deprecated or removed](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

コアコンポーネントを新しいメジャーバージョンに切り替えずにアップグレードしても、このページで説明したカスタマイズパターンが使用されている限り、カスタマイズには何の影響もありません。

コアコンポーネントを新しいメジャーバージョンに切り替えた場合、互換性が保たれるのはコンテンツの構造のみであり、カスタマイズはリファクタリングが必要となることがあります。コンポーネントバージョンごとに明瞭な変更ログが公開され、このページで説明した種類のカスタマイズに影響する変更を強調します。

## カスタマイズのサポート {#support-of-customizations}

他の AEM コンポーネントの場合と同様に、カスタマイズに関して注意すべき点がいくつかあります。

1. **コアコンポーネントのコードを直接変更しないでください。**

   そうしてしまうと、コアコンポーネントが完全にサポート対象外となり、将来のコンポーネントのアップデートが困難になってしまいます。代わりに、このページで説明したカスタマイズ方法を使用してください。

1. **カスタムコードはユーザー自身の責任になります。**

   サポートプログラムではカスタムコードはカバーされません。また、[記載どおりに使用](using.md)された標準のコアコンポーネントで再現できない問題が報告されても、その問題はサポート対象外となります。

1. **廃止された機能や削除された機能を確認してください。**

   With each new AEM version being upgraded to, ensure that all API used are still topical by keeping an eye on the [Deprecated and Removed Features](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html) page.

[コアコンポーネントのサポート](developing.md#core-component-support)の節も参照してください。

**関連項目：**

* [コアコンポーネントの使用](using.md) - 独自のプロジェクトにコアコンポーネントを導入する方法について説明します。
* [コンポーネントのガイドライン](guidelines.md) - コアコンポーネントの実装パターンについて説明します。
