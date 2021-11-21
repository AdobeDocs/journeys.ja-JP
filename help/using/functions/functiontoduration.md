---
product: adobe campaign
title: toDuration
description: toDuration 関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 3%

---

# toDuration {#toDuration}

引数の値を期間に変換します。 データタイプについて詳しくは、 [このページ](../expression/data-types.md).

## カテゴリ

コンバージョン

## 関数の構文

`toDuration(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601 期間形式 PnDTnHnMn.nS に基づく形式（日数は正確に 24 時間と見なされます） |
| 整数 | ミリ秒数 |

文字列式の場合：指定できる形式は、ISO-8601 デュレーションフォーマット PnDTnHnMn.nS に基づき、日は正確に 24 時間と見なされます。

文字列は、ASCII の負または正の記号で示されるオプションの記号で始まります。 負の場合は、期間全体が負の値になります。 ASCII 文字「P」は大文字または小文字で表されます。 次に、4 つのセクションがあり、それぞれが数値とサフィックスで構成されます。 各セクションでは、ASCII の「D」、「H」、「M」、「S」のサフィックスを日、時間、分、秒で使用し、大文字と小文字で使用できます。 サフィックスは、順番に付加する必要があります。 ASCII 文字「T」は、1 時間、1 分、2 秒のセクションの最初の出現箇所（存在する場合）より前に記述する必要があります。 4 つのセクションのうち少なくとも 1 つが存在し、「T」が存在する場合は、「T」の後に少なくとも 1 つのセクションが存在する必要があります。 各セクションの数値部分は、1 つ以上の ASCII 数字で構成する必要があります。 数字の先頭には、ASCII の負または正の記号を付けることができます。 解析に必要な日数、時間数、分数。 分数（省略可能）と共に解析する秒数を指定します。 小数点は、ドットまたはコンマです。 小数部は、0 から 9 桁までの値を持つことができます。

## 署名と戻り値の型

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

## 例

`toDuration("PT10H")`

10 時間の期間を返します。

`toDuration("PT4S")`

期間 4 秒を返します。

`toDuration(4000)`

期間 4 秒を返します。
