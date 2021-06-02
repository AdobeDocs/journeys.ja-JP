---
product: adobe campaign
title: データタイプ
description: 高度な式のデータ型について説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 5%

---

# データタイプ {#concept_gp3_rj5_dgb}

技術的には、定数には常にデータ型が含まれます。 リテラル式では、値のみを指定します。 データ型は、値から推論できます（例えば、文字列、整数、10進数など）。 日付時間などの特定のケースでは、表現に専用の関数を使用します。

以下の節では、様々なデータタイプ式とその表現方法について説明します。

## 文字列 {#string}

**説明**

一般的な文字列。 使用可能なメモリ量など、環境から取り出される暗黙的なサイズを除いて、特定のサイズはありません。

JSON形式：文字列

シリアル化形式：UTF-8

**リテラル表現**

```
"<value>"
```

```
'<value>'
```

**例**

```
"hello world"
```

```
'hello world'
```

## 整数 {#integer}

**説明**

-2^63～2^63-1の整数値。

JSON形式：数値

**リテラル表現**

```
<integer value>
```

**例**

```
42
```

## decimal {#decimal}

**説明**

10 進数. 浮動値を表します。

* double型の最大正の有限値(2-2^-52)x2^1023
* double型の最小正の正の正の値、2-1022
* double型の最小の正のゼロ以外の値、p-1074

JSON形式：数値

シリアル化形式：&#39;.&#39;を使用 を小数点区切り文字として使用します。

**リテラル表現**

```
<integer value>.<integer value>
```

**例**

```
3.14
```

## boolean {#boolean}

**説明**

小文字で書かれたブール値：trueまたはfalse

JSON形式：Boolean

**リテラル表現**

```
true
```

```
false
```

**例**

```
true
```

## dateTimeOnly {#date-time-only}

**説明**

タイムゾーンのない日時を表し、年 — 月 — 日 — 時 — 分 — 秒 — ミリ秒と表示されます。

タイムゾーンを保存または表すものではありません。 代わりに、誕生日に使用される日付の説明で、壁時計に表示される現地時間と組み合わせます。

オフセットやタイムゾーンなどの追加情報がない限り、タイムライン上の瞬時を表すことはできません。

シリアル化形式：ISO-8601拡張オフセット日時形式。

値の逆シリアル化とシリアル化には、 DateTimeFormatter ISO_LOCAL_DATE_TIMEを使用します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**リテラル表現**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**説明**

タイムゾーンも考慮する日時定数。 UTCからのオフセットを持つ日時を表します。

オフセットの追加情報を使用して、瞬時に表示できます。 これは、世界のある場所で特定の「瞬間」を表す方法です。

JSON形式：文字列。

toDateTime関数でカプセル化する必要があります。

シリアル化形式：ISO-8601拡張オフセット日時形式。

値の逆シリアル化とシリアル化には、 DateTimeFormatter ISO_OFFSET_DATE_TIMEを使用します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

エポック値を渡す整数を渡すこともできます。 [詳細情報](https://www.epochconverter.com)

タイムゾーンは、オフセットまたはタイムゾーンコードで指定できます(例：Europe/Paris、Z - UTC)。

**リテラル表現**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**例**

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
toDateTime(1560762190189)
```

## duration {#duration}

**説明**

「34.5秒」など、時間に基づく時間を表します。 量や時間をミリ秒単位でモデル化します。

サポートされる時間単位は次のとおりです。ミリ秒、秒、分、時間、日（日）（日が24時間）です。 年と月は一定の時間ではないので、サポートされません。

JSON形式：文字列。

toDuration関数でカプセル化する必要があります。

シリアル化形式：タイムゾーンIDのシリアル化を解除するために、java関数java.timeを使用します。

Duration.parse:指定できる形式は、ISO-8601デュレーション形式PnDTnHnMn.nSに基づき、日は正確に24時間と見なされます。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**リテラル表現**

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**例**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## リスト {#list}

**説明**

角括弧を区切り文字として使用する式のコンマ区切りリスト。

多型はサポートされていないので、リストに含まれるすべての式は同じ型を持つ必要があります。

**リテラル表現**

```
[<expression>, <expression>, ... ]
```

**例**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
