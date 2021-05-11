---
product: adobe campaign
solution: Journey Orchestration
title: indexOf
description: 関数indexOfについて説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 7617bb25-ec4c-498f-947a-66bbdecd1069
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 19%

---

# indexOf {#indexOf}

最初の引数文字列が特定の文字列（2番目の引数文字列）で終わるかどうかをチェックします。 文字列が見つからない場合は、-1を返します。

## カテゴリ

 バイト長文字列

## 関数の構文

`indexOf(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 |  バイト長文字列 |
| 指定値 |  バイト長文字列 |

## 署名と戻り値の型

`indexOf(<string>,<string>)`

整数を返します。

## 例

`indexOf("Hello", "l")`

2を返します。

説明：

「Hello」で、「l」の最初の値は位置2にあります。
