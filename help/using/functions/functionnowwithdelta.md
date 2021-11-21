---
product: adobe campaign
title: nowWithDelta
description: nowWithDelta 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 7%

---

# nowWithDelta {#nowWithDelta}

オフセットを含む現在の日時を返します。 タイムゾーン ID を指定した場合は、タイムゾーンオフセットが適用されます。 データタイプについて詳しくは、 [このページ](../expression/data-types.md).

## カテゴリ

日付

## 関数の構文

`nowWithDelta(<parameters>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| デルタ | 正または負の整数値 |
| 日付部分 | 文字列としての年、月、日、時間、分、秒 |
| タイムゾーン id | time zone 値の string 表現。 詳しくは、 [データタイプ](../expression/data-types.md). タイムゾーン ID は、文字列定数である必要があります。 フィールド参照や式は使用できません。 |

## 署名と戻り値の型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTime を返します。

## 例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

2 時間前の dateTime を返します。
