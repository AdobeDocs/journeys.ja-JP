---
product: adobe campaign
title: setDays
description: setDays 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# setDays {#setDays}

日時または日時のみの日を設定します。例えば、その月の特定の日まで待つ場合に、その日を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setDays(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | 日時のみ |
| 日 | 整数 |

## シグネチャと戻り値のタイプ

`setDays(<dateTime>,<days>)`

日時を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを無視して日時を返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Z を返します。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
