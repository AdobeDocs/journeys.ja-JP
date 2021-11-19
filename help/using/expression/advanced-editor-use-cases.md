---
product: adobe campaign
title: 高度な式エディターの使用
description: 高度な式の作成方法を説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 高度な式の例

高度な式エディターを使用して、ジャーニー内のユーザーをフィルターできる条件を作成できます。 これらの条件を使用すると、時間、日付、場所、期間または買い物かごの購入や放棄などのアクションに基づいてユーザーをターゲットに設定し、ジャーニーで再ターゲット化できます。

>[!NOTE]
>
>イベントは@で始まり、データソースは#で始まります。

## エクスペリエンスイベントの条件の作成

高度な式エディターは、購入のリストやメッセージに対する過去のクリックなどの時系列に対してクエリを実行する場合に必須です。 このようなクエリは、単純なエディターでは実行できません。

エクスペリエンスイベントは、時系列の逆順にAdobe Experience Platformからコレクションとして取得されます。そのため、次のようになります。

* 最初の関数は、最新のイベントを返します。
* 最後の関数は、最も古い関数を返します。

例えば、過去 7 日間に買い物かごが放棄され、顧客が店に近づいたときにメッセージを送信し、店舗にある必要のある品目に関するオファーを提供するとします。

**次の条件を作成する必要があります。**

まず、オンラインストアを閲覧したが、過去 7 日間に注文を確定しなかった顧客をターゲットにします。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**この式は、過去 7 日間に指定されたこのユーザーのすべてのイベントを検索します。**

次に、completePurchase に変換されなかったすべての addtocart イベントを選択します。

>[!NOTE]
>
>式にすばやくフィールドを挿入するには、エディターの左パネルにあるフィールドをダブルクリックします。

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

**次に、製品が在庫にあることを確認する式を作成します**

* Inventory で、この式は製品の数量フィールドを検索し、0 より大きい値を指定します。

`#{Inventory.fieldgroup3.quantity} > 0`

* 右側で、必要な値が指定されています。ここでは、イベント「ArriveLumaStudio」の場所からマッピングされている、ストアの場所を取得する必要があります。

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* また、関数を使用して SKU を指定します。 `first` 最新の「addToCart」インタラクションを取得するには：

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

製品がストアにない場合のジャーニーに別のパスを追加し、エンゲージメントオファーを含む通知を送信できます。 メッセージを適切に設定し、パーソナライゼーションデータを使用してメッセージのターゲットを強化します。

## 高度な式エディターを使用した文字列操作の例

**条件内**

この条件は、「Arlington」でトリガーされたジオフェンスイベントのみを取得します。

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

説明：これは厳密な文字列比較（大文字と小文字を区別）で、 `equal to` と `Is sensitive` オンにしました。

と同じクエリ `Is sensitive` オフにすると、詳細設定モードで次の式が生成されます。

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

説明：この例では、 `substr` および `lastIndexOf` モバイルアプリ起動イベントで渡される CRM ID を囲む中括弧を削除する関数。

高度な式エディターの使用方法について詳しくは、 [このビデオ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
