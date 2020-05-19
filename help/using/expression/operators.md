---
title: オペレーター
description: 高度な式の演算子について説明します。
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
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 5%

---



# オペレーター {#concept_wd5_pj5_dgb}

演算子には次の2種類があります。 単項演算子とバイナリ演算子。 左側の単項演算子と右側の単項演算子があります。

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

## 論理

<table>
<thead>
<tr ><th  >演算子</th><th  >リテラル式</th><th  >例</th></tr>
</thead>
<tbody>
<tr >&gt;<td>および</td><td><p><pre>&lt;式1&gt;と&lt;式2&gt;</pre></p>&lt;式1&gt;と&lt;式2&gt;の両方をブール値にする必要があります。 結果はbooleanです。</td><td><pre>3.14 &gt; 2および3.15 &lt; 1</pre></td></tr>
<tr ><td>または</td><td><p><pre>&lt;式1&gt;または&lt;式2&gt;</pre></p><p>&lt;式1&gt;と&lt;式2&gt;の両方をブール値にする必要があります。</p><p> 結果はbooleanです。</p></td><td><p><pre>3.14 &gt; 2または3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>not &lt;式&gt;</pre></p><p>&lt;式&gt;はブール値である必要があります。</p><p> 結果はbooleanです。</p></td><td><pre>not 3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## 比較

