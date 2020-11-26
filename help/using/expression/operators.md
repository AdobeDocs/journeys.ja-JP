---
product: adobe campaign
solution: Journey Orchestration
title: オペレーター
description: 高度な式の演算子について説明します。
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

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

## 論理  {#logical}

### および

**リテラル式**

```<expression1> and <expression2>```

&lt;式1>と&lt;式2>の両方をブール値にする必要があります。 結果はbooleanです。

**例**

```3.14 > 2 and 3.15 < 1```

### または

**リテラル式**

```<expression1> or <expression2>```

&lt;式1>と&lt;式2>の両方をブール値にする必要があります。 結果はbooleanです。

**例**

```3.14 > 2 or 3.15 < 1```

### not

**リテラル式**

```not <expression>```

&lt;式>はブール値である必要があります。 結果はbooleanです。

**例**

```not 3.15 < 1```

## 比較 {#comparison}

### 値がnull

**リテラル式**

```<expression> is null```

結果はbooleanです。

nullは、式に評価された値がないことを意味します。

**例**

```@{BarBeacon.location} is null```

### nullでない

**リテラル式**

```<expression> is not null```

結果はbooleanです。

nullは、式に評価された値がないことを意味します。

**例**

```@ is not null```

### nullを含む

**リテラル式**

```<expression> has null```

&lt;式>はリストでなければなりません。 結果はbooleanです。

リストに少なくとも1つのnull値が含まれていることを識別するのに役立ちます。

**例**

```["foo", "bar", null] has null``` はtrueを返します。

```["foo", "bar", ""] has null``` &quot;&quot;はnullとは見なされないので、falseを返します。

### ==

**リテラル式**

```<expression1> == <expression2>```

&lt;式1>と&lt;式2>の両方が同じデータ型である必要があります。 結果はbooleanです。

**例**

```3.14 == 42```

```"foo" == "bar"```

### !=

**リテラル式**

```<expression1> != <expression2>```

&lt;式1>と&lt;式2>の両方が同じデータ型である必要があります。 結果はbooleanです。

**例**

```3.14 != 42```

```"foo" != "bar"```

### >

**リテラル式**

```<expression1> > <expression2>```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

**例**

```3.14 > 42```

### >=

**リテラル式**

```<expression1> >= <expression2>```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

**例**

```42 >= 3.14```

### &lt;

**リテラル式**

```<expression1> < <expression2>```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

**例**

```42 < 3.14```

### &lt;=

**リテラル式**

```<expression1> <= <expression2>```

DatetimeはDatetimeと比較できます。

Datetimeonlyは、Datetimeonlyと比較できます。

整数と小数の両方を、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はbooleanです。

**例**

```42 <= 3.14```

## 演算 {#arithmetic}

### +

**リテラル式**

```<expression1> + <expression2>```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

**例**

```1 + 2``` 戻り値3

### -

**リテラル式**

```<expression1> - <expression2>```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

**例**

```2 - 1``` 戻り値

### /

**リテラル式**

```<expression1> / <expression2>```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

&lt;式2>は0に等しくない（0を返す）。

**例**

```4 / 2``` returns 2

### *

**リテラル式**

```<expression1> * <expression2>```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

**例**

```3 * 4``` 戻り値12

### %

**リテラル式**

```<expression1> % <expression2>```

どちらの式も数値（整数または10進）である必要があります。

結果も数値です。

**例**

```3 % 2``` は、1を返します。

## 計算数学 {#math}

### 数値

**リテラル式**

```<expression> is numeric```

式のタイプは整数または10進です。

**例**

```@ is numeric```

### integer

**リテラル式**

```<expression> is integer```

式のタイプは整数です。

**例**

```@ is integer```

### は小数

**リテラル式**

```<expression> is decimal```

式のタイプは10進です。

**例**

```@ is decimal```

## 文字列{#string}

### +

**リテラル式**

```<string> + <expression>```

```<expression> + <string>```

2つの式が連結されます。

1つの式は、チェーン文字列である必要があります。

**例**

```"the current time is " + (now())``` 「現在の時間は2019-09-23T09:30:06.693Z」を返します。

```(now()) + " is the current time"``` は、&quot;2019-09-23T09:30:06.693Zは現在の時刻&quot;を返します。

```"a" + "b" + "c" + 1234``` は、&quot;abc1234&quot;を返します。

## 日付 {#date}

### +

**リテラル式**

```<expression + <duration>```

dateTime、dateTimeOnlyまたはdurationに期間を追加します。

**例**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` は、2011-12-03T15:30:30Zを返します。

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` は、2011-12-03T15:30:30を返します。

```now() + toDuration("PT1H")``` 現在の時刻から1時間後に（UTCタイムゾーンで）dateTimeを返します

```toDuration("PT1H") + toDuration("PT1H")``` PT2Hを返す
