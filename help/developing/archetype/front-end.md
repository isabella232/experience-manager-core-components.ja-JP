---
title: AEMプロジェクトアーキタイプを使用したフロントエンド開発
description: AEM Project Archetype の、Webpack に基づく専用のフロントエンドビルドメカニズム（オプション）について説明します。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 75%

---


# AEMプロジェクトアーキタイプを使用したフロントエンド開発 {#front-end}

AEM プロジェクトのアーキタイプには、Webpack ベースの専用フロントエンドビルドメカニズム（オプション）が含まれています。このように、ui.frontend モジュールは、JavaScript や CSS ファイルを含む、プロジェクトのすべてのフロントエンドリソースの中心となります。この便利で柔軟な機能を最大限に活用するには、AEM プロジェクトにフロントエンド開発がどのように適合するかを理解することが重要です。

このドキュメントでは、フロントエンドビルドモジュールの一般的な使用パターンと、それがお客様に与える影響について説明します。 ビルドオプションと技術的な手順について詳しくは、アーキタイプの GitHub リポジトリにあるドキュメントを参照してください。

>[!TIP]
>
>最新のAEMプロジェクトアーキタイプと関連する技術ドキュメント [は GitHub にあります。](https://github.com/adobe/aem-project-archetype)

## AEMフロントエンドおよびバックエンド開発 {#front-end-back-end}

簡単に言えば、AEM プロジェクトは、2 つの異なる関連部分から成ると考えることができます。

* AEM のロジックを駆動し、Java ライブラリ、OSGi サービスなどを生成するバックエンドの開発
* 結果として作成される Web サイトの表示と動作を促し、JavaScript ライブラリと CSS ライブラリを生成するフロントエンド開発

これらの 2 つの開発プロセスはプロジェクトの異なる部分に焦点を当てているので、バックエンドとフロントエンドの開発が並行して行われる可能性があります。

![フロントエンドワークフロー図](/help/assets/front-end-flow.png)

ただし、作成されるプロジェクトでは、バックエンドとフロントエンドの両方の開発作業の出力を使用する必要があります。

## マークアップの決定 {#determining-markup}

プロジェクトに実装するフロントエンド開発ワークフローに関しては、まずバックエンド開発者とフロントエンド開発者がマークアップに同意する必要があります。通常、AEM はマークアップを定義し、これがコアコンポーネントで提供されます。[ただし、必要に応じてカスタマイズできます。](/help/developing/customizing.md#customizing-the-markup)

## 可能なフロントエンド開発ワークフロー {#possible-workflows}

フロントエンドビルドモジュールは、便利で柔軟なツールですが、どのように使用されるすべきかについてはユーザーに任されています。以下の 2 つは&#x200B;*可能な*&#x200B;使用例ですが、個々のプロジェクトでは他の使用モデルが必要になる場合があります。

### Webpack 静的開発サーバーの使用 {#using-webpack}

Webpack を使用すると、ui.frontend モジュール内の AEM Web ページの静的出力に基づいてスタイルを設定し、開発することができます。

1. ページプレビューモードを使用するか、URL に `wcmmode=disabled` を渡すことによって、AEM でページをプレビューする
1. ui.frontend モジュール内でページソースを表示し、静的 HTML として保存する
1. [Webpack を起動](#webpack-dev-server)して、必要な JavaScript と CSS のスタイル設定と生成を開始する
1. `npm run dev` を実行して clientlib を生成する

このフローでは、AEM 開発者が手順 1 と 2 を実行して、静的 HTML をフロントエンド開発者に渡し、フロントエンド開発者が AEM HTML 出力に基づいて開発をおこなうことができます。

>[!TIP]
>
>また、[コンポーネントライブラリ](https://adobe.com/go/aem_cmp_library_jp)を利用して、各コンポーネントのマークアップ出力のサンプルを取り込み、ページレベルではなくコンポーネントレベルで作業することもできます。

### Storybook の使用 {#using-storybook}

[Storybook ](https://storybook.js.org)を使用すると、よりアトミックなフロントエンド開発を実行できます。Storybook は AEM プロジェクトのアーキタイプには含まれていませんが、Storybook をインストールすると、ui.frontend モジュール内に Storybook アーティファクトを保存することができます。AEM 内でテストをおこなう準備が整ったら、`npm run dev` を実行して Storybook を clientlib としてデプロイできます。

>[!NOTE]
>
>[Storybook](https://storybook.js.org) は AEM プロジェクトのアーキタイプには含まれていません。使用する場合は、個別にインストールする必要があります。

## Clientlibs の概要 {#clientlibs}

フロントエンドモジュールは、 [AEM clientlib.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=ja)。NPM ビルドスクリプトを実行すると、アプリがビルドされ、 `aem-clientlib-generator` パッケージは、結果のビルド出力を取得し、そのような clientlib に変換します。

clientlib は、次のファイルとディレクトリで構成されます。

* `css/`：HTML で要求できる CSS ファイル
* `css.txt`：ファイルを結合できるように、`css/` 内のファイルの順序と名前を AEM に指示します。
* `js/`：HTML で要求できる JavaScript ファイル
* `js.txt`：ファイルを結合できるように、`js/` 内のファイルの順序と名前を AEM に指示します。
* `resources/`：ソースマップ、非エントリポイントコードチャンク（コード分割による）、静的アセット（アイコンなど）など。

>[!TIP]
>
>AEMでの clientlib の処理方法について詳しくは、 [AEM開発ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=ja) それらを [コアコンポーネントのドキュメント。](/help/developing/including-clientlibs.md)
