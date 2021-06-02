---
product: adobe campaign
title: substr
description: 関数substrの詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 16%

---

# substr {#substr}

beginインデックスとendインデックスの間の文字列式のサブ文字列を返します。 終了インデックスが定義されていない場合、開始インデックスと終了インデックスの間にあります。

## カテゴリ

 バイト長文字列

## 関数の構文

`substr(<parameters>)`

## パラメーター

| パラメーター | type |
|-------------|----------|
| 文字列 | 文字列 |
| beginIndex | 整数 |
| endIndex | 整数 |

## 署名と戻り値の型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

文字列を返します。

## 例

`substr("Hello World",6)`

「World」を返します。

`substr("Hello World", 0, 5)`

「Hello」を返します。
