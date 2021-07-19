---
product: adobe campaign
title: フィールド参照
description: 高度な式のフィールド参照について説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 5%

---

# フィールド参照 {#concept_fkj_ll5_dgb}

フィールド参照は、イベントまたはフィールドグループに添付できます。 意味のある情報は、フィールドの名前とそのパスのみです。

フィールドに特殊文字を使用する場合は、二重引用符または単純引用符を使用する必要があります。 引用符が必要な場合は次のようになります。

* フィールドは数字で始まる
* フィールドは「 — 」文字で始まる
* フィールドには次以外の値が含まれます。_a_-_z_、_A_-_Z_、_0_-_9_、_、_-_

例えば、フィールドが&#x200B;_3h_&#x200B;の場合は、次のようになります。_#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

式では、イベントフィールドは「@」で参照され、データソースフィールドは「#」で参照されます。

構文の色は、イベントフィールド（緑）とフィールドグループ（青）を視覚的に区別するために使用します。

**フィールド参照のデフォルト値**

デフォルト値をフィールド名に関連付けることができます。  構文は以下のとおりです。

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>フィールドのタイプとデフォルト値は同じである必要があります。 例えば、@{LobbyBeacon.endUserIDsのようにします。_experience.emailid.id, defaultValue :デフォルト値は整数であるのに対して、期待値は文字列である必要があるので、2}は無効です。

例：

```
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

**コレクション内のフィールドの参照**

コレクション内で定義された要素は、特定の関数all （最初と最後）を使用して参照されます。 詳しくは、[このページ](../expression/collection-management-functions.md)を参照してください。

例 :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**マップで定義されたフィールドの参照**

マップ内の要素を取得するには、特定のキーでエントリ関数を使用します。 例えば、選択した名前空間に従ってイベントのキーを定義する際に使用されます。 名前空間の選択を参照してください。 詳しくは、[このページ](../event/selecting-the-namespace.md)を参照してください。

```
@{MyEvent.identityMap.entry('Email').first().id}
```

この式では、イベントの「IdentityMap」フィールドの「Email」キーのエントリを取得しています。 「Email」エントリはコレクションで、最初の要素で「first()」を使用して「id」を取得します。 詳しくは、[このページ](../expression/collection-management-functions.md)を参照してください。

**データソースのパラメーター値（データソースの動的値）**

パラメーターの呼び出しが必要な外部データソースからフィールドを選択すると、右側に新しいタブが表示され、このパラメーターを指定できます。 [このページ](../expression/expressionadvanced.md)を参照してください。

より複雑な使用例では、データソースのパラメーターをメイン式に含める場合、キーワード&#x200B;_params_&#x200B;を使用して値を定義できます。 パラメーターは、別のパラメーターも含む別のデータソースからの有効な式でもかまいません。

>[!NOTE]
>
>式にパラメータ値を定義すると、右側のタブが消えます。

次の構文を使用します。

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:データソースの最初のパラメーターの正確な名前。
* **`<params-1-value>`**:最初のパラメーターの値。任意の有効な式を指定できます。

例：

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
