---
title: toTimeZone
description: toTimeZone関数について学びます
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 13%

---


# toTimeZone {#toTimeZone}

文字列値をタイムゾーンに変換します。

## カテゴリ

コンバージョン変換

## 関数の構文

`toTimeZone(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値には、ゾーンIDを含める必要があります。 フィールド参照または式を指定できます |

## 署名と戻り値の型

`toTimeZone(<string>)`

タイムゾーンを返します。

## 例

`toTimeZone("UTC")`

UTCを返します。
