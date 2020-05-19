---
title: inSegment
description: inSegment関数について説明します。
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 11%

---


# inSegment {#inSegment}

個々の人が特定のセグメントに属しているかどうかを確認します。

セグメント名は文字列定数である必要があります。 フィールド参照や式は使用できません。

セグメントは、 [Adobe Experience Platformで定義されます](https://platform.adobe.com/segment/overview)。 式エディターには、セグメントの自動入力リストが用意されています。

>[!NOTE]
>
>最大100個のセグメントを取得できます。

## カテゴリ

Adobe Experience Platform

## 関数の構文

`inSegment(<parameter>)`

## パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| セグメント | セグメント名 | `<string>` |

## 署名と戻り値の型

`inSegment(<string>)`

ブール値を返します。

## 例

`inSegment("men over 50")`

説明：

この関数は、ジャーニーインスタンス内の個人が「men over 50」という名前のプラットフォームセグメントの一部である場合は **[!UICONTROL true]** 、それ以外の場合は **[!UICONTROL falseを返します]** 。
