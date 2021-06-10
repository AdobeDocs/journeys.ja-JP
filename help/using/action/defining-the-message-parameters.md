---
product: adobe campaign
title: メッセージパラメーターの定義
description: メッセージパラメーターの定義方法を説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 1251eafcfe7487c3df01b412f17706f5ed6c6836
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# メッセージパラメーターの定義 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

「**[!UICONTROL メッセージパラメーター]**」セクションに、外部サービスに送信するJSONペイロードの例を貼り付けます。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>ペイロード内のフィールド名に「。」を含めることはできません。 文字。

パラメーターのタイプを定義できます(例：文字列、整数など)。

また、パラメーターが定数か変数かを指定することもできます。

* 定数は、パラメーターの値が技術的なペルソナによってアクション設定ペインで定義されることを意味します。 この値は、ジャーニー間で常に同じになります。 ジャーニーでカスタムアクションを使用する場合、変化はなく、マーケターには表示されません。 例えば、サードパーティシステムが想定するIDなどです。 その場合、切り替え定数/変数の右側にあるフィールドに渡された値が表示されます。
* 変数は、パラメーターの値が変わることを意味します。 このカスタムアクションをジャーニーで使用するマーケターは、目的の値を自由に渡したり、このパラメーターの値を取得する場所を指定したりできます(イベントから、Adobe Experience Platformからなど)。 この場合、切り替え定数/変数の右側のフィールドは、ジャーニーでマーケターがこのパラメーターに名前を付ける際に表示するラベルです。

![](../assets/customactionpayloadmessage2.png)
