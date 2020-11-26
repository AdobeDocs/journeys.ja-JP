---
product: adobe campaign
solution: Journey Orchestration
title: データタイプ
description: 高度な式でのデータタイプについて説明します。
translation-type: tm+mt
source-git-commit: f755f92d0479e2889dd7ed6dfa5e72d52c25634f
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 5%

---


# データタイプ {#concept_gp3_rj5_dgb}

技術的には、定数には常にデータ型が含まれます。 リテラル式では、値のみを指定します。 このデータ型は、値（文字列、整数、小数など）から推論できます。 日付時間などの特定のケースでは、表現に専用の関数を使用します。

以下の節では、様々なデータタイプの式とその表現方法について説明します。

## 文字列{#string}

**説明**

一般的な文字のシーケンス。 メモリの空き容量など、環境から暗黙的に取得されるサイズを除き、特定のサイズはありません。

JSON形式：文字列

シリアル化形式：UTF-8

**リテラル表現**

```"<value>"```

```'<value>'```

**例**

```"hello world"```

```'hello world'```

## integer {#integer}

**説明**

-2^63 ～ 2^63-1の整数値。

JSON形式：数値

**リテラル表現**

```<integer value>```

**例**

```42```

## decimal {#decimal}

**説明**

10 進数. これは、次の浮動値を表します。

* 重複型の最大正の有限値(2-2^-52)x2^1023
* 重複型の最小正の正の正規値、2-1022
* タイプ重複の最小のゼロ以外の値、p-1074

JSON形式：数値

シリアル化形式：&#39;.&#39;を使用 を小数点の区切り文字として使用します。

**リテラル表現**

```<integer value>.<integer value>```

**例**

```3.14```

## boolean {#boolean}

**説明**

小文字で書かれたブール値：trueまたはfalse

JSON形式：ブール値

**リテラル表現**

```true```

```false```

**例**

```true```

## dateTimeOnly {#date-time-only}

**説明**

タイムゾーンのない日付時刻を表し、年 — 月 — 日 — 時 — 分 — 秒 — ミリ秒で表示されます。

タイムゾーンは格納または表しません。 その代わりに、誕生日に使用される日付の説明と、壁掛けの時計に表示される現地時間が組み合わされます。

オフセットやタイムゾーンなどの追加情報がない場合は、タイムライン上の瞬間を表すことはできません。

シリアル化形式：ISO-8601拡張オフセット日時形式。

値のデシリアライズとシリアライズには、DateTimeFormatter ISO_LOCAL_DATE_TIMEを使用します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**リテラル表現**

```toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  ```

## dateTime {#date-time}

**説明**

タイムゾーンも考慮する日時定数。 UTCからのオフセットを持つ日時を表します。

オフセットの追加情報を使用して、瞬時に表示できます。 これは、世界のある場所で特定の「瞬間」を表す方法です。

JSON形式：文字列。

toDateTime関数にカプセル化する必要があります。

シリアル化形式：ISO-8601拡張オフセット日時形式。

値のデシリアライズとシリアライズには、DateTimeFormatter ISO_OFFSET_DATE_TIMEを使用します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

また、エポック値を渡す整数を渡すこともできます。 [詳細を表示](https://www.epochconverter.com)

タイムゾーンは、オフセットまたはタイムゾーンコードで指定できます(例：Europe/Paris、Z - UTC)。

**リテラル表現**

```toDateTime("<dateTime in ISO-8601 format>")```

```toDateTime(<integer value of an epoch in milliseconds>)```

**例**

```toDateTime("1977-04-22T06:00:00Z")```

```toDateTime("2011-12-03T15:15:30Z")```

```toDateTime("2011-12-03T15:15:30.123Z")```

```toDateTime("2011-12-03T15:15:30.123+02:00")```

```toDateTime("2011-12-03T15:15:30.123-00:20")```

```toDateTime(1560762190189)```

## duration {#duration}

**説明**

これは、「34.5秒」など、時間に基づく時間を表します。 ミリ秒単位で数量または時間をモデル化します。

サポートされる時間単位は次のとおりです。ミリ秒、秒、分、時間、日。日は24時間に等しくなります。 年と月は一定の期間ではないので、サポートされません。

JSON形式：文字列。

toDuration関数にカプセル化する必要があります。

シリアル化形式：タイムゾーンIDのシリアル化を解除するには、java関数java.timeを使用します。

Duration.parse:指定できる形式は、ISO-8601 duration形式PnDTnHnMn.nSに基づいており、日数はちょうど24時間と見なされます。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**リテラル表現**

```toDuration("<duration in ISO-8601 format>")```

```toDuration(<duration in milliseconds>)```

**例**

```toDuration("PT5S")``` 5秒で解析

```toDuration(500)``` 500ミリ秒として解析

```toDuration("PT20.345S")``` 解析を「20.345秒」として

```toDuration("PT15M") ``` 解析を「15分」（1分が60秒の場合）として

```toDuration("PT10H") ``` 解析を「10時間」（1時間が3600秒の場合）として解釈

```toDuration("P2D") ``` 「2日間」（日が24時間または86400秒の場合）として解析

```toDuration("P2DT3H4M") ```「2日3時間4分」と解釈する

```toDuration("P-6H3M") ``` 解析を「 —6時間+3分」として

```toDuration("-P6H3M")``` 解析を「 —6時間 —3分」として

```toDuration("-P-6H+3M") ``` 解析を「+6時間 —3分」として

## リスト {#list}

**説明**

区切り文字として角括弧を使用する式のコンマ区切りリスト。

ポリモーミズムはサポートされないので、リストに含まれるすべての式は同じタイプを持つ必要があります。

**リテラル表現**

```[<expression>, <expression>, ... ]```

**例**

```["value1","value2"]```

```[3,5]```

```[toDuration(500),toDuration(800)]```
