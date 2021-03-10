---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: toDuration関数について学びます
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 3%

---


# toDuration {#toDuration}

引数の値を期間に変換します。 データタイプの詳細については、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

コンバージョン変換

## 関数の構文

`toDuration(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601の継続時間形式PnDTnHnMn.nSに基づく形式で、日数はちょうど24時間と見なされます |
| integer | ミリ秒数 |

文字列式:指定できる形式は、ISO-8601 duration形式のPnDTnHnMn.nSに基づき、日数はちょうど24時間と見なされます。

オプションの記号を含む文字列開始。ASCIIの負または正の記号で示します。 負の値の場合は、期間全体の値が無効になります。 ASCII文字の「P」は、大文字または小文字で示されます。 次に、4つのセクションがあり、それぞれ番号とサフィックスで構成されます。 セクションのASCII文字の「D」、「H」、「M」、「S」は日、時間、分、秒で表され、大文字と小文字で区切ります。 サフィックスは順番に付加する必要があります。 ASCII文字の「T」は、1時間、1分、2秒のセクションの1番目の値（存在する場合）の前に配置する必要があります。 4つのセクションのうちの少なくとも1つが存在し、「T」が存在する場合は、「T」の後に少なくとも1つのセクションが存在する必要があります。 各セクションの数値部分は、1つ以上のASCII数字で構成する必要があります。 数字の前には、ASCIIの負の記号または正の記号を付けることができます。 日数、時間数、分数は解析して処理する必要があります。 秒数は、オプションの分数と共に解析する必要があります。 小数点は、ドットまたはコンマで指定します。 小数部は、0 ～ 9の桁数で指定できます。

## 署名と戻り値の型

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

## 例

`toDuration("PT10H")`

10時間の期間を返します。

`toDuration("PT4S")`

4sの期間を返します。

`toDuration(4000)`

4sの期間を返します。
