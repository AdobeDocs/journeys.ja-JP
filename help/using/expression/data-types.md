---
product: adobe campaign
title: データタイプ
description: 高度な式でのデータ型について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 7%

---

# データタイプ {#concept_gp3_rj5_dgb}

技術的には、定数には常にデータ型が含まれます。 リテラル式では、値のみを指定します。 このデータ型は、値（文字列、整数、小数など）から推論できます。 日時などの特定のケースでは、表現に専用の関数を使用します。

以下の節では、様々なデータタイプ式とその表現方法に関する情報を提供します。

## 文字列 {#string}

**説明**

一般的な文字列。 使用可能なメモリ量など、環境から取得される暗黙のサイズ以外は、特定のサイズを持ちません。

JSON 形式：文字列

シリアル化形式：UTF-8

**リテラル表現**

```json
"<value>"
```

```json
'<value>'
```

**例**

```json
"hello world"
```

```json
'hello world'
```

## 整数 {#integer}

**説明**

-2^63～2^63-1 の整数値。

JSON 形式：数値

**リテラル表現**

```json
<integer value>
```

**例**

```json
42
```

## decimal {#decimal}

**説明**

小数. 浮動値を表します。

* 倍精度浮動小数点型の最大正の有限値 (2-2^-52)x2^1023
* 倍精度浮動小数点型の最小正の正の正の値、2-1022
* double 型の最小の 0 以外の値、p-1074

JSON 形式：数値

シリアル化形式：&#39;.&#39;の使用 を小数点区切り記号として使用します。

**リテラル表現**

```json
<integer value>.<integer value>
```

**例**

```json
3.14
```

## ブール型 {#boolean}

**説明**

小文字で書かれたブール値：true または false

JSON 形式：ブール値

**リテラル表現**

```json
true
```

```json
false
```

**例**

```json
true
```

## dateOnly {#date-only}

**説明**

タイムゾーンを持たない日付のみを表し、年 — 月 — 日として表示されます。

誕生日に使用される日付の説明です。

JSON 形式：文字列。

形式：YYYY-MM-DD(ISO-8601) の例：&quot;2021-03-11&quot;.

toDateOnly 関数でカプセル化できます。

値の逆シリアル化とシリアル化に DateTimeFormatter ISO_LOCAL_DATE_TIME を使用します。 [詳細情報](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**リテラル表現**

```json
date("<dateOnly in ISO-8601 format>")  
```

**例**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**説明**

タイムゾーンを持たない日時を表し、年 — 月 — 日 — 時間 — 分 — 秒 — ミリ秒と表示されます。

JSON 形式：文字列。

タイムゾーンは保存も表現もしません。 代わりに、誕生日に使用される日付の説明と、壁の時計で見られる現地時間の組み合わせです。

オフセットやタイムゾーンなどの追加情報がないと、タイムライン上のインスタントを表すことはできません。

toDateTimeOnly 関数でカプセル化できます。

シリアル化形式：ISO-8601 拡張オフセット日時形式。

値の逆シリアル化とシリアル化に DateTimeFormatter ISO_LOCAL_DATE_TIME を使用します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**リテラル表現**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**例**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**説明**

タイムゾーンも考慮する日時定数。 UTC からのオフセットを持つ日時を表します。

オフセットの追加情報を含む即時の情報として表示できます。 世界のある場所で特定の「瞬間」を表す方法です。

JSON 形式：文字列。

toDateTime 関数でカプセル化できます。

シリアル化形式：ISO-8601 拡張オフセット日時形式。

値の逆シリアル化とシリアル化に DateTimeFormatter ISO_OFFSET_DATE_TIME を使用します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

エポック値を渡す整数を渡すこともできます。 [詳細情報](https://www.epochconverter.com)

タイムゾーンは、オフセットまたはタイムゾーンコードで指定できます ( 例：ヨーロッパ/パリ、Z - UTC を意味します。

**リテラル表現**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**例**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## duration {#duration}

**説明**

「34.5 秒」など、時間に基づく時間を表します。 数量または時間をミリ秒単位でモデル化します。

サポートされる時間単位は次のとおりです。ミリ秒、秒、分、時間、日（日が 24 時間に等しい）。 年と月は一定の時間ではないので、サポートされません。

JSON 形式：文字列。

toDuration 関数でカプセル化する必要があります。

シリアル化形式：タイムゾーン ID を逆シリアル化するには、java 関数 java.time を使用します。

Duration.parse:受け入れられるフォーマットは、ISO-8601 デュレーションフォーマット PnDTnHnMn.nS に基づいており、日は正確に 24 時間と見なされます。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**リテラル表現**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**例**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**説明**

区切り文字として角括弧を使用する式のコンマ区切りリスト。

多型はサポートされていないので、リストに含まれるすべての式の型は同じにする必要があります。

**リテラル表現**

```json
[<expression>, <expression>, ... ]
```

**例**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
