---
product: adobe campaign
title: イベントをJourney Orchestrationに送信するための追加手順
description: イベントをJourney Orchestrationに送信するための追加手順について説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 8%

---

# [!DNL Journey Orchestration]にイベントを送信するための追加手順 {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>イベントを作成する際、[!DNL Journey Orchestration]はこのイベントのIDを自動的に生成します。 イベントをプッシュするシステムでは ID を生成せずに、ペイロードプレビューにある ID を使用する必要があります。[このページ](../event/previewing-the-payload.md)を参照してください。

**[!UICONTROL ストリーミング取得API]**&#x200B;に送信し[!DNL Journey Orchestration]で使用するイベントを設定するには、次の手順に従う必要があります。

1. Adobe Experience Platform APIからインレットURLを取得します（[ストリーミング取得API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html)を参照）。
1. **[!UICONTROL イベント]**&#x200B;メニューのペイロードプレビューからペイロードをコピーします。 [このページ](../event/defining-the-payload-fields.md)を参照してください。

次に、コピーしたペイロードを使用して、イベントをストリーミング取得APIにプッシュするデータシステムを設定する必要があります。

1. ストリーミングPOSTAPI URL（インレットと呼ばれる）へのインジェストAPI呼び出しを設定します。
1. ストリーミング取得APIへのAPI呼び出しの本文（「データセクション」）の[!DNL Journey Orchestration]からコピーしたペイロードを使用します。 例については、以下を参照してください。
1. ペイロードに存在するすべての変数を取得する場所を決定します。 例：イベントがアドレスを伝えることになっている場合、貼り付けられたペイロードには「アドレス」と表示されます。&quot;string&quot;. 「string」は、適切な値（メッセージの送信先となる人のEメール）を自動的に入力する変数に置き換える必要があります。 ペイロードプレビューの&#x200B;**[!UICONTROL Header]**&#x200B;セクションでは、作業を容易にするために予想される多くの値が自動入力されます。
1. 本文のタイプとして「application/json」を選択します。
1. キー「x-gw-ims-org-id」を使用して、IMS組織IDをヘッダーに渡します。 値には、IMS組織ID(「XXX@AdobeOrg」)を使用します。

ストリーミング取得APIイベントの例を次に示します。

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

「データ」部分を貼り付ける場所を特定しやすくするために、[https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)などのJSONビジュアライゼーションツールを使用できます

ストリーミング取得APIのトラブルシューティングについては、この[ページ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html)を参照してください。
