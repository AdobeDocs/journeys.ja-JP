---
product: adobe campaign
title: getListItem
description: 関数gstListItemの詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 22%

---

# getListItem {#gestListItem}

指定されたインデックスのリストの項目を返します。

## カテゴリ

リスト

## 関数の構文

`getListItem(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| index | 整数 |

## 署名と戻り値の型

`getListItem(<listInteger>,<index>)`

整数を返します。

`getListItem(<listDecimal>,<index>)`

小数を返します。

`getListItem(<listString>,<index>)`

文字列を返します。

`getListItem(<listDateTimeOnly>,<index>)`

タイムゾーンを考慮せずに、datetimeを返します。

`getListItem(<listDateTime>,<index>)`

datetimeを返します。

`getListItem(<listBoolean>,<index>)`

ブール値を返します。

`getListItem(<listDuration>,<index>)`

期間を返します。

## 例

`getListItem([10, 2, 3], 1)`

戻り値は「2」

`getListItem(["A", "B", "C"], 2)`
戻り値は「C」

値を持つイベントフィールド「event.appVersion」の例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

戻り値 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

戻り値：「20」
