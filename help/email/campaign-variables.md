---
title: キャンペーン変数
description: キャンペーン変数をプレースホルダーとして使用して、パーソナライズされた電子メールコンテンツを作成します。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# キャンペーン変数 {#campaign-variables}

キャンペーン変数を使用してパーソナライズされた E メールコンテンツを作成します。 キャンペーン変数は、Adobe Campaign値のプレースホルダーとして機能し、E メールコンテンツに挿入できます。 コンテンツがAdobe Campaign経由で送信されると、Campaign は、これらの変数を受信者のパーソナライズされたコンテンツで置き換えます。

## 使用方法 {#usage}

電子メールコアコンポーネントを使用すると、共通のテキストフィールドの横にあるパーソナライゼーションボタンを使用して、キャンペーン変数に簡単にアクセスできます。 押すと、パーソナライゼーションフィールドを選択できるダイアログが表示されます。

使用可能なパーソナライゼーションフィールドのリストがAdobe Campaignインスタンスと同期されます。 フィールドは、スキーマ内のAdobe Campaignで管理されます `nms:seedMember`. のすべてのフィールド `nms:seedMember` また、受信者テーブルにも存在する必要があります。

## Adobe Campaign Variable ダイアログを選択 {#dialog}

Adobe Campaign変数を選択ダイアログは、電子メールコアコンポーネントの多くの編集ダイアログで使用できます。 これを使用するには、 **Adobe Campaign変数を選択** 該当するフィールドの横にあるアイコン。 このアイコンは 2 つの形式を取ることができます。

![Adobe Campaignボタン](/help/email/assets/campaign-button.png)
![「Adobe Campaign変数」アイコンを選択します。](/help/email/assets/select-adobe-campaign-variable-icon.png)

両方のアイコンをクリックすると、 **Adobe Campaign変数を選択** ダイアログ。

![Adobe Campaign Variable ダイアログを選択](assets/select-campaign-variable-dialog.png)

列表示を使用して、挿入する変数を見つけます。 列内のノードをクリックすると、その子が右側の新しい列に表示されます。 これにより、変数コンテンツ構造をナビゲートできます。

挿入する変数を選択し、ダイアログの右上にあるチェックマークをクリックします。

![Adobe Campaign変数が選択されました](assets/select-campaign-variable-dialog-selected.png)

次に、変数が電子メールコアコンポーネントの編集ダイアログのフィールドに挿入されます。

![編集ダイアログに挿入されるキャンペーン変数](assets/campaign-variable.png)

ダイアログの左上にある X をいつでもクリックして、ダイアログをキャンセルして閉じます。
