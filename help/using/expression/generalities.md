---
title: 一般法則規則
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
source-git-commit: 1ccf020a882c1d6d9bd00f2e9f5d6b2aee6f7829
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# 一般法則規則 {#concept_rcy_qj5_dgb}

## 丸括弧と式の優先度{#section_edf_fks_bgb}

丸括弧は、複雑な式をより読みやすくするために使用できます。 _(&lt;式>)_ は、 _&lt;式>と同じです_。 また、評価の順序と関連付けを定義する際にも括弧を使用できます。

式は左から右に評価されます。 演算子の関連付けを適用する必要があります。 乗法や区分は、加算や減算よりも優先されます。 特定の順序を強制するには、演算を区切る括弧を追加する必要があります。 次に例を示します。

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 式 | 評価 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;は&#39;+&#39;より優先されます。 2 * 10が評価され→ 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧によって優先度が変わります。 (4 + 2)を評価→ 6</li><li> 6 * 10 → 60</li></ul> |

## 大文字と小文字の区別{#section_lrb_xh5_dgb}

大文字と小文字の区別に関する様々なルールを次に示します。

* すべての演算子（および、またはなど） は小文字に書き込む必要があります。 例えば、 _`<expression1>`とは有効な式`<expression2>`_ですが、式_`<expression1>` ANDは無効 `<expression2>`_ です。
* すべての関数名では大文字と小文字が区別されます。 例えば、 _getBestSendTime()は有効ですが_ 、関数 __ GETBESTSENDTIME()は無効です。
* フィールド参照と定数値では大文字と小文字が区別されます。 演算子や関数とは異なり、言語の組み込み要素ではなく、エンドユーザーが作成します。

## 返される式の種類{#section_gyc_435_53b}

使用状況に応じて、式エディターから返される値が異なる場合があります。

| 高度な式エディターの使用 | 返される式の種類が必要です |
|--- |--- |
| 条件（データソース条件、日付条件） | boolean |
| カスタムタイマー | dateTimeOnly |
| Actionパラメーターのマッピング | 任意 |
