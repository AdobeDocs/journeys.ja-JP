---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: nowWithDelta関数について
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---


# nowWithDelta {#nowWithDelta}

オフセットを含む現在の日時を返します。 タイムゾーンIDを指定した場合は、タイムゾーンのオフセットが適用されます。 データタイプの詳細については、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

日付

## 関数の構文

`nowWithDelta(<parameters>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| delta | 正または負の整数値 |
| 日付部 | 文字列としての年、月、日、時間、分または秒 |
| タイムゾーンID | タイムゾーン値の文字列表現です。 詳しくは、[データタイプ](../expression/data-types.md)を参照してください。 タイムゾーンIDは、文字列定数である必要があります。 フィールド参照や式は使用できません。 |

## 署名と戻り値の型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTimeを返します。

## 例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

2時間前のdateTimeを返します。
