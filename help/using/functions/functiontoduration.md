---
title: toDuration
description: toDuration関数について説明します。
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


# toDuration {#toDuration}

引数の値を期間に変換します。 For more information on data types, refer to [](../expression/data-types.md).

## カテゴリ

コンバージョン

## 関数の構文

`toDuration(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601継続時間形式PnDTnHnMn.nSに基づく形式で、日数は正確に24時間と見なされます。 |
| 整数 | ミリ秒数 |

文字列式の場合：使用できる形式は、ISO-8601の継続時間形式PnDTnHnMn.nSに基づいており、日数は正確に24時間と見なされます。

文字列は、ASCIIの負の記号または正の記号で示されるオプションの記号で始まります。 負の値の場合は、期間全体が無効になります。 ASCII文字の「P」は大文字または小文字で表されます。 次に、4つのセクションがあり、それぞれ番号とサフィックスで構成されます。 セクションのASCII文字のサフィックスは、「D」、「H」、「M」、「S」（日、時間、分、秒）で、大文字と小文字の区別は受け付けます。 サフィックスは順番に付加する必要があります。 ASCII文字の「T」は、1時間、1分、2秒の1番目のセクション（存在する場合）の前に配置する必要があります。 4つのセクションのうち少なくとも1つが存在し、「T」が存在する場合は、「T」の後に少なくとも1つのセクションが存在する必要があります。 各セクションの番号の部分は、1つ以上のASCII数字で構成する必要があります。 数字の前には、ASCIIの負の記号または正の記号を付けることができます。 日数、時間数、分数も解析する必要があります。 秒数は、オプションの分数と共に解析する必要があります。 小数点はドットまたはコンマで指定できます。 小数部は、0 ～ 9桁の数値を持つことができます。

## 署名と戻り値の型

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

## 例

`toDuration("PT10H")`

10時間の期間を返します。

`toDuration("PT4S")`

4秒の継続時間を返します。

`toDuration(4000)`

4秒の継続時間を返します。
