---
title: メッセージパラメーターの定義
description: メッセージパラメーターの定義方法を説明します
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# メッセージパラメーターの定義 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

このセクシ **[!UICONTROL Message parameters]**ョンに、外部サービスに送信するJSONペイロードの例を貼り付けます。


![](../assets/customactionpayloadmessage.png)

パラメータのタイプが正しいかどうかを定義できます(例：文字列、整数など)。

また、パラメーターが定数か変数かを指定することもできます。

* 「定数」は、パラメーターの値が、アクション設定ウィンドウで技術的な人物によって定義されることを意味します。 この値は、旅の間で常に同じになります。 この変数は変化せず、マーケティング担当者は、旅の中でカスタムアクションを使用する場合にこの値を見ることはできません。 例えば、サードパーティシステムが予期するIDを指定できます。 この場合、トグル定数/変数の右側のフィールドに渡された値が表示されます。
* 変数は、パラメーターの値が変化することを意味します。 このカスタムアクションを遍歴で使用するマーケターは、必要な値を渡したり、このパラメーターの値を取得する場所を自由に指定できます（例：イベントから、データプラットフォームから）。 この場合、トグル定数/変数の右側のフィールドは、このパラメーターに名前を付けるための遍歴でマーケターに表示されるラベルです。
