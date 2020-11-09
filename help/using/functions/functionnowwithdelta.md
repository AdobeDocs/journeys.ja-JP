---
title: nowWithDelta
description: nowWithDelta関数について
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 7%

---


# nowWithDelta {#nowWithDelta}

オフセットを含む現在の日時を返します。 タイムゾーンIDを指定した場合は、タイムゾーンのオフセットが適用されます。 For more information on data types, refer to [this page](../expression/data-types.md).

## カテゴリ

日付

## 関数の構文

`nowWithDelta(<parameters>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| delta | 正または負の整数値 |
| 日付部 | 文字列としての年、月、日、時間、分または秒 |
| タイムゾーンID | タイムゾーン値の文字列表現です。 詳しくは、「 [データ型](../expression/data-types.md)」を参照してください。 タイムゾーンIDは、文字列定数である必要があります。 フィールド参照や式は使用できません。 |

## 署名と戻り値の型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTimeを返します。

## 例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

2時間前のdateTimeを返します。
