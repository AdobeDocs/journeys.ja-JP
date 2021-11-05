---
product: adobe campaign
title: getListItem
description: 関数 gstListItem の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 21%

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
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |
| index | 整数 |

## 署名と戻り値の型

`getListItem(<listInteger>,<index>)`

整数を返します。

`getListItem(<listDecimal>,<index>)`

小数を返します。

`getListItem(<listString>,<index>)`

文字列を返します。

`getListItem(<listDateTimeOnly>,<index>)`

タイムゾーンを考慮せずに、日時を返します。

`getListItem(<listDateTime>,<index>)`

日時を返します。

`getListItem(<listDateOnly>,<index>)`

日付のリストを返します。

`getListItem(<listBoolean>,<index>)`

ブール値を返します。

`getListItem(<listDuration>,<index>)`

期間を返します。

## 例

`getListItem([10, 2, 3], 1)`

&quot;2&quot;を返します

`getListItem(["A", "B", "C"], 2)`
「C」を返します。

イベントフィールド「event.appVersion」と値の例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

戻り値 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

&quot;20&quot;を返します
