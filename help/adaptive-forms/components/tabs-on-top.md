---
title: アダプティブフォームのコアコンポーネント - 上部のタブ
description: 上部のコアコンポーネントで、アダプティブフォームのタブを使用するか、カスタマイズします。
role: Architect, Developer, Admin, User
source-git-commit: 59cd9d65bf4c1be6ab2eaf15bbb747b532863fdd
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 100%

---


# 上部のタブ {#tabs-on-top-adaptive-forms-core-component}

アダプティブフォームの上部にあるタブレイアウトを使用すると、フォームの関連するフィールドやセクションを別々のタブに整理し、グループ化することができます。各タブはタブラベルで表され、通常はフォームの上部に配置され、特定のフォームフィールドとセクションのセットが含まれます。このレイアウトにより、ユーザーはフォームの様々なセクションに簡単に移動してアクセスできるので、より使いやすく無理のないフォームになります。これは、通常、フォームに多数のフィールドとセクションが含まれ、それらをより小さく管理しやすい塊に分割する必要がある場合に使用します。また、タブは、ユーザーがキーボードショートカットを使用してフォームを移動できるようにすることで、アクセシビリティを向上させるのにも役立ちます。これにより、障がいのあるユーザーがフォームに簡単にアクセスできるようになります。

**例**

![](/help/adaptive-forms/assets/tabs.png)

## 使用方法 {#reasons-to-use-tab-on-the-top-layout}

アダプティブフォームの上部レイアウトでタブを使用する理由はいくつかあります。

* **組織**：タブを使用すると、フォームの様々なセクションを別々のカテゴリに整理することができ、ユーザーが移動しやすく、必要な情報を簡単に検索できるようになります。

* **スペースの節約**：タブを使用すると、フォームの 1 つのセクションのみを一度に表示できるので、ページ上のスペースを節約できます。

* **ユーザーエクスペリエンスの向上**：タブを使用すると、フォームをより視覚的に訴えかけ、使いやすくすることで、ユーザーエクスペリエンスを向上させることができます。

* **モバイル対応**：タブを使用すると、スクロールを減らし、フィールド間を簡単に切り替えることで、フォームがよりモバイルに適した形式になります。

つまり、タブを使用すると、フォームをより整理し、スペースを効率的に、使いやすく、アクセスしやすくすることができます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームのアコーディオンコアコンポーネントは、Cloud Service のコアコンポーネント 2.0.4 および AEM 6.5.16.0 Forms 以降のコアコンポーネント 1.1.12 の一部として 2023年2月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

| コンポーネントのバージョン | AEM as a Cloud Service | AEM 6.5.16.0 Forms 以降 |
|---|---|---|
| v1 | <br>[リリース 2.0.4](/help/adaptive-forms/version.md) 以降と互換性あり | <br>[リリース 1.1.12](/help/adaptive-forms/version.md) 以降、2.0.0 未満と互換性があります。 |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/adaptive-forms/version.md)ドキュメントをご覧ください。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術的詳細 {#technical-details}

上部コアコンポーネントの「アダプティブフォーム」タブに関する最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/tabsontop/v1/tabsontop) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、[コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者向けの上位エクスペリエンスのタブを簡単にカスタマイズできます。また、シームレスなユーザーエクスペリエンスを実現するために、上部オプションのタブを簡単に定義できます。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->


>[!MORELIKETHIS]
>
>* [アコーディオン](/help/adaptive-forms/components/accordion.md)
>* [ボタン](/help/adaptive-forms/components/button.md)
>* [チェックボックスグループ](/help/adaptive-forms/components/checkbox-group.md)
>* [日付選択](/help/adaptive-forms/components/date-picker.md)
>* [ドロップダウンリスト](/help/adaptive-forms/components/drop-down.md)
>* [メール入力](/help/adaptive-forms/components/email-input.md)
>* [フォームコンテナ](/help/adaptive-forms/components/form-container.md)
>* [ファイル添付](/help/adaptive-forms/components/file-attachment.md)
>* [フッター](/help/adaptive-forms/components/footer.md)
>* [ヘッダー](/help/adaptive-forms/components/header.md)
>* [水平タブ](/help/adaptive-forms/components/horizontal-tabs.md)
>* [画像](/help/adaptive-forms/components/image.md)
>* [数値入力](/help/adaptive-forms/components/number-input.md)
>* [パネルコンテナ](/help/adaptive-forms/components/panel-container.md)
>* [ラジオボタン](/help/adaptive-forms/components/radio-button.md)
>* [リセットボタン](/help/adaptive-forms/components/reset-button.md)
>* [送信ボタン](/help/adaptive-forms/components/submit-button.md)
>* [電話入力](/help/adaptive-forms/components/telephone-input.md)
>* [テキスト入力](/help/adaptive-forms/components/text-input.md)
>* [テキスト](/help/adaptive-forms/components/text.md)
>* [タイトル](/help/adaptive-forms/components/title.md)
>* [ウィザード](/help/adaptive-forms/components/wizard.md)

## 関連トピック {#see-also}

{{see-also}}