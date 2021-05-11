---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: nowWithDelta関数について
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 8%

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
