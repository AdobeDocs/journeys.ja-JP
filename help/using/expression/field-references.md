---
title: フィールド参照
description: 高度な式のフィールド参照について説明します。
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
source-git-commit: 8be9cd1803ab2f7093934424c36fcd7407a4a20a

---



# フィールド参照 {#concept_fkj_ll5_dgb}

フィールド参照は、イベントまたはフィールドグループに添付できます。 意味のある情報は、フィールドの名前とパスだけです。

フィールドに特殊文字を使用する場合は、二重引用符または単純引用符を使用する必要があります。 見積もりが必要な場合は次のようになります。

* フィールドは数字で始まる
* フィールドは「 — 」文字で始まります
* フィールドに次以外の要素が含まれています。 _z, A_, A __- _Z_-_0_, _____0 , 9 , 9 , , , , , , , , ,_

例えば、フィールドが _3hの場合_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

この式では、イベントフィールドは「@」で参照され、データソースフィールドは「#」で参照されます。

構文の色は、イベントフィールド（緑）とフィールドグループ（青）を視覚的に区別するために使用します。

**フィールド参照のデフォルト値**

デフォルト値をフィールド名に関連付けることができます。 構文は以下のようになります。


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
>フィールドのタイプとデフォルト値は同じである必要があります。 例えば、@{LobbyBeacon.endUserIDsとします。_experience.emailid.id, defaultValue :デフォルト値は整数で、期待値は文字列である必要があるのに対し、2}は無効です。

**コレクション内のフィールドの参照**

コレクション内で定義された要素は、最初と最後の特定の関数を使用して参照されます。 For more information, see [](../expression/collection-management-functions.md).

例：

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**mapで定義されたフィールドの参照** map内の要素を取得するには、指定したキーを持つエントリ関数を使用します。 例えば、選択した名前空間に従ってイベントのキーを定義する場合に使用されます。 名前空間の選択を参照してください。 For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

この式では、イベントの「IdentityMap」フィールドの「Email」キーのエントリを取得します。 「電子メール」エントリはコレクションで、「first()」を使用して最初の要素の「id」を取得します。 For more information, see [](../expression/collection-management-functions.md).

**データソースのパラメーター値（データソースの動的値）**

パラメーターの呼び出しを必要とする外部データソースからフィールドを選択すると、右側に新しいタブが表示され、このパラメーターを指定できます。 [](../expression/expressionadvanced.md)を参照してください。

より複雑な使用例では、メインの式にデータソースのパラメーターを含める場合、キーワード _paramsを使用してその値を定義できます_。 パラメーターは、別のパラメーターも含む別のデータソースの任意の有効な式にすることができます。

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
