---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: 関数gstListItemの詳細
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 17%

---


# getListItem {#gestListItem}

渡されたインデックスにあるリストの項目を返します。

## カテゴリ

リスト

## 関数の構文

`getListItem(<parameters>)`

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
| index | integer |

## 署名と戻り値の型

`getListItem(<listInteger>,<index>)`

整数のリストを返します。

`getListItem(<listDecimal>,<index>)`

小数のリストを返します。

`getListItem(<listString>,<index>)`

文字列のリストを返します。

`getListItem(<listDateTimeOnly>,<index>)`

タイムゾーンを考慮せずに、日付時刻のリストを返します。

`getListItem(<listDateTime>,<index>)`

日付時間のリストを返します。

`getListItem(<listBoolean>,<index>)`

ブール値のリストを返します。

`getListItem(<listDuration>,<index>)`

期間のリストを返します。

## 例

`getListItem([10, 2, 3], 1)`

戻り値は&quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
戻り値は&quot;C&quot;

値が「イベント.appVersion」のイベントフィールドの例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

戻り値 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

戻り値は&quot;20&quot;