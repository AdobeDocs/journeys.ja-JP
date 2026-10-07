---
product: adobe campaign
title: 一般規則
description: 高度な式の一般規則について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%
---
# 一般規則 {#concept_rcy_qj5_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


## 括弧と式の優先度{#section_edf_fks_bgb}

括弧を使用すると、複雑な式が読みやすくなります。 _(&lt;expression>)_ は _&lt;expression>_&#x200B;と同等です。 括弧を使用して、評価順序と結合規則を定義することもできます。

式は左から右に評価されます。 演算子の結合規則を適用する必要があります。乗算と除算は、加算と減算よりも優先されます。 特定の順序を強制するには、括弧を追加して演算を区切る必要があります。 例：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 式 | 評価結果 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>「*」は「+」よりも優先されます：2 * 10 の評価結果は → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧によって優先度が変わります：(4 + 2) の評価結果は → 6</li><li> 6 * 10 → 60</li></ul> |

## 大文字と小文字の区別{#section_lrb_xh5_dgb}

大文字と小文字の区別に関する様々なルールを次に示します。

* すべての演算子（and、or など）は 小文字で書き込む必要があります。 例： _`<expression1>`and`<expression2>`_ は有効な式であるのに対して、_`<expression1>`AND`<expression2>`_ は有効な式ではありません。
* すべての関数名では大文字と小文字が区別されます。 例： _inSegment()_ は有効なのに対して、_INSEGMENT()_ 関数は有効ではありません。
* フィールド参照と定数値は、大文字と小文字が区別されます。（演算子や関数とは異なり）これらは言語のビルトインの要素ではなく、エンドユーザーが作成します。

## 式の戻り値のタイプ{#section_gyc_435_53b}

使用コンテキストに応じて、式エディターは異なる値を返す可能性があります。

| 高度な式エディターでの使用法 | 式の戻り値として想定されるタイプ |
|--- |--- |
| 条件（データソース条件、日付条件） | ブール値 |
| カスタムタイマー | dateTimeOnly |
| アクションパラメーターのマッピング | 任意 |
