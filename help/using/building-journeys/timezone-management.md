---
title: タイムゾーン管理
description: タイムゾーンの管理について
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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# タイムゾーン管理 {#timezone_management}

タイムゾーンの定義は、次のアクティビティで使用できます。

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

この旅行のエントリイベントに名前空間がある場合、つまり、その旅行がデータプラットフォームのReal-time Customer Profileサービスに到達できる場合、タイムゾーンは、旅に出る個人のプロファイルで指定されたタイムゾーンで事前に定義されます。 個人のプロファイルにタイムゾーンが含まれていない場合は、インスタンスのタイムゾーンが使用されます。 インスタンスのタイムゾーンについては、管理者に問い合わせてください。

![](../assets/journey73.png)

タイムゾーンも修正できます。 事前定義済みのタイムゾーンをクリアし、ドロップダウンリストから1つ選択します。 固定タイムゾーンを使用する場合は、個人が旅行に参加するときと同じタイムゾーンになります。

![](../assets/journey72.png)

最後に、ステップに入る各人に対してタイムゾーンを動的に設定することができます。 この場合、式エディターを使用して、この情報を取得する場所を選択します（イベントまたはデータソースから取得できます）。 [](../expression/expressionadvanced.md)を参照してください。


旅行の開始日と終了日を特定のタイムゾーンにリンクすることはできません。 インスタンスのタイムゾーンに自動的に関連付けられます。
