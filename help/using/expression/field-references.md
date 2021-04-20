---
product: adobe campaign
solution: Journey Orchestration
title: フィールド参照
description: 高度な式でのフィールドリファレンスについて説明します。
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 5%

---



# フィールド参照 {#concept_fkj_ll5_dgb}

フィールド参照は、イベントまたはフィールドグループに添付できます。 意味のある情報は、フィールドの名前とパスのみです。

フィールドに特殊文字を使用する場合は、重複引用符または単純な引用符を使用する必要があります。 引用符が必要な場合は次のようになります。

* 数字を含むフィールド開始
* 「 — 」文字を含むフィールド開始
* フィールドには次以外のものが含まれます。_a_-_z_, _A_-_Z_, _0_-_, _ ,_-__

例えば、フィールドが&#x200B;_3h_&#x200B;の場合：_#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

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

デフォルト値は、フィールド名に関連付けることができます。 構文は以下のようになります。

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
>フィールドの種類とデフォルト値は同じである必要があります。 例えば、@{LobbyBeacon.endUserIDsのように指定します。_experience.emailid.id, defaultValue :2}は、デフォルト値は整数ですが、期待値は文字列である必要があるので無効です。

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

コレクション内で定義された要素は、最初と最後の特定の関数allを使用して参照されます。 詳しくは、[このページ](../expression/collection-management-functions.md)を参照してください。

例 :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**マップで定義されたフィールドの参照**

マップ内の要素を取得するには、指定したキーを持つエントリ関数を使用します。 例えば、選択した名前空間に従ってイベントのキーを定義する場合に使用します。 詳しくは、名前空間の選択を参照してください。 詳しくは、[このページ](../event/selecting-the-namespace.md)を参照してください。

```
@{MyEvent.identityMap.entry('Email').first().id}
```

この式では、イベントの「IdentityMap」フィールドの「Email」キーのエントリを取得します。 「Email」エントリはコレクションで、「first()」を使用して最初の要素の「id」を取得します。 詳しくは、[このページ](../expression/collection-management-functions.md)を参照してください。

**データソースのパラメーター値（データソースの動的値）**

パラメーターの呼び出しが必要な外部データソースからフィールドを選択すると、右側に新しいタブが表示され、このパラメーターを指定できます。 [このページ](../expression/expressionadvanced.md)を参照してください。

より複雑な使用例では、データソースのパラメーターをメイン式ーに含める場合、キーワード&#x200B;_params_&#x200B;を使用して値を定義できます。 パラメーターは、別の式ーも含む別のデータソースからのパラメーターでも、任意の有効な任意のパラメーターにできます。

>[!NOTE]
>
>式でパラメータ値を定義すると、右側のタブが消えます。

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
