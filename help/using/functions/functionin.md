---
title: '-'
description: この機能については、
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# -{#in}

最初の引数の値がリスト内にあるかどうかを確認します。 チェックは、各引数の値に対してEqualを使用して実行されます。 引数の値が見つかった場合はtrueを返し、それ以外の場合はfalseを返します。

のタイプは、リストの `<expression>` 項目と一致する必要があります。 リマインダーとしてのリストの項目のタイプは、相互に一致する必要があります。

## カテゴリ

リスト

## 関数の構文

`in(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| ブール値 | ブール値 |
| 整数 | 整数 |
| 小数 | 小数 |
| 期間 | 期間 |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |

## 署名と戻り値の型

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

ブール値を返します。

## 例

`in(4,[4,5,3,4])`

trueを返します。

`in(8,[4,5,3,4])`

falseを返します。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
