---
product: adobe campaign
title: toString
description: toString関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 10%

---

# toString {#toString}

引数の値を、型に応じて文字列値に変換します。 データタイプの詳細については、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

コンバージョン

## 関数の構文

`toString(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| dateTime | 日付をUTC形式に変換します |
| dateTimeOnly | 日付をUTC形式に変換します |
| duration | 対応するミリ秒数を文字列に変換する |
| タイムゾーン | タイムゾーンid文字列表現(JODA id)への変換 |
| 整数 | 値を文字列表現に変換します（1は「1」になります） |
| decimal | 値の文字列表現に変換されます（1.5は「1.5」になります） |
| ブール型 | trueの場合はブール値を「true」に、falseの場合は「false」に変換します。 |

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

「4」を返します。
