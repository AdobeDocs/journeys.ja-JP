---
title: タイムゾーン管理
description: タイムゾーン管理について説明します。
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 2%

---



# タイムゾーン管理 {#timezone_management}

タイムゾーンは、旅の [プロパティ](../building-journeys/changing-properties.md) で定義できます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含む遍歴のすべてのアクティビティに使用されます。

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するかを選択できます。

## 固定タイムゾーンの定義 {#fixed-timezone}

タイムゾーンも修正できます。 定義済みのタイムゾーンをクリアし、ドロップダウンリストからタイムゾーンを選択します。 固定タイムゾーンを使用する場合は、そのタイムゾーンを訪問するすべてのユーザーが同じタイムゾーンになります。

タイムゾーンを設定するには、 **[!UICONTROL プロパティ]**&#x200B;でタイムゾーンを選択します。

![](../assets/journey73.png)

## プロファイルを使用した遍歴タイムゾーンの定義 {#timezone-from-profiles}

この旅行の入口イベントに名前空間がある場合、つまり、その旅行がAdobe Experience Platformのリアルタイム顧客プロファイルサービスに到達できる場合、タイムゾーンは、旅行中の個人のプロファイルに指定されたタイムゾーンで事前に定義されます。

タイムゾーンがAdobe Experience Platformプロファイルで定義されている場合は、そのタイムゾーンを遍歴で取得できます。

個々のプロファイルにタイムゾーンが含まれていない場合、取得されるタイムゾーンはtimezoneフィールドに定義されているタイムゾーンになります。

これを行うには、「 **[!UICONTROL Properties]**」で、「Useプロファイルタイムゾーンin timers and conditions ****」をチェックします。

![](../assets/journey72.png)

## 式でのタイムゾーンの使用 {#timezone-in-expressions}

旅行の開始日と終了日を特定のタイムゾーンにリンクすることはできません。 これらは、インスタンスのタイムゾーンに自動的に関連付けられます。
