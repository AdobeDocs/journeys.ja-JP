---
title: カスタムアクションの制限
description: カスタムアクションの制限について説明します
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

---


# カスタムアクションの制限 {#concept_lh2_df1_2gb}

カスタムアクションの使用に関するいくつかの制限を以下に示します。

* キャッピングや送信ボリュームのバッファリング/スムージングはありません。
* エラーが発生した場合、2回の再試行が系統的に実行されます。 受け取ったエラーメッセージに従って再試行回数を調整することはできません。
* 組み込みのイベ **[!UICONTROL Reaction]**ントを使用すると、すぐに使用できるアクションに対応できます(を参照してくださ[](../building-journeys/event-activities.md)い。 カスタムアクションを介して送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。
* カスタムアクションURLは動的パラメーターをサポートしていません。
* POSTおよびPUT呼び出しメソッドのみがサポートされます。
* クエリパラメーターまたはヘッダーの名前は、「。」で始めることはできません。 または &quot;$&quot;.
* IPアドレスは許可されません。
* 内部アドビアドレス(.adobe.)は許可されません。
