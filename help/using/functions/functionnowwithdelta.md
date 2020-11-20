---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: nowWithDelta関数について
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
