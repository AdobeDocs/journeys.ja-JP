---
product: adobe campaign
solution: Journey Orchestration
title: in
description: 関数について詳しくは、
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 24%

---


# in {#in}

最初の引数の値がリスト内にあるかどうかを確認します。 チェックは、各引数の値に対してEqualを介して実行されます。 引数の値が見つかった場合はtrueを返し、それ以外の場合はfalseを返します。

`<expression>`の型は、リストの項目と一致する必要があります。 リマインダーとしてのリストの項目のタイプは、互いに一致する必要があります。

## カテゴリ

リスト

## 関数の構文

`in(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
|  バイト長文字列 |  バイト長文字列 |
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
