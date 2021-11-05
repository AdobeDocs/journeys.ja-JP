---
product: adobe campaign
title: toDateOnly
description: toDateOnly 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# toDateOnly{#toDateOnly}

引数の値を日付のみの値に変換します。

## カテゴリ

コンバージョン

## 関数の構文

`toDateOnly(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601 形式または「YYYY-MM-DD」形式の日付（XDM 日付形式） | 文字列 |
| 日付 | 日付 |

## 署名と戻り値の型

`toDateOnly(<date>)`

`toDateOnly(<string>)`

タイムゾーンを考慮せずに、日時を返します。

## 例

`toDateOnly("2016-08-18")`

2016-08-18を表す dateOnly オブジェクトを返します。
