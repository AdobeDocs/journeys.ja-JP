---
product: adobe campaign
solution: Journey Orchestration
title: イベントデータサイクル
description: イベントのデータサイクルについて
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 79%

---

# データサイクル {#section_r1f_xqt_pgb}

イベントは POST API 呼び出しです。イベントは、ストリーミング取得 API を使用して Adobe Experience Platform に送信されます。トランザクションメッセージング API を通じて送信されるイベントの URL 宛先は「インレット」と呼ばれます。イベントのペイロードは、XDM 形式に従います。

ペイロードには、ストリーミング取得 API が機能するために必要とする情報（ヘッダー内）、[!DNL Journey Orchestration] が機能するために必要とする情報（イベント ID、ペイロード本文の一部）、ジャーニー内で使用する情報（本文内では、例えば、放棄された買い物かごの金額など）が含まれます。ストリーミング取得には、認証済みと非認証の 2 つのモードがあります。ストリーミング取得 API の詳細については、[このリンク](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/api/getting-started.html)を参照してください。

ストリーミング取得 API を通じて到着したイベントは、パイプラインと呼ばれる内部サービスに送られ、その後 Adobe Experience Platform に送られます。イベントスキーマでリアルタイム顧客プロファイルサービスフラグが有効になっていて、リアルタイム顧客プロファイルフラグも持つデータセット ID が設定されている場合は、リアルタイム顧客プロファイルサービスに移動します。

システム生成イベントの場合、パイプラインフィルターイベントは、[!DNL Journey Orchestration]が提供する[!DNL Journey Orchestration] eventIDを含むペイロード(以下のイベント作成プロセスを参照)を持ち、イベントペイロードに含まれます。 ルールベースのイベントの場合、イベントはeventID条件を使用して識別されます。 これらのイベントは、[!DNL Journey Orchestration] によってリッスンされ、対応するジャーニーがトリガーされます。
