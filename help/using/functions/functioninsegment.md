---
title: inSegment
description: inSegmentの関数について説明します。
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

---


# inSegment {#inSegment}

個人が特定のセグメントに属しているかどうかを確認します。

セグメント名は文字列定数である必要があります。 フィールド参照または式は使用できません。

セグメントは [Adobe Experience Platformで定義されます](https://platform.adobe.com/segment/overview)。 式エディターには、セグメントの自動完了リストが表示されます。

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

この関数は、ジャーニーイ **[!UICONTROL true]**ンスタンス内の個人が「men over 50」という名前のプラットフォームセグメントの一部である場合に返されます。それ以外の場合は返**[!UICONTROL false]** されます。
