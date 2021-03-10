---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestrationにイベントを送信するための追加手順
description: Journey Orchestrationにイベントを送信するための追加手順について説明します
feature: ジャーニー
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 13%

---



# [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}にイベントを送信する追加手順

>[!NOTE]
>
>イベントの作成時に、[!DNL Journey Orchestration]は自動的にこのイベントのIDを生成します。 イベントをプッシュするシステムでは ID を生成せずに、ペイロードプレビューにある ID を使用する必要があります。[このページ](../event/previewing-the-payload.md)を参照してください。

**[!UICONTROL ストリーミング取り込みAPI]**&#x200B;に送信し、[!DNL Journey Orchestration]で使用するイベントを設定するには、次の手順に従う必要があります。

1. Adobe Experience PlatformAPIからインレットURLを取得します（[ストリーミングインジェストAPI](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/streaming/overview.html)を参照）。
1. ペイロードプレビューの&#x200B;**[!UICONTROL イベント]**&#x200B;メニュー内のペイロードをコピーします。 [このページ](../event/defining-the-payload-fields.md)を参照してください。

次に、コピーしたペイロードを使用してイベントをストリーミングインジェストAPIにプッシュするデータシステムを設定する必要があります。

1. ストリーミング取り込みAPIのURLに対するPOSTAPI呼び出しを設定します（入口と呼ばれます）。
1. [!DNL Journey Orchestration]からコピーしたペイロードを、ストリーミングインジェストAPIへのAPI呼び出しの本文(「data section」)で使用します。 以下に例を示します
1. ペイロード内のすべての変数を取得する場所を決定します。 例：イベントが住所を伝えると想定されている場合、貼り付けられたペイロードには「住所」が表示されます。&quot;string&quot;. 「string」は、メッセージの送信先の電子メールである適切な値を自動的に設定する変数に置き換える必要があります。 ペイロードプレビューの&#x200B;**[!UICONTROL Header]**&#x200B;セクションでは、作業を容易にするために予想される多くの値が自動的に入力されます。
1. 「application/json」をbodyタイプとして選択します。
1. 「x-gw-ims-org-id」キーを使用して、IMS組織IDをヘッダーで渡します。 値には、IMS組織ID(「XXX@AdobeOrg」)を使用します。

以下に、ストリーミング取り込みAPIイベントの例を示します。

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

「data」部分を貼り付ける場所の特定を容易にするために、[https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)などのJSONビジュアライゼーションツールを使用できます。

ストリーミング取り込みAPIのトラブルシューティングについては、[ページ](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/streaming/troubleshooting.translate.html)を参照してください。
