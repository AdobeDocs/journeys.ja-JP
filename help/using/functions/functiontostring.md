---
title: toString
description: toString関数について
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
source-wordcount: '114'
ht-degree: 7%

---


# toString {#toString}

引数の値を、型に応じて文字列値に変換します。 For more information on data types, refer to [this page](../expression/data-types.md).

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
