---
title: AEM Forms コアコンポーネントのバージョン
description: コアコンポーネントはリリースとして公開されます。これらのリリースには、同じコアコンポーネントの複数のバージョンが含まれている場合があります。このドキュメントでは、リリースとバージョンの概要、およびコアコンポーネントと AEM の互換性を理解する方法について説明します。
role: Architect, Developer, Admin, User
exl-id: 8146a5b1-acf6-4b54-ad6b-6e1747a137f6
source-git-commit: e0ed415bd7f45fdca6fbbb8ba409604d9e82a647
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 62%

---

# コアコンポーネントのバージョン {#core-components-versions}

コアコンポーネント 2.0.10 の現在のリリースは [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja) と互換性があり、コアコンポーネントリリース 1.1.12 は[オンプレミスおよび AMS の AEM 6.5 Form](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=ja) のインストールと互換性があります。

## AEM as a Cloud Service のバージョン履歴 {#aem-as-cs-version-history}

次の表は、AEM as a Cloud Service と互換性のあるコアコンポーネントリリースをリストアップしたものです。これらは、[GitHub とそのリリースの包括的な詳細](https://github.com/adobe/aem-core-forms-components/releases)で利用できます。

| リリース | 説明 | AEM as a Cloud Service | Java | リリース日 |
|---|---|---|---|---|
| [2.0.74](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.74) | このリリース送信エラーでは、AEM Formsの送信アクションが更新されます。 | 継続的 | 8、11 | 2023 年 11 月 16 日 |
| [2.0.70](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.70) | このリリースでは、フォームコンテナのサイトページ言語を処理するサポートが追加されました。 | 継続的 | 8、11 | 2023 年 11 月 11 日 |
| [2.0.64](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.64) | ラジオ/チェックボックスコンポーネントのラベルにリッチテキストをサポートします。 このリリースには、利用条件コンポーネントの修正も含まれています。 | 継続的 | 8、11 | 2023 年 11 月 7 日 |
| [2.0.62](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.62) | このリリースでは、利用条件コンポーネントのサポートが追加されています。 また、コアコンポーネントで修飾名のサポートが追加されました。 | 継続的 | 8、11 | 2023 年 10 月 17 日 |
| [2.0.60](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.60) | このリリースには、カスタムプロパティ機能、ウィザードおよび日付選択コンポーネントに関する修正が含まれています。 | 継続的 | 8、11 | 2023年9月12日（PT） |
| [2.0.56](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.56) | このリリースでは、すべてのコアコンポーネントのカスタムプロパティのサポートが追加されています。 | 継続的 | 8、11 | 2023年9月12日（PT） |
| [2.0.54](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.54) | このリリースでは、日付選択コンポーネントを使用したローカライゼーションに関連する問題が修正されました。 | 継続的 | 8、11 | 2023年8月30日（PT） |
| [2.0.52](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.52) | アダプティブフォーム内でのチェックボックスコンポーネントの使用をサポートします。 | 継続的 | 8、11 | 2023年8月25日（PT） |
| [2.0.50](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.50) | このリリースでは、アダプティブフォーム内のフォームフラグメントのサポートが追加されました。 | 継続的 | 8、11 | 2023年8月4日（PT） |
| [2.0.48](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.48) | このリリースでの主な改善点は、Lighthouse のパフォーマンスに関連しています。 | 継続的 | 8、11 | 2023 年 7 月 25 日 |
| [2.0.42](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.42) | このリリースは、プログラミング終了時に改善点を組み込んでいます。 | 継続的 | 8、11 | 2023 年 7 月 19 日 |
| [2.0.38](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.38) | このリリースではアクセシビリティ機能が向上しました。 | 継続的 | 8、11 | 2023 年 7 月 18 日 |
| [2.0.36](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.36) | このリリースでは、ルールエディターの「サービスを起動」を使用して、カスタムエラーハンドラーを使用できます。 | 継続的 | 8、11 | 2023 年 7 月 3 日 |
| [2.0.34](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.34) | 繰り返し可能なコンポーネントの追加/削除ボタンと共に、デフォルトのエラーメッセージのローカリゼーションサポートを追加しました。 | 継続的 | 8、11 | 2023年28月6日（PT） |
| [2.0.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.32) | このリリースでは、アダプティブForms用に Captcha のサポートが追加されています。 | 継続的 | 8、11 | 2023年15月6日（PT） |
| [2.0.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.26) | AEM Sitesでのアダプティブフォームの追加のサポート。 | 継続的 | 8、11 | 2023年7月6日（PT） |
| [2.0.18](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.18) | このリリースでは、アコーディオンコンポーネントの繰り返しのサポートがサポートされます。 | 継続的 | 8、11 | 2023年5月6日（PT） |
| [2.0.10](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.10) | このリリースでは、Sites のエディターでアダプティブフォームのコンテナコンポーネントのサポートが導入されました。 | 継続的 | 8、11 | 2023年3月17日（PT） |
| [2.0.8](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.8) | このリリースでは、ウィザードコンポーネントの繰り返し機能が導入されました。 | 継続的 | 8、11 | 2023年3月3日（PT） |
| [2.0.6](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | このリリースでは、数値入力コアコンポーネントの複数の形式が導入されました。 | 継続的 | 8、11 | 2023年2月8日（PT） |
| [2.0.4](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | このリリースでは、AEM as a Cloud Service のコアコンポーネントのサポートが導入されました。 | 継続的 | 8、11 | 2023年1月30日（PT） |

## AEM 6.5 Forms のバージョン履歴 {#aem-as-form-version-history}

次の表は、オンプレミスおよび AMS の AEM 6.5 Form と互換性のあるコアコンポーネントリリースをリストアップしたものです。これらは、[GitHub とそのリリースの包括的な詳細](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12)で利用できます。

| リリース | 説明 | AEM 6.4 | AEM 6.5 | Java | リリース日 |
|---|---|---|---|---|---|
| [1.1.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.32) | このリリースでは、AEM Service Pack 6.5.18.0のパッケージ情報に関する情報が更新されました。 | - | 6.5.16.0+ | 8、11 | 2023 年 10 月 16 日 |
| [1.1.28](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.28) | ラジオ/チェックボックスコンポーネントのラベルにリッチテキストをサポートします。 このリリースには、利用条件コンポーネントのサポートも含まれています。 | - | 6.5.16.0+ | 8、11 | 2023 年 10 月 16 日 |
| [1.1.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.26) | このリリースでは、アダプティブフォームのチェックボックスコンポーネントのサポートが追加されました。 また、Lighthouse のパフォーマンスも向上しました。 ルールエディターの Invoke Service を使用するカスタムエラーハンドラーも、このリリースに含まれています。 | - | 6.5.16.0+ | 8、11 | 2023 年 10 月 16 日 |
| [1.1.24](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.24) | 繰り返し可能なコンポーネントの追加/削除ボタンと共に、デフォルトのエラーメッセージのローカリゼーションサポートを追加しました。 また、アダプティブFormsでの recaptcha のサポートが追加されました。 | - | 6.5.16.0+ | 8、11 | 2023年29月6日（PT） |
| [1.1.22](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.22) | AEM Sitesでのアダプティブフォームの追加のサポート。 ウィザードおよび縦長タブコンポーネントの編集ダイアログに「項目」タブが追加されました。 | - | 6.5.16.0+ | 8、11 | 2023年07月6日（PT） |
| [1.1.12](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12) | このリリースでは、オンプレミスおよび AMS の AEM Forms のコアコンポーネントのサポートが導入されました。 | - | 6.5.16.0+ | 8、11 | 2023年2月8日（PT） |

## 関連トピック {#see-also}

{{see-also}}