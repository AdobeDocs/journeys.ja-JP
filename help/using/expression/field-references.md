---
title: フィールド参照
description: 高度な式でのフィールドリファレンスについて説明します。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 2%

---



# フィールド参照 {#concept_fkj_ll5_dgb}

フィールド参照は、イベントまたはフィールドグループに添付できます。 意味のある情報は、フィールドの名前とパスのみです。

フィールドに特殊文字を使用する場合は、重複引用符または単純な引用符を使用する必要があります。 引用符が必要な場合は次のようになります。

* 数字を含むフィールド開始
* 「 — 」文字を含むフィールド開始
* フィールドには次以外のものが含まれます。 __-z, A-_Z___, A _-Z______, nnn, n, n, n_

例えば、フィールドが _3hの場合_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

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

**コレクション内のフィールドの参照**

コレクション内で定義された要素は、最初と最後の特定の関数allを使用して参照されます。 For more information, see [](../expression/collection-management-functions.md).

例：

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**マップで定義されたフィールドの参照**

マップ内の要素を取得するには、指定したキーを持つエントリ関数を使用します。 例えば、選択した名前空間に従ってイベントのキーを定義する場合に使用します。 詳しくは、名前空間の選択を参照してください。 For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

この式では、イベントの「IdentityMap」フィールドの「Email」キーのエントリを取得します。 「Email」エントリはコレクションで、「first()」を使用して最初の要素の「id」を取得します。 For more information, see [](../expression/collection-management-functions.md).

**データソースのパラメーター値（データソースの動的値）**

パラメーターの呼び出しが必要な外部データソースからフィールドを選択すると、右側に新しいタブが表示され、このパラメーターを指定できます。 [](../expression/expressionadvanced.md) を参照してください。

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. パラメーターは、別の式ーも含む別のデータソースからのパラメーターでも、任意の有効な任意のパラメーターにできます。

>[!NOTE]
>
>式でパラメータ値を定義すると、右側のタブが消えます。

次の構文を使用します。

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:データソースの最初のパラメーターの正確な名前。
* **`<params-1-value>`**:最初のパラメーターの値。 任意の有効な式を指定できます。

例：

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
