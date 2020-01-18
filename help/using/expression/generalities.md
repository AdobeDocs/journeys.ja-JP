---
title: 一般論
description: 高度な式の一般性について説明します。
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


# 一般論 {#concept_rcy_qj5_dgb}

## 括弧と式の優先順位{#section_edf_fks_bgb}

丸括弧は、複雑な式をより読みやすくするために使用できます。 _(&lt;expression>)は_ 、&lt;expression>と同 _等です_。 また、評価の順序と関連付けを定義するために括弧を使用することもできます。

式は左から右に評価されます。 演算子のアソシエティビティを適用する必要があります。乗算や区分は、加算や減算よりも優先されます。 特定の順序を設定するには、演算を区切る括弧を追加する必要があります。 次に例を示します。

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 式 | 評価 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;は&#39;+&#39;より優先されます。2 * 10が評価され→ 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧によって優先順位が変わります。(4 + 2)が評価され→ 6</li><li> 6 * 10 → 60</li></ul> |

## 大文字と小文字の区別{#section_lrb_xh5_dgb}

大文字と小文字の区別の異なるルールを次に示します。

* すべての演算子（および、またはなど）は小文字にする必要があります。 例えば、とは _`<expression1>`有効な式`<expression2>`_ですが、式_`<expression1>` ANDは無 `<expression2>`_ 効です。
* すべての関数名では大文字と小文字が区別されます。 例えば、 _getBestSendTime()は有効ですが_ 、関数 _GETBESTSENDTIME()は無効です_ 。
* フィールド参照と定数値では大文字と小文字が区別されます。演算子や関数とは異なり、言語の組み込み要素ではなく、エンドユーザーが作成します。

## 返される式の型{#section_gyc_435_53b}

使用状況に応じて、式エディターは異なる値を返すことがあります。

| 高度な式エディターの使用 | 戻り値の式の型が必要です |
|--- |--- |
| 条件（データソース条件、日付条件） | boolean |
| カスタムタイマー | dateTimeOnly |
| カスタムタイムゾーン | timeZoneまたは文字列（例：ヨーロッパ/パリ） |
| アクションパラメーターのマッピング | 任意 |
