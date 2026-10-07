---
product: adobe campaign
title: イベントデータサイクル
description: イベントデータサイクルについてさらに詳しく
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 96%
---
# データサイクル {#section_r1f_xqt_pgb}

イベントは POST API 呼び出しです。 イベントは、ストリーミング取得 API を使用して Adobe Experience Platform に送信されます。 トランザクションメッセージング API を通じて送信されるイベントの URL 宛先は「インレット」と呼ばれます。 イベントのペイロードは、XDM 形式に従います。

ペイロードには、ストリーミング取得 API が機能するために必要な情報（ヘッダー内）、[!DNL Journey Orchestration] が機能するために必要な情報（イベント ID、ペイロード本文の一部）、ジャーニー内で使用する情報（本文内で使用する、放棄された買い物かごの金額など）が含まれます。 ストリーミング取り込みには、認証済みと非認証の 2 つのモードがあります。 ストリーミング取得 API の詳細については、[このリンク](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=ja)を参照してください。

ストリーミング取得 API を通じて到着したイベントは、パイプラインと呼ばれる内部サービスに送られ、その後 Adobe Experience Platform に送られます。 イベントスキーマで「リアルタイム顧客プロファイルサービス」フラグが有効になっていて、データセット ID にも「リアルタイム顧客プロファイル」フラグが設定されている場合は、リアルタイム顧客プロファイルサービスに移動します。

システム生成イベントの場合、パイプラインがフィルタリングするイベントは、[!DNL Journey Orchestration] が提供する [!DNL Journey Orchestration] eventID（以下のイベント作成プロセスを参照）がペイロードに含まれているイベントです。 ルールベースのイベントの場合は、eventID 条件を使用してイベントを識別します。 これらのイベントは [!DNL Journey Orchestration] がリッスンし、対応するジャーニーがトリガーされます。
