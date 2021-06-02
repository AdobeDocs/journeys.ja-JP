---
product: adobe campaign
title: in
description: の関数について説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 25%

---

# in {#in}

最初の引数値がリストに含まれているかどうかを確認します。 チェックは、各引数値のEqualを使用して実行されます。 引数の値が見つかった場合はtrueを返し、それ以外の場合はfalseを返します。

`<expression>`の型は、リストの項目と一致する必要があります。 リマインダーとして、リストの項目のタイプが互いに一致する必要があります。

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
