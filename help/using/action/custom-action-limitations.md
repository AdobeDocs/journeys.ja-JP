---
title: カスタムアクションの制限
description: カスタムアクションの制限について説明します。
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
source-git-commit: 2a55139697347ade80959f60bf52bfde39e43eb9
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 5%

---


# カスタムアクションの制限 {#concept_lh2_df1_2gb}

Here are a few limitations regarding the use of custom actions:

* There is no sending volume buffering/smoothing.
* Two retries are systematically performed in case of an error. 受け取ったエラーメッセージに従って再試行数を調整することはできません。
* 組み込みの **[!UICONTROL Reaction]** イベントを使用すると、すぐに使用できるアクションに対して反応できます(を参照 [](../building-journeys/reaction-events.md))。 カスタムアクションを介して送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。
* カスタムアクションURLは動的パラメーターをサポートしていません。
* POSTとPUT呼び出しのメソッドのみがサポートされています。
* クエリパラメーターまたはヘッダーの名前は、「。」で開始できません。 または &quot;$&quot;.
* IPアドレスは使用できません。
* 内部Adobeアドレス(.adobe.) は許可されません。
