---
title: ルールベースのイベント
description: ルールベースのイベントについての詳細。
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
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 8%

---


# ルールベースのイベント{#simplified-events}

エクスペリエンスイベントの設定方法が簡略化されました。 eventIDを使用する必要のない新しいメソッドを導入します。 Journey Orchestrationでイベントを設定する際に、ルールベースのイベントを定義できるようになりました。

この新しいタイプのイベントでは、eventIDが生成されません。 シンプルな式エディターを使用して、システムがジャーニーをトリガーする関連イベントを特定するために使用するルールを定義するだけです。 このルールは、イベントペイロードで使用可能な任意のフィールドに基づくことができます。例えば、プロファイルの場所や、プロファイルの買い物かごに追加された項目数などです。

この新しいメソッドは、ほとんどの場合、ユーザーに対して透明です。 唯一の変更は、イベント定義画面の新しいフィールドです。

1. 左側のメニューで、「 **管理者** 」アイコンをクリックし、「 **イベント**」をクリックします。 イベントのリストが表示されます。

   ![](../assets/alpha-event1.png)

1. 新しいイベントを作成するには、「**追加**」をクリックします。画面の右側にイベント設定ペインが開きます。

   ![](../assets/alpha-event2.png)

1. イベントの名前を入力します。 説明を追加することもできます。

   ![](../assets/alpha-event3.png)

1. 新しい **イベントID type** ( **IDタイプ**)フィールドで、「ルールに基づく」を選択します。

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >「 **System Generated** 」タイプは、eventIDを必要とする既存のメソッドです。 [この節](../event/about-events.md)を参照してください。

1. **スキーマ** とペイロードの **フィールドを定義します**。 [この節](../event/defining-the-payload-fields.md)を参照してください。

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >「 **システム生成タイプ**」を選択した場合は、eventIDタイプがmixinのスキーマのみを使用できます。 「 **ルールベース** 」タイプを選択した場合は、エクスペリエンスイベントスキーマをすべて使用できます。

1. 「 **イベントID条件** 」フィールド内をクリックします。 シンプルな式エディターを使用して、遍歴のトリガーとなるイベントを特定するためにシステムで使用される条件を定義します。

   ![](../assets/alpha-event6.png)

   この例では、プロファイルの都市に基づいて条件を作成しました。 つまり、この条件に一致するイベント(**City** フィールドと **Paris** 値)を受け取るたびに、その情報がJourney Orchestrationに渡されます。

1. **名前空間** と ****&#x200B;キーを定義します。 「名前空間 [の選択](../event/selecting-the-namespace.md) 」および「イベントキーの [定義」を参照してください](../event/defining-the-event-key.md)。

   ![](../assets/alpha-event7.png)

イベントの設定と遍歴の作成に関するその他の手順は変更されません。

これでイベントが設定され、他のイベントと同様に遍歴に含まれる準備が整いました。 ルールに一致するイベントがシステムに送信されるたびに、そのイベントがJourney Orchestrationに渡され、ジャーニーがトリガーされます。

