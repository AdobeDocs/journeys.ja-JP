---
title: Jargeny Orchestrationにイベントを送信する追加手順
description: イベントをJargeny Orchestrationに送信する追加の手順について説明します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Jargeny Orchestrationにイベントを送信する追加手順 {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>イベントを作成すると、Jarney OrchestrationはこのイベントのIDを自動的に生成します。 イベントをプッシュするシステムではIDを生成しないでください。ペイロードプレビューで使用できるIDを使用する必要があります。 [](../event/previewing-the-payload.md)を参照してください。

Jureny Orchestrationで送信され、使用されるイベ **[!UICONTROL Streaming Ingestion APIs]**ントを設定するには、次の手順に従う必要があります。

1. データプラットフォームAPIからインレットURLを取得します( [Streaming Ingestion APIsを参照](https://www.adobe.io/apis/cloudplatform/dataservices/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md))。
1. メニューのペイロードプレビューからペイロードをコピー **[!UICONTROL Event]**します。[](../event/defining-the-payload-fields.md)を参照してください。

次に、コピーしたペイロードを使用して、イベントをストリーミングインジェストAPIにプッシュするデータシステムを設定する必要があります。

1. ストリーミングインジェストAPIのURL（インレットと呼ばれる）に対するPOST API呼び出しを設定します。
1. Streaming Ingestion APIへのAPI呼び出しの本文(「data section」)で、Jeurney Orchestrationからコピーしたペイロードを使用します。 以下に例を示します。
1. ペイロード内のすべての変数を取得する場所を決定します。 例：イベントがアドレスを伝えると想定されている場合、貼り付けられたペイロードに「アドレス」が表示されます。&quot;string&quot;. 「string」は、メッセージの送信先の電子メールである適切な値を自動的に設定する変数に置き換える必要があります。 ペイロードプレビューのセクションでは、作業を **[!UICONTROL Header]**容易にすると予想される多くの値が自動的に入力されます。
1. 「application/json」をボディタイプとして選択します。
1. 「x-gw-ims-org-id」キーを使用して、IMS ORG IDをヘッダーに渡します。 値には、IMS ORG ID(「XXX@AdobeOrg」)を使用します。

以下に、ストリーミングインジェストAPIイベントの例を示します。

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

「データ」部分を貼り付ける場所を容易に特定するために、https://jsonformatter.curiousconcept.comなどのJSONビジュアライゼーションツールを使用できま [す。](https://jsonformatter.curiousconcept.com)

ストリーミングインジェストAPIのトラブルシューティングについては、このページを参照 [してくださ](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md)い。
