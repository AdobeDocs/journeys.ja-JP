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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# nowWithDelta {#nowWithDelta}

オフセットを含む現在の日時を返します。 タイムゾーンIDを指定した場合は、タイムゾーンのオフセットが適用されます。 データタイプの詳細については、を参照してくださ [](../expression/data-types.md)い。

## カテゴリ

日付

## 関数の構文

`nowWithDelta(<parameters>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| デルタ | 正または負の整数値 |
| 日付部 | 年、月、日、時間、分、秒を文字列として |
| タイムゾーンID | タイムゾーン値の文字列表現。 詳しくは、を参照してくださ [](../expression/data-types.md)い。 タイムゾーンIDは文字列定数である必要があります。 フィールド参照または式は使用できません。 |

## 署名と戻り値の型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTimeを返します。

## 例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

2時間前のdateTimeを返します。
