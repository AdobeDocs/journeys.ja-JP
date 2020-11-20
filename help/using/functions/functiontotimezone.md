---
product: adobe campaign
solution: Journey Orchestration
title: toTimeZone
description: toTimeZone関数について学びます
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
