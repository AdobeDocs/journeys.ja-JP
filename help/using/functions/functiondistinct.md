---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: 関数の区別について
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
