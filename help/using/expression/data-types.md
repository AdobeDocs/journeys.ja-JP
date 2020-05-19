---
title: データタイプ
description: 高度な式でのデータタイプについて説明します。
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
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 4%

---


# データタイプ {#concept_gp3_rj5_dgb}

技術的には、定数には常にデータ型が含まれます。 リテラル式では、値のみを指定します。 このデータ型は、値（文字列、整数、小数など）から推論できます。 日付時間などの特定のケースでは、表現に専用の関数を使用します。

次に、データタイプの式を示します。

<table>
    <thead>
        <tr>
        <td>データタイプ</td>
        <td>説明</td>
        <td>リテラル表現</td>
        <td>例</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>文字列</td>
        <td><p>一般的な文字のシーケンス。</p><p>メモリの空き容量など、環境から暗黙的に取得されるサイズを除き、特定のサイズはありません。</p><p>JSON形式： 文字列</p><p>シリアル化形式： UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>-2^63 ～ 2^63-1の整数値。</p><p>JSON形式： 数値</p></td>
        <td>&lt;整数値&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>10 進数.</p><p>これは、次の浮動値を表します。</p>
        <p>-重複型の最大正の有限値(2-2^-52)x2^1023</p>
        <p>  — タイプ重複の最小正の正の正規値、2-1022</p>
        <p>  — タイプ重複の最小のゼロ以外の正の値、p-1074</p><p>JSON形式： 数値</p><p>シリアル化形式： '.'を使用 を小数点の区切り文字として使用します。</p></td>
        <td>&lt;整数値&gt;&lt;整数値&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>小文字で書かれたブール値： trueまたはfalse</p><p>JSON形式： ブール値</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>タイムゾーンのない日付時刻を表し、年 — 月 — 日 — 時 — 分 — 秒 — ミリ秒で表示されます。</p><p>タイムゾーンは格納または表しません。</p><p>その代わりに、誕生日に使用される日付の説明と、壁掛けの時計に表示される現地時間が組み合わされます。</p><p>オフセットやタイムゾーンなどの追加情報がない場合は、タイムライン上の瞬間を表すことはできません。</p><p>シリアル化形式： ISO-8601拡張オフセット日時形式。</p><p>DateTimeFormatterを使用します。</p><p>ISO_LOCAL_DATE_TIMEを使用して、値のデシリアライズとシリアル化を行います。</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">詳細情報</a></td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly in ISO-8601 format&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>タイムゾーンも考慮する日時定数。</p><p>UTCからのオフセットを持つ日時を表します。 オフセットの追加情報を使用して、瞬時に表示できます。 </p><p>これは、世界のある場所で特定の「瞬間」を表す方法です。</p><p>JSON形式： 文字列。</p><p> toDateTime関数にカプセル化する必要があります。</p><p>
        シリアル化形式： ISO-8601拡張オフセット日時形式。</p><p> 値の逆シリアライズとシリアライズには、DateTimeFormatter.ISO_OFFSET_DATE_TIMEを使用します。</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">詳細情報</a> 
        <p>また、エポック値を渡す整数を渡すこともできます。</p> <a href="https://www.epochconverter.com/">詳細を表示</a>。</p>
        <p>タイムゾーンは、オフセットまたはタイムゾーンコードで指定できます(例： Europe/Paris、Z - UTC)。</p></td>
        <td><p>toDateTime("&lt;dateTime in ISO-8601 format&gt;")</p>
        <p>toDateTime(&lt;エポックの整数値（ミリ秒）)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duration</td>
        <td><p>これは、「34.5秒」など、時間に基づく時間を表します。</p><p> ミリ秒単位で数量または時間をモデル化します。</p><p>サポートされる時間単位は次のとおりです。 ミリ秒、秒、分、時間、日。日は24時間に等しくなります。</p><p> 年と月は一定の期間ではないので、サポートされません。</p><p>JSON形式： 文字列。 toDuration関数にカプセル化する必要があります。</p><p>シリアル化形式： タイムゾーンIDのシリアル化を解除するには、java関数java.timeを使用します。</p><p>Duration.parse: 指定できる形式は、ISO-8601 duration形式PnDTnHnMn.nSに基づいており、日数はちょうど24時間と見なされます。</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">詳細情報</a></td>
        <td><p>toDuration("&lt;duration in ISO-8601 format&gt;")</p><p>toDuration(&lt;duration in milliseconds&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5秒</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre> — 解析は「20.345秒」</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre>  — 解析は「15分」</pre></p>
        <p><pre>（1分は60秒）</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre> — 解析は「10時間」と呼ばれます。</pre></p>
        <p><pre>（時間は3600秒）</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— parses as "2 days"</pre></p>
        <p><pre>(日が </pre></p>
        <p><pre>24時間または86400秒)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre> — パースは</pre></p>
        <p><pre>"2日3時間4分"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre> — パースは</pre></p>
        <p><pre>"-6時間+3分"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre> — パースは</pre></p>
        <p><pre>"-6時間 —3分"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre> — パースは</pre></p>
        <p><pre>"+6時間 —3分"</pre></p></td>
    </tr>
    <tr>
        <td>リスト</td>
        <td>区切り文字として角括弧を使用する式のコンマ区切りリスト。 ポリモーミズムはサポートされないので、リストに含まれるすべての式は同じタイプを持つ必要があります。</td>
        <td>[&lt;式&gt;, &lt;式&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
