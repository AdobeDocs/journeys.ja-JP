---
title: 条件の追加
description: 条件の追加方法
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
source-git-commit: 5df2fecc56d2d2d081d952f17aadf103f2f0140a

---



# 条件の追加 {#concept_rbg_gqt_52b}

イベント条件を使用すると、システムでイベントの処理をフィルタリングできます。 条件がtrueの場合、イベントが処理されます。 条件がtrueでない場合、イベントは無視されます。

イベントの条件は、イベントペイロードで渡されたデータに基づいてのみ指定できます。 イベントレベルで定義された条件は、マーケティング担当者がキャンバス内で変更することはできません。 このイベントを使用する際に、この条件を強化することが目的です。 例えば、買い物かごの値が小さすぎる場合に買い物かごの放棄イベントをマーケターが使用しないようにするには、「買い物かごの値」イベントフィールドに条件を作成し、100ドルを超える値を課します。

イベントの条件を設定するには、簡易式エディターまたは高度な式エディターを使用します。 [](../expression/expressionadvanced.md)を参照してください。

例えば、特定のイベントタイプのイベントのみを処理し、他のタイプは無視する条件を定義できます。 または、イベントが買い物かごの放棄で、ペイロードに買い物かごの値フィールドが含まれる場合、買い物かごの値が100ドルを超える場合にのみイベントを処理するイベント条件を定義できます。

![](../assets/journey78.png)
