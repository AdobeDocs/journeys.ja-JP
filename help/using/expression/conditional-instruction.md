---
product: adobe campaign
title: 条件付き命令(if、then、else)
description: 条件付き命令の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 1%

---

# 条件付き命令(if、then、else) {#section_cdz_lsk_w3b}

条件付き命令(if、then、else)は、高度なエディターでサポートされます。 これにより、より複雑な式を定義できます。 これは、次の要素で構成されます。

* ****&#x200B;の場合：最初に評価する条件。
* **[!UICONTROL 次に、]**&#x200B;を示します。条件評価の結果がtrueの場合に評価される式。
* **[!UICONTROL else]**:条件評価の結果がfalseの場合に評価される式。

>[!NOTE]
>
>すべての式を囲むには括弧が必要です。

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` はブール値を返す **必要があります**。

`<expression2>` と `<expression3>` は、同じ型または互換性のある型を持つ必要があります。サポートされている署名と返される型は次のとおりです。

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

**用途**

条件付き命令を使用すると、条件アクティビティの数を減らして、ジャーニーワークフローを最適化できます。 例えば、同じアクションアクティビティ内で、1つの条件式のみを使用して、1つのフィールド定義に2つの代替オプションを指定できます。

アクションアクティビティの例（条件付き命令の結果として文字列が必要なフィールドの場合）:

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
