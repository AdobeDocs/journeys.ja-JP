---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: 関数の区別について
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 20%

---

# distinct {#distinct}

リストの明確な値をnull値なしで返します。

## カテゴリ

リスト

## 関数の構文

`distinct(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |

## 署名と戻り値の型

`distinct(<listInteger>)`

整数のリストを返します。

`distinct(<listDecimal>)`

小数のリストを返します。

`distinct(<listString>)`

文字列のリストを返します。

`distinct(<listDateTimeOnly>)`

タイムゾーンを考慮せずに、日付時刻のリストを返します。

`distinct(<listDateTime>)`

日付時間のリストを返します。

`distinct(<listBoolean>)`

ブール値のリストを返します。

`distinct(<listDuration>)`

期間のリストを返します。

## 例

`distinct([10,2,10,null])`

戻り値 `[10, 2]`.
