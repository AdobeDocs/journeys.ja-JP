---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: inSegment関数について説明します。
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 8%

---


# inSegment {#inSegment}

個々の人が特定のセグメントに属しているかどうかを確認します。

>[!NOTE]
>
>最大100個のセグメントを取得できます。

セグメント名は文字列定数である必要があります。 フィールド参照や式は使用できません。

セグメントは[Adobe Experience Platform](https://platform.adobe.com/segment/overview)で定義されます。 式エディターには、セグメントの自動入力リストが用意されています。

>[!NOTE]
>
>**実現**&#x200B;および&#x200B;**既存の**&#x200B;セグメントパーティシペーションのステータスの個人のみが、セグメントのメンバーと見なされます。 セグメントの評価方法について詳しくは、[Segmentation Serviceドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)を参照してください。

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

ジャーニーインスタンス内の個人が「men over 50」という名前のAdobe Experience Platformセグメントの一部である場合、**[!UICONTROL true]**&#x200B;を返します。それ以外の場合は、**[!UICONTROL false]**&#x200B;を返します。
