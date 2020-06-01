---
title: Journey Orchestrationにイベントを送信するための追加手順
description: Journey Orchestrationにイベントを送信するための追加手順について説明します
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---



# Journey Orchestrationにイベントを送信するための追加手順 {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>イベントの作成時に、Journey OrchestrationはこのイベントのIDを自動的に生成します。 イベントをプッシュするシステムではIDを生成しない。ペイロードプレビューで使用できるIDを使用する必要がある。 [](../event/previewing-the-payload.md)を参照してください。

イベントを **[!UICONTROL ストリーミング取り込みAPIに送信し、Journey Orchestrationで使用するように設定するには]** 、次の手順に従う必要があります。

1. Data Platform APIからインレットURLを取得します( [ストリーミング取り込みAPIを参照](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/streaming/overview.html))。
1. ペイロードメニューのペイロードプレビューから **[!UICONTROL イベント]** をコピーします。 [](../event/defining-the-payload-fields.md)を参照してください。

次に、コピーしたペイロードを使用してイベントをストリーミングインジェストAPIにプッシュするデータシステムを設定する必要があります。

1. ストリーミングインジェストAPIのURL（インレットと呼ばれる）に対するPOST API呼び出しを設定します。
1. Journey Orchestrationからコピーしたペイロードを、Streaming Ingestion APIへのAPI呼び出しの本文(「data section」)で使用します。 以下に例を示します
1. ペイロード内のすべての変数を取得する場所を決定します。 例： イベントが住所を伝えると想定されている場合、貼り付けられたペイロードには「住所」が表示されます。 &quot;string&quot;. 「string」は、メッセージの送信先の電子メールである適切な値を自動的に設定する変数に置き換える必要があります。 ペイロードプレビューの「 **[!UICONTROL Header]** 」セクションでは、作業を容易にすると予想される多くの値が自動的に入力されます。
1. 「application/json」をbodyタイプとして選択します。
1. 「x-gw-ims-org-id」キーを使用して、IMS ORG IDをヘッダーで渡します。 値には、IMS ORG ID(&quot;XXX@AdobeOrg&quot;)を使用します。

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

「data」部分を貼り付ける場所の特定を容易にするために、https://jsonformatter.curiousconcept.comなどのJSONビジュアライゼーションツールを使用でき [ます。](https://jsonformatter.curiousconcept.com)

ストリーミング取り込みAPIのトラブルシューティングについては、この [ページを参照してください](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html)。
