---
product: adobe campaign
title: nowWithDelta
description: nowWithDelta 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# nowWithDelta {#nowWithDelta}

オフセットを含んだ現在の日時を返します。 タイムゾーン ID を指定した場合は、タイムゾーンオフセットが適用されます。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

日付

## 関数の構文

`nowWithDelta(<parameters>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| delta | 正または負の整数値 |
| 日時の構成要素 | 「years」、「months」、「days」、「hours」、「minutes」、「seconds」のいずれかを文字列として指定します |
| タイムゾーン ID | タイムゾーン値の文字列表現。 詳しくは、[データタイプ](../expression/data-types.md)を参照してください。タイムゾーン ID は文字列定数である必要があります。フィールド参照や式は使用できません。 |

## シグネチャと戻り値のタイプ

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

日時を返します。

## 例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

正確に 2 時間前の日時を返します。
