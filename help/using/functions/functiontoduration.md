---
product: adobe campaign
title: toDuration
description: toDuration 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 100%

---

# toDuration {#toDuration}

引数の値を期間に変換します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

変換

## 関数の構文

`toDuration(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601 の期間形式 PnDTnHnMn.nS に基づく形式（日数は正確に 24 時間と見なされます） |
| 整数 | ミリ秒数 |

文字列式の場合：指定できる形式は、ISO-8601 期間形式 PnDTnHnMn.nS に基づいたもので、1 日は正確に 24 時間と見なされます。

文字列は、ASCII の負または正の記号で表されるオプションの符号で始まります。負の場合は、期間全体が負の値になります。ASCII 文字「P」が次に現れ、大文字または小文字で表されます。その後に 4 つのセクションがあり、それぞれが数値とサフィックスで構成されます。各セクションには、日、時間、分および秒を示す「D」、「H」、「M」および「S」の ASCII サフィックスがあります（大文字でも小文字でもかまいません）。サフィックスは、順序に従って現れる必要があります。ASCII 文字「T」は、時、分、秒のセクションの最初の出現箇所（存在する場合）より前に記述する必要があります。4 つのセクションのうち少なくとも 1 つが存在し、「T」が存在する場合は、「T」の後に少なくとも 1 つのセクションが存在する必要があります。各セクションの数値部分は、1 つ以上の ASCII 数字で構成される必要があります。数字の先頭には、ASCII の負または正の記号を付けてもかまいません。日数、時間数および分数は long 型の値に解析される必要があります。秒数は long 型の値（オプションで小数を含む）に解析される必要があります。小数点はドットまたはコンマです。小数部は 0～9 桁まで可能です。

## シグネチャと戻り値のタイプ

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

## 例

`toDuration("PT10H")`

10 時間の期間を返します。

`toDuration("PT4S")`

4 秒の期間を返します。

`toDuration(4000)`

4 秒の期間を返します。
