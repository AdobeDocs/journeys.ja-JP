---
product: adobe campaign
title: toDateOnly
description: toDateOnly 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '58'
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
