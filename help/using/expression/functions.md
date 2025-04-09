---
product: adobe campaign
title: 関数
description: 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 80%

---

# 関数 {#concept_p1r_qj5_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


関数は、異なるシグネチャ（順序付きパラメーターの異なるセット）を持つことができます。関数シグネチャは、0～N 個の式を順序付きパラメーターとして持つことができます。

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

関数ごとに、固有の戻り値タイプがあります。

サポートされている関数の一覧を以下に示します。

## 主な関数

| カテゴリ | 関数 |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| 集計 | [avg](../functions/functionavg.md) |
| 集計 | [count](../functions/functioncount.md) |
| 集計 | [countOnlyNull](../functions/functioncountonlynull.md) |
| 集計 | [countWithNull](../functions/functioncountwithnull.md) |
| 集計 | [distinctCount](../functions/functiondistinctcount.md) |
| 集計 | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| 集計 | [max](../functions/functionmax.md) |
| 集計 | [min](../functions/functionmin.md) |
| 集計 | [sum](../functions/functionsum.md) |
| 変換 | [toBool](../functions/functiontobool.md) |
| 変換 | [toDateOnly](../functions/functiontodateonly.md) |
| 変換 | [toDateTime](../functions/functiontodatetime.md) |
| 変換 | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| 変換 | [toDecimal](../functions/functiontodecimal.md) |
| 変換 | [toDuration](../functions/functiontoduration.md) |
| 変換 | [toInteger](../functions/functiontointeger.md) |
| 変換 | [toString](../functions/functiontostring.md) |
| 日付 | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| 日付 | [inLastDays](../functions/functioninlastdays.md) |
| 日付 | [inLastHours](../functions/functioninlasthours.md) |
| 日付 | [inLastMonths](../functions/functioninlastmonths.md) |
| 日付 | [inLastYears](../functions/functioninlastyears.md) |
| 日付 | [inNextDays](../functions/functioninnextdays.md) |
| 日付 | [inNextHours](../functions/functioninnexthours.md) |
| 日付 | [inNextMonths](../functions/functioninnextmonths.md) |
| 日付 | [inNextYears](../functions/functioninnextyears.md) |
| 日付 | [now](../functions/functionnow.md) |
| 日付 | [nowWithDelta](../functions/functionnowwithdelta.md) |
| 日付 | [setHours](../functions/functionsethours.md) |
| 日付 | [setDays](../functions/functionsetdays.md) |
| 日付 | [updateTimeZone](../functions/functionupdatetimezone.md) |
| リスト | [distinct](../functions/functiondistinct.md) |
| リスト | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| リスト | [filter](../functions/functionfilter.md) |
| リスト | [getListItem](../functions/functiongetlistitem.md) |
| リスト | [in](../functions/functionin.md) |
| リスト | [intersect](../functions/functionintersect.md) |
| リスト | [listSize](../functions/functionlistsize.md) |
| リスト | [serializeList](../functions/functionserializelist.md) |
| リスト | [sort](../functions/functionsort.md) |
| 数値計算 | [random](../functions/functionrandom.md) |
| 数値計算 | [round](../functions/functionround.md) |
| 文字列 | [concat](../functions/functionconcat.md) |
| 文字列 | [contain](../functions/functioncontain.md) |
| 文字列 | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 文字列 | [endWith](../functions/functionendwith.md) |
| 文字列 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 文字列 | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| 文字列 | [indexOf](../functions/functionindexof.md) |
| 文字列 | [isEmpty](../functions/functionisempty.md) |
| 文字列 | [isNotEmpty](../functions/functionisnotempty.md) |
| 文字列 | [lastIndexOf](../functions/functionlastindexof.md) |
| 文字列 | [length](../functions/functionlength.md) |
| 文字列 | [lower](../functions/functionlower.md) |
| 文字列 | [matchRegExp](../functions/functionmatchregexp.md) |
| 文字列 | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| 文字列 | [replace](../functions/functionreplace.md) |
| 文字列 | [replaceAll](../functions/functionreplaceall.md) |
| 文字列 | [startWith](../functions/functionstartwith.md) |
| 文字列 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 文字列 | [substr](../functions/functionsubstr.md) |
| 文字列 | [trim](../functions/functiontrim.md) |
| 文字列 | [upper](../functions/functionupper.md) |
| 文字列 | [uuid](../functions/functionuuid.md) |
