---
product: adobe campaign
solution: Journey Orchestration
title: 関数
description: 関数について
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 73%

---


# 関数 {#concept_p1r_qj5_dgb}

関数は異なる署名を持つことができます（順序付けられたパラメーターの異なるセット）。 関数のシグネチャは、0 ～ N式を順序付けられたパラメーターとして持つことができます。

`<function name>`(`<expression as param 1>`、 `<expression as param 2>`、...、`<expression as param N>`)

各関数は、特定の戻り値の型を持ちます。

次に、サポートされる関数のリストを示します。

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
| コンバージョン変換 | [toBool](../functions/functiontobool.md) |
| コンバージョン変換 | [toDateTime](../functions/functiontodatetime.md) |
| コンバージョン変換 | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| コンバージョン変換 | [toDecimal](../functions/functiontodecimal.md) |
| コンバージョン変換 | [toDuration](../functions/functiontoduration.md) |
| コンバージョン変換 | [toInteger](../functions/functiontointeger.md) |
| コンバージョン変換 | [toString](../functions/functiontostring.md) |
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
| リスト | [distinct](../functions/functiondistinct.md) |
| リスト | [distinctCount](../functions/functiondistinctcount.md) |
| リスト | [in](../functions/functionin.md) |
| リスト | [listSize](../functions/functionlistsize.md) |
| リスト | [serializeList](../functions/functionserializelist.md) |
| リスト | [sort](../functions/functionsort.md) |
| 計算数学 | [random](../functions/functionrandom.md) |
| 計算数学 | [round](../functions/functionround.md) |
|  バイト長文字列 | [concat](../functions/functionconcat.md) |
|  バイト長文字列 | [contain](../functions/functioncontain.md) |
|  バイト長文字列 | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
|  バイト長文字列 | [endWith](../functions/functionendwith.md) |
|  バイト長文字列 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
|  バイト長文字列 | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
|  バイト長文字列 | [indexOf](../functions/functionindexof.md) |
|  バイト長文字列 | [isEmpty](../functions/functionisempty.md) |
|  バイト長文字列 | [isNotEmpty](../functions/functionisnotempty.md) |
|  バイト長文字列 | [lastIndexOf](../functions/functionlastindexof.md) |
|  バイト長文字列 | [length](../functions/functionlength.md) |
|  バイト長文字列 | [lower](../functions/functionlower.md) |
|  バイト長文字列 | [matchRegExp](../functions/functionmatchregexp.md) |
|  バイト長文字列 | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
|  バイト長文字列 | [replace](../functions/functionreplace.md) |
|  バイト長文字列 | [replaceAll](../functions/functionreplaceall.md) |
|  バイト長文字列 | [startWith](../functions/functionstartwith.md) |
|  バイト長文字列 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
|  バイト長文字列 | [substr](../functions/functionsubstr.md) |
|  バイト長文字列 | [trim](../functions/functiontrim.md) |
|  バイト長文字列 | [upper](../functions/functionupper.md) |
|  バイト長文字列 | [uuid](../functions/functionuuid.md) |