---
product: adobe campaign
title: startWithIgnoreCase
description: startWithIgnoreCase 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# startWithIgnoreCase {#startWithIgnoreCase}

大文字と小文字を区別しない場合に 2 番目のパラメーターが最初のパラメーターの接頭辞としてある場合は、true を返します。

## カテゴリ

文字列

## 関数の構文

`startWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| 接頭辞 | 文字列 |

## シグネチャと戻り値のタイプ

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`startWithIgnoreCase("rowing is great", "RO")`

true を返します。
