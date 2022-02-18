---
product: adobe campaign
title: toDateOnly
description: toDateOnly 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

---

# toDateOnly{#toDateOnly}

引数値を日付のみの値に変換します。

## カテゴリ

変換

## 関数の構文

`toDateOnly(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601 形式つまり「YYYY-MM-DD」形式（XDM 日付形式）の日付 | 文字列 |
| 日付 | 日付 |

## シグネチャと戻り値のタイプ

`toDateOnly(<date>)`

`toDateOnly(<string>)`

タイムゾーンを無視して日時を返します。

## 例

`toDateOnly("2016-08-18")`

2016/08/18 を表す dateOnly オブジェクトを返します。
