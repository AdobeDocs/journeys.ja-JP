---
product: adobe campaign
title: イベントデータサイクル
description: イベントデータサイクルの詳細
feature: ジャーニー
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 96%

---

# データサイクル {#section_r1f_xqt_pgb}

イベントは POST API 呼び出しです。イベントは、ストリーミング取得 API を使用して Adobe Experience Platform に送信されます。トランザクションメッセージング API を通じて送信されるイベントの URL 宛先は「インレット」と呼ばれます。イベントのペイロードは、XDM 形式に従います。

ペイロードには、ストリーミング取得 API が機能するために必要とする情報（ヘッダー内）、[!DNL Journey Orchestration] が機能するために必要とする情報（イベント ID、ペイロード本文の一部）、ジャーニー内で使用する情報（本文内では、例えば、放棄された買い物かごの金額など）が含まれます。ストリーミング取得には、認証済みと非認証の 2 つのモードがあります。ストリーミング取得 API の詳細については、[このリンク](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=ja)を参照してください。

ストリーミング取得 API を通じて到着したイベントは、パイプラインと呼ばれる内部サービスに送られ、その後 Adobe Experience Platform に送られます。イベントスキーマで「リアルタイム顧客プロファイルサービス」フラグが有効になっていて、データセット ID にも「リアルタイム顧客プロファイル」フラグが設定されている場合は、リアルタイム顧客プロファイルサービスに移動します。

システム生成イベントの場合、パイプラインがフィルタリングするイベントは、[!DNL Journey Orchestration] が提供する [!DNL Journey Orchestration] eventID（以下のイベント作成プロセスを参照）がペイロードに含まれているイベントです。ルールベースのイベントの場合は、eventID 条件を使用してイベントを識別します。これらのイベントは [!DNL Journey Orchestration] がリッスンし、対応するジャーニーがトリガーされます。
