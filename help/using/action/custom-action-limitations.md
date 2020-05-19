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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 5%

---


# カスタムアクションの制限 {#concept_lh2_df1_2gb}

カスタムアクションの使用に関する制限事項を以下に示します。

* 上限が設定されていないか、ボリュームのバッファリング/スムージングを送信していません。
* 誤りの場合には、2つの再試行を系統的に行う。 受け取ったエラーメッセージに従って再試行数を調整することはできません。
* 組み込みの **[!UICONTROL Reaction]** イベントを使用すると、すぐに使用できるアクションに対して反応できます(を参照 [](../building-journeys/event-activities.md))。 カスタムアクションを介して送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。
* カスタムアクションURLは動的パラメーターをサポートしていません。
* POSTおよびPUT呼び出しメソッドのみがサポートされます。
* クエリパラメーターまたはヘッダーの名前は、「。」で開始できません。 または &quot;$&quot;.
* IPアドレスは使用できません。
* 内部アドビアドレス(.adobe.) は許可されません。