<table>
<thead>
<tr ><th  >演算子</th><th  >リテラル式 </th><th  >例</th></tr>
</thead>
<tbody><tr ><td>値がnull</td><td><p><pre>&lt;式&gt;がnullです</pre></p><p>結果はbooleanです。</p><p>nullは、式に評価された値がないことを意味します。</p></td><td><pre>@{BarBeacon.location}がnullです</pre></td></tr>
<tr ><td>nullでない</td><td><p><pre>&lt;式&gt;がnullでない</pre></p><p>結果はbooleanです。</p><p>nullは、式に評価された値がないことを意味します。</p></td><td><pre>@がnullでない</pre></td></tr>
<tr ><td>nullを含む</td><td><p><pre>&lt;式&gt;にNULLがあります</pre>&lt;式&gt;はリストでなければなりません。</p><p>結果はbooleanです。</p><p>リストに少なくとも1つのnull値が含まれていることを確認するのに役立ちます。</p></td><td><p><pre>["foo", "bar", null"]にnullが含まれています</pre></p>trueを返します<p><pre>["foo", "bar", ""]にnullがあります</pre></p> ""はnullとは見なされないので、falseを返します。</td></tr>
<tr ><td>==</td><td><p><pre>&lt;式1&gt; == &lt;式2&gt;</pre></p><p>&lt;式1&gt;と&lt;式2&gt;の両方が同じデータ型である必要があります。</p><p> 結果はbooleanです。</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;式1&gt; != &lt;式2&gt;</pre></p><p> &lt;式1&gt;と&lt;式2&gt;の両方が同じデータ型である必要があります。</p><p> 結果はbooleanです。</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;式1&gt; &gt; &lt;式2&gt;</pre></p><p>DatetimeはDatetimeと比較できます。</p><p>Datetimeonlyは、Datetimeonlyと比較できます。</p><p>整数と小数の両方を、整数と小数の両方と比較できます。</p><p>その他の組み合わせは禁止されています。</p><p>結果はbooleanです。</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;式1&gt; &gt;= &lt;式2&gt;</pre></p><p>DatetimeはDatetimeと比較できます。</p><p>Datetimeonlyは、Datetimeonlyと比較できます。</p><p>整数と小数の両方を、整数と小数の両方と比較できます。</p><p>その他の組み合わせは禁止されています。</p><p>結果はbooleanです。</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;式1&gt; &lt; &lt;式2&gt;</pre></p><p>DatetimeはDatetimeと比較できます。</p><p>Datetimeonlyは、Datetimeonlyと比較できます。</p><p>整数と小数の両方を、整数と小数の両方と比較できます。</p><p>その他の組み合わせは禁止されています。</p><p>結果はbooleanです。</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;式1&gt; &lt;= &lt;式2&gt;</pre></p><p>DatetimeはDatetimeと比較できます。</p><p>Datetimeonlyは、Datetimeonlyと比較できます。</p><p>整数と小数の両方を、整数と小数の両方と比較できます。</p><p>その他の組み合わせは禁止されています。</p><p>結果はbooleanです。</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## 演算

<table>
<thead>
<tr ><th  >演算子</th><th>リテラル式 </th><th  >例</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;式1&gt; + &lt;式2&gt;</pre></p><p>どちらの式も数値（整数または10進）である必要があります。 </p><p>結果も数値です。</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>戻り値3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;式1&gt; - &lt;式2&gt;</pre></p><p> どちらの式も数値（整数または10進）である必要があります。</p><p> 結果も数値です。</p></td><td><p><pre>2 - 1</pre></p>戻り値1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;式1&gt; / &lt;式2&gt;</pre></p><p>どちらの式も数値（整数または10進）である必要があります。 </p><p>結果も数値です。</p><p>&lt;式2&gt;は0に等しくない（0を返す）。</p></td><td><p><pre>4 / 2</pre></p>戻り値2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;式1&gt; * &lt;式2&gt;</pre></p><p> どちらの式も数値（整数または10進）である必要があります。 </p><p>結果も数値です。</p></td><td><p><pre>3 * 4</pre></p>戻り値12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;式1&gt; % &lt;式2&gt;</pre></p><p>どちらの式も数値（整数または10進）である必要があります。</p><p> 結果も数値です。</p></td><td><p><pre>3 % 2</pre></p>1を返します。</td></tr>
</tbody>
</table>

## 計算数学

<table>
<thead>
<tr ><th  >演算子</th><th  >リテラル式 </th><th  >例</th></tr>
</thead>
<tbody><tr ><td>数値</td><td><p><pre>&lt;式&gt;は数値です</pre></p><p>式のタイプは整数または10進です。</p></td><td><pre>@は数値</pre></td></tr>
<tr ><td>integer</td><td><p><pre>&lt;式&gt;は整数です</pre></p><p>式のタイプは整数です。</p></td><td><pre>@は整数</pre></td></tr>
<tr ><td>は小数</td><td><p><pre>&lt;式&gt;は10進数</pre></p><p>式のタイプは10進です。</p></td><td><pre>@は10進数</pre></td></tr>

## 文字列

<table>
<thead>
<tr ><th  >演算子</th><th  >リテラル式 </th><th  >例</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;string&gt; + &lt;式&gt;</pre></p><p><pre>&lt;式&gt; + &lt;文字列&gt;</pre></p><p>2つの式が連結されます。 </p><p>1つの式は、チェーン文字列である必要があります。</p></td><td><p><pre>"現在の時刻は" + (now())</pre></p> 「現在の時刻は2019-09-23T09:30:06.693Zです」を返します。<p><pre>(now()) + "は現在の時間です"</pre></p>"2019-09-23T09:30:06.693Z is the current time"を返します。<p><pre>"a" + "b" + "c" + 1234</pre></p> "abc1234"を返します。</td></tr>
</tbody>
</table>

## 日付

<table>
<thead>
<tr ><th  >演算子</th><th  >リテラル式 </th><th  >例</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;式+ &lt;期間&gt;</pre></p><p>dateTime、dateTimeOnlyまたはdurationに期間を追加します。</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>2011-12-03T15:30:30Zを返します。</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>2011-12-03T15:30:30を返します<p><pre>now() + toDuration("PT1H")</pre></p><p>現在の時刻から1時間後に（UTCタイムゾーンで）dateTimeを返します</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>PT2Hを返します</p></td></tr>
</tbody>
</table>