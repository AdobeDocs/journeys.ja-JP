---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: toString関数について
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 8%

---


# toString {#toString}

引数の値を、型に応じて文字列値に変換します。 データタイプの詳細については、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

コンバージョン変換

## 関数の構文

`toString(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| dateTime | 日付をUTC形式に変換します。 |
| dateTimeOnly | 日付をUTC形式に変換します。 |
| duration | 文字列として対応するミリ秒数に変換する |
| 時間帯 | タイムゾーンid文字列表現(JODA id)に変換 |
| integer | 値の文字列表現に変換します（1は「1」になります）。 |
| decimal | 値の文字列表現に変換します（1.5は「1.5」に変換されます） |
| boolean | trueの場合はブール値を「true」に、falseの場合は「false」に変換します。 |

## 署名と戻り値の型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

文字列を返します。

## 例

`toString(4)`

&quot;4&quot;を返します。
