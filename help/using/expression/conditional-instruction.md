---
title: 条件付き命令(if、then、else)
description: 条件付き命令の詳細
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 条件付き命令(if、then、else) {#section_cdz_lsk_w3b}

条件付き命令(if、then、else)は、アドバンスエディターでサポートされています。 これにより、より複雑な式を定義できます。 これは、次の要素で構成されます。

* **[!UICONTROL if]**:最初に評価される条件。
* **[!UICONTROL then]**:条件評価の結果がtrueの場合に評価される式です。
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

`<expression1>` はブール値を返す必要が **あります**。

`<expression2>` と同じタ `<expression3>` イプまたは互換性のあるタイプを持つ必要があります。 サポートされている署名と返される型は次のとおりです。

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

条件付き命令を使用すると、条件アクティビティの数を減らして、ジャーニーワークフローを最適化できます。 例えば、同じアクションアクティビティ内で、1つのフィールド定義に対して1つの条件式のみを使用して2つの代替オプションを指定できます。

アクションアクティビティの例（条件付き命令の結果として文字列が必要なフィールドの場合）:

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
