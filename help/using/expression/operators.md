---
product: adobe campaign
solution: Journey Orchestration
title: オペレーター
description: 高度な式の演算子について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 7%

---



# オペレーター {#concept_wd5_pj5_dgb}

演算子には次の2種類があります。単項演算子とバイナリ演算子。 左側の単項演算子と右側の単項演算子があります。

```
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

次に、サポートされる演算子のリストを示します。

## 論理{#logical}

### かつ

```
<expression1> and <expression2>
```

&lt;式1>と&lt;式2>の両方をブール値にする必要があります。 結果はbooleanです。

例：

```
3.14 > 2 and 3.15 < 1
```

### または



```
<expression1> or <expression2>
```

&lt;式1>と&lt;式2>の両方をブール値にする必要があります。 結果はbooleanです。

例：

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression> はboolean値である必要があります。結果はbooleanです。

例：

```
not 3.15 < 1
```

## 比較 {#comparison}

### 値がnull



```
<expression> is null
```

結果はbooleanです。

nullは、式に評価された値がないことを意味します。

例：

```
@{BarBeacon.location} is null
```

### nullでない



```
<expression> is not null
```

結果はbooleanです。

nullは、式に評価された値がないことを意味します。

例：

```
@ is not null
```

### nullを含む



```
<expression> has null
```

&lt;expression> はリストである必要があります。結果はbooleanです。

リストに少なくとも1つのnull値が含まれていることを識別するのに役立ちます。

例：

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

&lt;式1>と&lt;式2>の両方が同じデータ型である必要があります。 結果はbooleanです。

例：

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

&lt;式1>と&lt;式2>の両方が同じデータ型である必要があります。 結果はbooleanです。

例：

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

例：

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

例：

```
42 >= 3.14
```

### &lt;



```
<expression1> < <expression2>
```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

例：

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

例：

```
42 <= 3.14
```

## 算術{#arithmetic}

### +



```
<expression1> + <expression2>
```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

例：

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

例：

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

&lt;expression2> は0と等しくない（0を返す）必要があります。

例：

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

例：

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

例：

```
3 % 2 -- returns 1.
```

## 計算数学 {#math}

### 数値



```
<expression> is numeric
```

式のタイプは整数または10進です。

例：

```
@ is numeric
```

### integer



```
<expression> is integer
```

式のタイプは整数です。

例：

```
@ is integer
```

### は小数



```
<expression> is decimal
```

式のタイプは10進です。

例：

```
@ is decimal
```

## 文字列{#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

2つの式が連結されます。

1つの式は、チェーン文字列である必要があります。

例：

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 日付 {#date}

### +



```
<expression + <duration>
```

dateTime、dateTimeOnlyまたはdurationに期間を追加します。

例：

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
