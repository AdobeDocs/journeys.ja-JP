---
product: adobe campaign
solution: Journey Orchestration
title: 一般法則規則
description: 高度な式の一般性について説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 4%

---

# 一般法則規則 {#concept_rcy_qj5_dgb}

## 括弧と式の優先度{#section_edf_fks_bgb}

丸括弧は、複雑な式をより読みやすくするために使用できます。 _(&lt;expression>)_ は、と等価で _&lt;expression>_&#x200B;す。また、評価の順序と関連付けを定義する際にも括弧を使用できます。

式は左から右に評価されます。 演算子の関連付けを適用する必要があります。乗法や区分は、加算や減算よりも優先されます。 特定の順序を強制するには、演算を区切る括弧を追加する必要があります。 例：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 式 | 評価 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;は&#39;+&#39;より優先されます。2 * 10が評価され→ 20</li><li>4 + 20 = 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧によって優先度が変わります。(4 + 2)を評価→ 6</li><li> 6 * 10 = 60</li></ul> |

## 大文字と小文字の区別{#section_lrb_xh5_dgb}

大文字と小文字の区別に関する様々なルールを次に示します。

* すべての演算子（および、またはなど） は小文字に書き込む必要があります。 例えば、_`<expression1>`と`<expression2>`_&#x200B;は有効な式ですが、_`<expression1>`と`<expression2>`_&#x200B;は有効な式ではありません。
* すべての関数名では大文字と小文字が区別されます。 例えば、_inSegment()_&#x200B;は有効ですが、_INSEGMENT()_&#x200B;は無効です。
* フィールド参照と定数値では大文字と小文字が区別されます。演算子や関数とは異なり、言語の組み込み要素ではなく、エンドユーザーが作成します。

## 返された式タイプ{#section_gyc_435_53b}

使用状況に応じて、式エディターから返される値が異なる場合があります。

| 高度な式エディターの使用 | 返される式の種類が必要です |
|--- |--- |
| 条件（データソース条件、日付条件） | boolean |
| カスタムタイマー | dateTimeOnly |
| Actionパラメーターのマッピング | 任意 |
