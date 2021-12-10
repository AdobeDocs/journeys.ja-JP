---
product: adobe campaign
title: 演算子
description: 高度な式で使用できる演算子について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 100%

---

# 演算子 {#concept_wd5_pj5_dgb}

演算子には、単項演算子と二項演算子の 2 種類があります。左単項演算子と右単項演算子があります。

```json
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

サポートされている演算子の一覧を以下に示します。

## 論理  {#logical}

### and

```json
<expression1> and <expression2>
```

&lt;expression1> と &lt;expression2> は両方ともブール値である必要があります。結果はブール値です。

例：

```json
3.14 > 2 and 3.15 < 1
```

### or



```json
<expression1> or <expression2>
```

&lt;expression1> と &lt;expression2> は両方ともブール値である必要があります。結果はブール値です。

例：

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> はブール値である必要があります。結果はブール値です。

例：

```json
not 3.15 < 1
```

## 比較 {#comparison}

### is null



```json
<expression> is null
```

結果はブール値です。

null は、式に評価値がないことを意味します。

例：

```json
@{BarBeacon.location} is null
```

### is not null



```json
<expression> is not null
```

結果はブール値です。

null は、式に評価値がないことを意味します。

例：

```json
@ is not null
```

### has null



```json
<expression> has null
```

&lt;expression> はリストである必要があります。結果はブール値です。

リストに少なくとも 1 つの null 値が含まれているかどうかを識別するのに役立ちます。

例：

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

&lt;expression1> と &lt;expression2> の両方が同じデータタイプである必要があります。結果はブール値です。

例：

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### ! =



```json
<expression1> != <expression2>
```

&lt;expression1> と &lt;expression2> の両方が同じデータタイプである必要があります。結果はブール値です。

例：

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
42 <= 3.14
```

## 算術計算 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

&lt;expression2> は 0 以外である必要があります（0 の場合は戻り値が 0 になります）。

例：

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
3 % 2 -- returns 1.
```

## 数値計算 {#math}

### is numeric



```json
<expression> is numeric
```

式のタイプは整数または小数です。

例：

```json
@ is numeric
```

### is integer



```json
<expression> is integer
```

式のタイプは整数です。

例：

```json
@ is integer
```

### is decimal



```json
<expression> is decimal
```

式のタイプは小数です。

例：

```json
@ is decimal
```

## 文字列 {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

2 つの式を連結します。

一方の式は、連結される文字列である必要があります。

例：

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 日付 {#date}

### +



```json
<expression> + <duration>
```

日時、日時のみ、期間のいずれかに期間を連結します。

例：

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
