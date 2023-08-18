---
product: adobe campaign
title: 高度な式エディターの使用
description: 高度な式の作成方法について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 100%

---

# 高度な式の例

高度な式エディターを使用すると、ジャーニーでユーザーをフィルタリングできる条件を作成できます。これらの条件を使用すると、時刻、日付、場所、期間またはアクション（買い物かごの購入や放棄など）に基づいてユーザーをターゲットに設定して、ジャーニーでユーザーを再ターゲット化できるようになります。

>[!NOTE]
>
>イベントは @ で始まり、データソースは # で始まります。

## エクスペリエンスイベントに関する条件の作成

高度な式エディターは、購入のリストやメッセージに対する過去のクリックなどの時系列に対してクエリを実行する場合に必須です。このようなクエリは、単純なエディターでは実行できません。

エクスペリエンスイベントは、Adobe Experience Platform からコレクションとして新しい順に取得されます。したがって、次のようになります。

* first 関数は最新のイベントを返します
* last 関数は最も古いイベントを返します

例えば、過去 7 日間に買い物かごを放棄した顧客をターゲットにして、顧客が店に近づいたときに、過去に顧客が希望した商品のうち店頭にあるものに関するオファーをメッセージで送信するとします。

**次の条件を作成する必要があります。**

まず、過去 7 日間にオンラインストアを閲覧したものの、最終的に注文をしていない顧客をターゲットにします。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**この式は、過去 7 日間に指定された、このユーザーのすべてのイベントを検索します。**

次に、completePurchase に転換されなかったすべての addtocart イベントを選択します。

>[!NOTE]
>
>式に手早くフィールドを挿入するには、エディターの左パネルにあるフィールドをダブルクリックします。

指定したタイムスタンプは日時の値として機能し、2 番目は日数です。

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

この式はブール値を返します。

**次に、商品の在庫があるかどうかを確認する式を作成します**

* Inventory で、この式は製品の数量フィールドを検索し、その値が 0 より大きいことを指定します。

`#{Inventory.fieldgroup3.quantity} > 0`

* 必要な値は適宜指定されます。ここでは、ストアの場所を取得する必要があります。これは、イベント「ArriveLumaStudio」の location からマッピングされています。

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* そして、SKU を指定し、`first` 関数を使用して、最新の「addToCart」インタラクションを取得します。

  ```json
      #{ExperiencePlatformDataSource
                      .ExperienceEventFieldGroup
                      .experienceevent
                      .first(
                      currentDataPackField
                      .productData
                      .productInteraction == "addToCart"
                      )
                      .SKU}
  ```

そこから、商品がストアにない場合のために別のパスをジャーニーに追加し、エンゲージメントオファーの通知を送信することができます。メッセージを適切に設定し、パーソナライゼーションデータを使用してメッセージのターゲットを強化します。

## 高度な式エディターを使用した文字列操作の例

**条件内**

次の条件は、「Arlington」でトリガーされたジオフェンスイベントのみを取得します。

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

説明：これは厳密な文字列比較（大文字と小文字を区別）で、`Is sensitive` をオンにして `equal to` を使用するシンプルモードのクエリと同等です。

同じクエリでも `Is sensitive` をオフにすると、詳細設定モードで次の式が生成されます。

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**アクション内**

次の式を使用すると、アクションパーソナライゼーションフィールドで CRM ID を定義できます。

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

説明：この例では、`substr` および `lastIndexOf` 関数を使用して、モバイルアプリ起動イベントで渡される CRM ID を囲む中括弧を削除しています。

高度な式エディターの使用方法について詳しくは、 [このビデオ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html?lang=ja)をご覧ください。
