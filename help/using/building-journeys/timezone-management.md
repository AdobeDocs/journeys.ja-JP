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
source-git-commit: f4f41428b19f611da15b20a1788b240fadfd49fa

---



# タイムゾーン管理 {#timezone_management}

タイムゾーンは、旅のプロパティで [定義で](../building-journeys/changing-properties.md) きます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含む遍歴のすべてのアクティビティに使用されます。

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するように選択できます。

## 固定タイムゾーンの定義 {#fixed-timezone}

タイムゾーンも修正できます。 事前定義済みのタイムゾーンをクリアし、ドロップダウンリストから1つ選択します。 固定タイムゾーンを使用する場合は、個人が旅行に参加するときと同じタイムゾーンになります。

これを行うには、でタ **[!UICONTROL Properties]**&#x200B;イムゾーンを選択します。

![](../assets/journey73.png)

## プロファイルを使用した旅行タイムゾーンの定義 {#timezone-from-profiles}

この旅行のエントリイベントに名前空間がある場合、つまり、その旅行がデータプラットフォームのReal-time Customer Profileサービスに到達できる場合、タイムゾーンは、旅に出る個人のプロファイルで指定されたタイムゾーンで事前に定義されます。

タイムゾーンがエクスペリエンスプラットフォームプロファイルで定義されている場合は、そのタイムゾーンを遍歴で取得できます。

個人のプロファイルにタイムゾーンが含まれていない場合、取得されるタイムゾーンはtimezoneフィールドで定義されたタイムゾーンになります。

これを行うには、チェック **[!UICONTROL Properties]**&#x200B;を入れま **[!UICONTROL Use Profile timezone in timers and conditions]**&#x200B;す。

![](../assets/journey72.png)

## 式でのタイムゾーンの使用 {#timezone-in-expressions}

タイムゾーンは、高度な式エディターを使用して式を作成するために使用します。 この場合、式エディターを使用して、この情報を取得するシステムの場所を選択します。 [](../expression/expressionadvanced.md)を参照してください。

旅行の開始日と終了日を特定のタイムゾーンにリンクすることはできません。 インスタンスのタイムゾーンに自動的に関連付けられます。
