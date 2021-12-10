---
product: adobe campaign
title: 条件命令（if、then、else）
description: 条件命令について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 100%

---

# 条件命令（if、then、else） {#section_cdz_lsk_w3b}

高度なエディターでは、条件命令（if、then、else）をサポートしています。これにより、より複雑な式を定義できます。条件命令は、次の要素で構成されています。

* **[!UICONTROL if]**：最初に評価される条件。
* **[!UICONTROL then]**：条件評価の結果が true の場合に評価される式。
* **[!UICONTROL else]**：条件評価の結果が false の場合に評価される式。

>[!NOTE]
>
>すべての式は括弧で囲む必要があります。

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` は&#x200B;**ブール値**&#x200B;を返す必要があります。

`<expression2>` と `<expression3>` は、同じタイプまたは互換性のあるタイプを持つ必要があります。サポートされているシグネチャと戻り値のタイプは次のとおりです。

```json
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
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**用途**

条件命令を使用すると、条件アクティビティの数を減らして、ジャーニーワークフローを最適化できます。例えば、同じアクションアクティビティ内で、1 つの条件式のみを使用して、1 つのフィールド定義に 2 つの代替オプションを指定できます。

アクションアクティビティの例（条件命令の結果として文字列を想定するフィールドの場合）：

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
