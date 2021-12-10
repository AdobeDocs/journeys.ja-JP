---
product: adobe campaign
title: フィールド参照
description: 高度な式でのフィールド参照について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: e4a003656058ac7ae6706e22fd5162c9e875629a
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 99%

---

# フィールド参照 {#concept_fkj_ll5_dgb}

フィールド参照は、イベントまたはフィールドグループに添付できます。 意味のある情報は、フィールドの名前とパスだけです。

フィールドに特殊文字を使用する場合は、二重または一重の引用符を使用する必要があります。次のような場合には引用符が必要です。

* フィールドが数字で始まる
* フィールドが「-」文字で始まる
* フィールドに _a_～_z_、_A_～_Z_、_0_～_9_、_、_-_ 以外の文字が含まれる

例えば、フィールドが _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_ の場合

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

式では、イベントフィールドは「@」で参照され、データソースフィールドは「#」で参照されます。

構文の色を使用して、イベントフィールド（緑）とフィールドグループ（青）を視覚的に区別します。

## フィールド参照のデフォルト値

デフォルト値をフィールド名に関連付けることができます。構文は以下のとおりです。

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>フィールドとデフォルト値のタイプは同じにする必要があります。例えば、@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} は無効になります。想定される値は文字列であるにもかかわらず、デフォルト値が整数であるからです。

例：

```json
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

## コレクション内のフィールドへの参照

コレクション内で定義された要素は、特定の関数 `all`、`first` および `last` を使用して参照します。詳しくは、[このページ](../expression/collection-management-functions.md)を参照してください。

例：

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## マップ内で定義されたフィールドへの参照

### `entry` 関数

マップ内の要素を取得するには、指定のキーで entry 関数を使用します。例えば、イベントのキーを定義する際に、選択した名前空間に応じて使用します。名前空間の選択を参照してください。 詳しくは、[このページ](../event/selecting-the-namespace.md)を参照してください。

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

この式では、イベントの「IdentityMap」フィールドの「Email」キーのエントリを取得しています。「Email」エントリはコレクションであり、ここから「first()」を使用して最初の要素の「id」を取得しています。詳しくは、[このページ](../expression/collection-management-functions.md)を参照してください。

### `firstEntryKey` 関数

マップの最初のエントリキーを取得するには、`firstEntryKey` 関数を使用します。

次の例では、特定のリストの購読者の最初のメールアドレスを取得する方法を示しています。

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

この例では、サブスクリプションリストの名前は `daily-email` です。メールアドレスは `subscribers` マップのキーとして定義され、サブスクリプションリストマップにリンクされています。

### `keys` 関数

マップのすべてのキーを取得するには、 `keys` 関数を使用します。

次の例では、特定のプロファイルについて、特定のリストの購読者に関連付けられているすべてのメールアドレスを取得する方法を示しています。

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## データソースのパラメーター値（データソースの動的な値）

パラメーターの呼び出しが必要な外部データソースからフィールドを選択すると、新しいタブが右側に表示され、そのパラメーターを指定できます。[このページ](../expression/expressionadvanced.md)を参照してください。

より複雑なユースケースの場合、データソースのパラメーターをメイン式に含めるには、_params_ キーワードを使用して、そのパラメーター値を定義できます。パラメーターは有効な式であれば、別のパラメーターも含む別のデータソースの式でも構いません。

>[!NOTE]
>
>式にパラメーター値を定義すると、右側のタブが消えます。

次の構文を使用します。

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**：データソースに存在する最初のパラメーターの正確な名前。
* **`<params-1-value>`**：最初のパラメーターの値。任意の有効な式を指定できます。

例：

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
