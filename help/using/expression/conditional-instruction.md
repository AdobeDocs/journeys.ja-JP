---
product: adobe campaign
solution: Journey Orchestration
title: 条件付き命令(if、then、else)
description: 条件付き指示について説明します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%

---


# 条件付き命令(if, then, else) {#section_cdz_lsk_w3b}

アドバンスエディターでは、条件付き命令(if、then、else)がサポートされています。 これにより、より複雑な式を定義できます。 この要素は、次の要素で構成されます。

* **[!UICONTROL if]**:最初に評価される条件。
* **[!UICONTROL then]**:条件評価の結果がtrueの場合に評価される式。
* **[!UICONTROL else]**:条件評価の結果がfalseの場合に評価される式。

>[!NOTE]
>
>すべての式は括弧で囲む必要があります。

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` は **booleanを返す必要があります**。

`<expression2>` とは、同じ型または互換性のある型を持つ `<expression3>` 必要があります。サポートされている署名と返される型は次のとおりです。

```
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**使用状況**

条件付き命令を使用すると、条件アクティビティの数を減らしてジャーニーワークフローを最適化できます。 例えば、同じアクションアクティビティ内で、1つのフィールド定義に対して1つの条件式のみを使用する2つの代替オプションを指定できます。

アクションアクティビティの例（条件付き命令の結果として文字列が必要なフィールドの場合）:

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
