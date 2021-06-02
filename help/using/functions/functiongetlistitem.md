---
product: adobe campaign
title: getListItem
description: 関数gstListItemの詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 18%

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
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| index | 整数 |

## 署名と戻り値の型

`getListItem(<listInteger>,<index>)`

整数のリストを返します。

`getListItem(<listDecimal>,<index>)`

小数のリストを返します。

`getListItem(<listString>,<index>)`

文字列のリストを返します。

`getListItem(<listDateTimeOnly>,<index>)`

タイムゾーンを考慮せずに日付のリストを返します。

`getListItem(<listDateTime>,<index>)`

日付時間のリストを返します。

`getListItem(<listBoolean>,<index>)`

ブール値のリストを返します。

`getListItem(<listDuration>,<index>)`

期間のリストを返します。

## 例

`getListItem([10, 2, 3], 1)`

戻り値は「2」

`getListItem(["A", "B", "C"], 3)`
戻り値は「C」

値を持つイベントフィールド「event.appVersion」の例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

戻り値 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

戻り値：「20」
