---
product: adobe campaign
title: inSegment
description: inSegment 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 18%

---

# inSegment {#inSegment}

個人が特定のセグメントに属しているかどうかを確認します。

>[!NOTE]
>
>最大 100 個のセグメントを取得できます。

セグメント名は、文字列定数である必要があります。 フィールド参照や式は使用できません。

セグメントは [Adobe Experience Platform](https://platform.adobe.com/segment/overview). 式エディターには、自動入力されたセグメントのリストが表示されます。

セグメントには次の 3 つのステータスがあります。

* 既存：エンティティが引き続きセグメント内に存在します。
* 実現：エンティティがセグメントに入っています。
* 終了：エンティティがセグメントから退出しています。

個人のみ **実現済み** および **既存** セグメントパーティシペーションのステータスは、セグメントのメンバーと見なされます。 セグメントの評価方法について詳しくは、[Segmentation Service ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

`IF inSegment('segmentName') == true` は、「 segmentMembership 」が「入力済み」または「既存」のステータスになっていることを意味します。

`ELSE inSegment('segmentName') == false` は、「終了」ステータスの segmentMembership があることを意味します。

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

説明:

関数はを返します。 **[!UICONTROL true]** ジャーニーインスタンス内の個人が「men over 50」という名前のAdobe Experience Platformセグメントに属している場合、 **[!UICONTROL false]** それ以外の場合は
