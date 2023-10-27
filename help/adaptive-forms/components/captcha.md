---
title: アダプティブフォームのコアコンポーネント - フォームコンテナ
description: Web ページへのアダプティブフォームの追加。
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
exl-id: 1e413ef3-7a6f-41fc-825d-dbe09ebaffe9
source-git-commit: 37ac7d3a9ae8c88d4c9be8129cfbd1eb4a7cccd1
workflow-type: ht
source-wordcount: '1048'
ht-degree: 100%

---

# Google reCPATCHA {#google-recaptcha}

CAPTCHA（コンピュータと人間を区別する完全に自動化された公開チューリングテスト）は、人間と自動化されたプログラム／ボットを区別するために、オンライントランザクションで一般的に使用されるプログラムです。テストを行ってユーザーの反応を評価し、サイトを使用しているのが人間かボットかを判断します。テストが失敗した場合の続行を防ぎ、ボットによるスパムの投稿や悪意のある目的を防止することで、オンライントランザクションの安全性を高めます。

AEM Forms as a Cloud Service は、アダプティブフォームで Google reCAPTCHA v2 をサポートします。これを使用して、フォームの送信時に CAPTCHA の課題を提示できます

## 使用方法 {#reasons-to-use-google-recaptcha}


- **スパムとボットの防止**：reCAPTCHA を使用する主な理由の 1 つは、スパムの送信や悪意のあるボットがフォームにフラッディングするのを防止するためです。reCAPTCHA の高度なアルゴリズムでは、フォームの送信の自動試行を検出し、正規のユーザーのみがフォームを操作できるようにします。

- **セキュリティの強化**：reCAPTCHA を実装すると、アダプティブフォームに追加のセキュリティのレイヤーが追加されます。これにより、機密情報が保護され、悪意のあるユーザーによる脆弱性の悪用を防止できます。

- **ユーザーエクスペリエンス**：CAPTCHA は不便だと見なされることもありますが、reCAPTCHA の適応型アプローチにより、ほとんどのユーザーには最小限の操作で済む、合理化されたわかりやすいエクスペリエンスが提供されます。これにより、ボットを抑止しながら、肯定的なユーザーエクスペリエンスを保持できます。

- **適応性**：reCAPTCHA のアダプティブメカニズムは、ユーザーの行動とインタラクションを分析し、ユーザーが人間であるかどうかを判断します。つまり、ボットである可能性によって、ユーザーに提示される課題のレベルは異なります。この適応性により、強力なセキュリティを保持しながら、ユーザー自身の負担が軽減されます。

- **手動モデレートの削減**：reCAPTCHA では、スパム送信とボット生成コンテンツの数を大幅に削減することで、手動でのモデレートやクリーンアップに費やされる時間とリソースを節約できます。

## バージョンと互換性 {#version-and-compatibility}

アダプティブフォームの Google reCAPTCHA コアコンポーネントは、コアコンポーネントの「バージョン」の一部として 2023年8月にリリースされました。次の表に、サポートされているすべてのバージョン、AEM の互換性、対応するドキュメントへのリンクを示します。

|  |  |
|---|---|
| コンポーネントのバージョン | AEM as a Cloud Service |
| --- | --- |
| v1 | <br>[リリース 2.0.4](/help/versions.md) 以降と互換性あり | 互換性あり | 互換性あり |

コアコンポーネントのバージョンとリリースについて詳しくは、[コアコンポーネントのバージョン](/help/versions.md)ドキュメントをご覧ください。

## 技術的詳細 {#technical-details}

アダプティブフォームの Google reCAPTCHA コアコンポーネントに関する最新情報については、[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha) のテクニカルドキュメントをご覧ください。コアコンポーネントの開発について詳しくは、 [コアコンポーネント開発者向けのドキュメント](/help/developing/overview.md)をご覧ください。

## 設定ダイアログ {#configure-dialog}

設定ダイアログを使用すると、訪問者の Google reCAPTCHA エクスペリエンスを簡単にカスタマイズできます。また、簡単に Google reCAPTCHA オプションを定義して、シームレスなユーザーエクスペリエンスを実現することもできます。

### 「基本」タブ {#basic-tab}

- **名前** - フォームコンポーネントは、フォーム内とルールエディター内の両方で一意の名前で簡単に識別できますが、名前にスペースや特殊文字を含めることはできません。

- **タイトル** - タイトルを使用すると、フォーム内のコンポーネントを簡単に識別できます。デフォルトでは、コンポーネントの上にタイトルが表示されます。 タイトルを追加しない場合、コンポーネントの名前がタイトルテキストの代わりに表示されます。

- **タイトルを非表示** - コンポーネントのタイトルを非表示にするには、このオプションを選択します。

- **設定** -

- **タイプ** -

- **コンポーネントを非表示** - フォームでコンポーネントを非表示にするには、このオプションを選択します。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。 これは、ユーザーが表示する必要のない情報や直接変更した情報を保存する必要がある場合に役立ちます。

- **コンポーネントの無効化** - コンポーネントを無効にする場合は、このオプションを選択します。 エンドユーザーは、無効になっているコンポーネントをアクティブにしたり、編集したりすることはできません。 無効なコンポーネントのデータは送信されません。ユーザーはフィールドの値を表示できますが、変更することはできません。このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

- **読み取り専用** - コンポーネントを編集不可にするには、このオプションを選択します。 ユーザーはフィールドの値を表示できますが、変更することはできません。 このコンポーネントは、他の目的（ルールエディターでの計算に使用するなど）にも利用できます。

### 「検証」タブ {#validation-tab}

- **エラーメッセージ** - このオプションを使用すると、「**必須**」チェックボックスがオンになっていて、フォームフィールドは空白の場合に表示されるメッセージを指定できます。

## 関連トピック {#see-also}

- [AEM アダプティブフォームの作成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=ja)
- [AEM Sites ページへの AEM アダプティブフォームの追加](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=ja)
- [AEM アダプティブフォームへテーマを適用](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=ja)
- [AEM アダプティブフォームへコンポーネントを追加](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [AEM アダプティブフォームで reCAPTCHA を使用](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html?lang=ja)
- [AEM アダプティブフォームの PDF バージョン（DoR）を生成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html?lang=ja)
- [AEM アダプティブフォームを翻訳](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html?lang=ja)
- [フォームの使用状況を追跡するアダプティブフォームの Adobe Analytics を有効にする](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html?lang=ja)
- [Microsoft SharePoint へアダプティブフォームを接続](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html?lang=ja#create-sharepoint-configuration)
- [Microsoft Power Automate へアダプティブフォームを接続](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html?lang=ja#microsoft-power-automate)
- [Microsoft OneDrive へアダプティブフォームを接続](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html?lang=ja#submit-to-onedrive)
- [Microsoft Azure Blob Storage へアダプティブフォームを接続](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html?lang=ja#submit-to-azure-blob-storage)
- [Salesforce へアダプティブフォームを接続](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html?lang=ja)
- [AEM アダプティブフォームで Adobe Sign を使用](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html?lang=ja)
- [アダプティブフォームの新しいロケールを追加](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html?lang=ja)
- [データベースへアダプティブフォームデータを送信](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html?lang=ja)
- [REST エンドポイントへアダプティブフォームデータを送信](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html?lang=ja#submit-to-rest-endpoint)
- [AEM ワークフローへアダプティブフォームデータを送信](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html?lang=ja#invoke-an-aem-workflow)
- [AEM web サイト上の AEM アダプティブフォームをリストするフォームポータルを使用](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html?lang=ja)

