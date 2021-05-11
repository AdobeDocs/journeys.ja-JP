---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: 関数gstListItemの詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 18%

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
