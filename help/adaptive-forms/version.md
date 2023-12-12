---
title: AEM Forms コアコンポーネントのバージョン
description: AEMコアコンポーネントはリリースとして公開されます。同じコアコンポーネントの複数のバージョンが含まれている場合があります。 このドキュメントでは、リリースとバージョンの概要、およびコアコンポーネントと AEM の互換性を理解する方法について説明します。
role: Architect, Developer, Admin, User
exl-id: 8146a5b1-acf6-4b54-ad6b-6e1747a137f6
source-git-commit: a567b5ad937d426abe16c34e039e19cd0b1af5b0
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 85%

---

# コアコンポーネントのバージョン {#core-components-versions}

コアコンポーネント 2.0.10 の現在のリリースは [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja) と互換性があり、コアコンポーネントリリース 1.1.12 は[オンプレミスおよび AMS の AEM 6.5 Form](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=ja) のインストールと互換性があります。

## AEM as a Cloud Service のバージョン履歴 {#aem-as-cs-version-history}

次の表は、AEM as a Cloud Service と互換性のあるコアコンポーネントリリースをリストアップしたものです。これらは、[GitHub とそのリリースの包括的な詳細](https://github.com/adobe/aem-core-forms-components/releases)で利用できます。

| リリース | 説明 | AEM as a Cloud Service | Java™ | リリース日 |
|---|---|---|---|---|
| [2.0.74](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.74) | このリリースでは、AEM Formsの送信アクションで送信エラーが更新されました。 | 継続的 | 8、11 | 2023年11月15日（PT） |
| [2.0.70](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.70) | このリリースでは、フォームコンテナのサイトページ言語を処理するサポートが追加されました。 | 継続的 | 8、11 | 2023年11月10日（PT） |
| [2.0.64](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.64) | ラジオ／チェックボックスコンポーネントのラベルルのリッチテキストをサポートします。このリリースには、利用条件コンポーネントの修正も含まれています。 | 継続的 | 8、11 | 2023年11月6日（PT） |
| [2.0.62](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.62) | このリリースでは、利用条件コンポーネントのサポートが追加されました。 また、コアコンポーネントの修飾名のサポートも追加されました。 | 継続的 | 8、11 | 2023年10月16日（PT） |
| [2.0.60](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.60) | このリリースには、カスタムプロパティ機能、ウィザード、日付選択の各コンポーネントに関する修正が含まれています。 | 継続的 | 8、11 | 2023年9月12日（PT） |
| [2.0.56](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.56) | このリリースでは、すべてのコアコンポーネントのカスタムプロパティがサポートされるようになりました。 | 継続的 | 8、11 | 2023年9月12日（PT） |
| [2.0.54](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.54) | このリリースでは、日付選択コンポーネントを使用したローカライゼーションに関連する問題が修正されました。 | 継続的 | 8、11 | 2023年8月30日（PT） |
| [2.0.52](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.52) | アダプティブフォーム内でのチェックボックスコンポーネントの使用のサポート。 | 継続的 | 8、11 | 2023年8月25日（PT） |
| [2.0.50](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.50) | このリリースでは、アダプティブフォーム内のフォームフラグメントのサポートが追加されました。 | 継続的 | 8、11 | 2023年8月4日（PT） |
| [2.0.48](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.48) | このリリースでの主な改善点は、Lighthouse のパフォーマンスに関連しています。 | 継続的 | 8、11 | 2023年7月25日（PT） |
| [2.0.42](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.42) | このリリースには、プログラミング終了時に改善点が組み込まれています。 | 継続的 | 8、11 | 2023年7月18日（PT） |
| [2.0.38](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.38) | このリリースではアクセシビリティ機能が改善されました。 | 継続的 | 8、11 | 2023年7月17日（PT） |
| [2.0.36](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.36) | このリリースでは、ルールエディターのサービスの呼び出しを使用すると、カスタムエラーハンドラーを使用できます。 | 継続的 | 8、11 | 2023年7月3日（PT） |
| [2.0.34](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.34) | 繰り返し可能なコンポーネントの追加／削除ボタンと共に、デフォルトのエラーメッセージのローカライゼーションサポートを追加しました。 | 継続的 | 8、11 | 2023年6月28日（PT） |
| [2.0.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.32) | このリリースでは、アダプティブフォームに Captcha のサポートが追加されています。 | 継続的 | 8、11 | 2023年6月15日（PT） |
| [2.0.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.26) | AEM Sites でのアダプティブフォームの追加のサポート。 | 継続的 | 8、11 | 2023年6月7日（PT） |
| [2.0.18](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.18) | このリリースでは、アコーディオンコンポーネントの再現性がサポートされます。 また、新しいコンポーネントを縦向きタブとして追加しました。 | 継続的 | 8、11 | 2023年6月5日（PT） |
| [2.0.10](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.10) | このリリースでは、Sites のエディターでアダプティブフォームのコンテナコンポーネントのサポートが導入されました。 | 継続的 | 8、11 | 2023年3月17日（PT） |
| [2.0.8](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.8) | このリリースでは、ウィザードコンポーネントの再現性機能が導入されました。 | 継続的 | 8、11 | 2023年3月3日（PT） |
| [2.0.6](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | このリリースでは、数値入力コアコンポーネントの複数の形式が導入されました。 | 継続的 | 8、11 | 2023年2月8日（PT） |
| [2.0.4](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | このリリースでは、AEM as a Cloud Service のコアコンポーネントのサポートが導入されました。 | 継続的 | 8、11 | 2023年1月30日（PT） |

## AEM 6.5 Forms のバージョン履歴 {#aem-as-form-version-history}

次の表は、オンプレミスおよび AMS の AEM 6.5 Form と互換性のあるコアコンポーネントリリースをリストアップしたものです。これらは、[GitHub とそのリリースの包括的な詳細](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12)で利用できます。

| リリース | 説明 | AEM 6.4 | AEM 6.5 | Java™ | リリース日 |
|---|---|---|---|---|---|
| [1.1.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.32) | このリリースでは、AEM Service Pack 6.5.18.0 のパッケージ情報を更新しました。 | - | 6.5.16.0+ | 8、11 | 2023年10月15日（PT） |
| [1.1.28](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.28) | ラジオ／チェックボックスコンポーネントのラベルルのリッチテキストをサポートします。また、このリリースには、利用条件コンポーネントのサポートも含まれます。 | - | 6.5.16.0+ | 8、11 | 2023年10月15日（PT） |
| [1.1.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.26) | このリリースでは、アダプティブフォームのチェックボックスコンポーネントのサポートを追加しました。また、Lighthouse のパフォーマンスの改善も含まれます。このリリースには、ルールエディターのサービスの呼び出しを使用するカスタムエラーハンドラーも含まれます。 | - | 6.5.16.0+ | 8、11 | 2023年10月15日（PT） |
| [1.1.24](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.24) | 繰り返し可能なコンポーネントの追加／削除ボタンと共に、デフォルトのエラーメッセージのローカライゼーションサポートを追加しました。また、アダプティブフォームでの reCAPTCHA のサポートも追加しました。 | - | 6.5.16.0+ | 8、11 | 2023年6月29日（PT） |
| [1.1.22](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.22) | AEM Sites でのアダプティブフォームの追加のサポート。ウィザードと垂直タブコンポーネントの編集ダイアログに「項目」タブを追加しました。 | - | 6.5.16.0+ | 8、11 | 2023年6月7日（PT） |
| [1.1.12](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12) | このリリースでは、オンプレミスおよび AMS の AEM Forms のコアコンポーネントのサポートが導入されました。 | - | 6.5.16.0+ | 8、11 | 2023年2月8日（PT） |

## 関連トピック {#see-also}

{{see-also}}