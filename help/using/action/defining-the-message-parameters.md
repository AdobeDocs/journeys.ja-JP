---
title: メッセージパラメーターの定義
description: メッセージパラメーターの定義方法を学びます
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 3%

---


# メッセージパラメーターの定義 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

「 **[!UICONTROL Message parameters]** 」セクションに、外部サービスに送信するJSONペイロードの例を貼り付けます。


![](../assets/customactionpayloadmessage.png)

パラメーターのタイプが正しいかどうかを定義できます(例： 文字列、整数など)。

また、パラメーターが定数か変数かを指定することもできます。

* 「定数」は、パラメーターの値が、アクション設定ウィンドウで技術的な人物によって定義されることを意味します。 この値は、常にジャーニー全体で同じになります。 この変数は変化せず、マーケティング担当者が遍歴でカスタムアクションを使用する場合には表示されません。 例えば、サードパーティのシステムが予期するIDを指定できます。 この場合、トグル定数/変数の右側にあるフィールドが渡される値です。
* 変数は、パラメーターの値が変化することを意味します。 このカスタムアクションを遍歴で使用するマーケターは、自由に値を渡したり、このパラメーターの値を取得する場所(イベント、Adobe Experience Platformなど)を指定したりできます。 この場合、トグル定数/変数の右側にあるフィールドが、このパラメーターの名前を付ける遍歴でマーケターに表示されるラベルです。
