---
product: adobe campaign
title: 高度な式エディターの使用
description: 高度な式の作成方法を説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# 高度な式の例

高度な式エディターを使用して、ジャーニー内のユーザーをフィルターできる条件を作成できます。 これらの条件を使用すると、時間、日付、場所、期間、または買い物かごの購入や放棄などのアクションに基づいてユーザーをターゲット設定し、ジャーニーで再ターゲット化できます。

>[!NOTE]
>
>イベントは@で始まり、データソースは#で始まります。

## エクスペリエンスイベントの条件の作成

高度な式エディターは、購入のリストやメッセージに対する過去のクリックなどの時系列に対してクエリを実行する場合に必須です。 このようなクエリは、シンプルなエディターでは実行できません。

エクスペリエンスイベントは、時系列の逆順にコレクションとしてAdobe Experience Platformから取得されます。そのため、

* 最初の関数は、最新のイベントを返します
* 最後の関数は、最も古い関数を返します。

例えば、過去7日間に買い物かごが放棄され、顧客が店舗に近づいたときにメッセージを送信し、店舗にあるいは店舗にある必要のある品目に関するオファーを送信する顧客をターゲット設定するとします。

**次の条件を作成する必要があります。**

まず、オンラインストアを閲覧したが、過去7日間に注文を最終決定しなかった顧客をターゲットにします。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**この式は、過去7日間に指定されたこのユーザーのすべてのイベントを検索します。**

次に、completePurchaseに変換されなかったすべての追加買い物かごイベントを選択します。

>[!NOTE]
>
>式にフィールドをすばやく挿入するには、エディターの左側のパネルにあるフィールドをダブルクリックします。

指定したタイムスタンプは日時値として機能し、2つ目は日数です。

```
        In( “addToCart”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        And
        Not(In( “completePurchase”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
```

この式はブール値を返します。

**次に、製品が在庫していることを確認する式を作成します**

* 在庫で、この式は製品の数量フィールドを検索し、0より大きい値を指定します。

`#{Inventory.fieldgroup3.quantity} > 0`

* 右側で、必要な値を指定します。ここでは、イベント「ArriveLumaStudio」の場所からマッピングされたストアの場所を取得する必要があります。

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* また、関数`first`を使用してSKUを指定し、最新の「addToCart」インタラクションを取得します。

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

そこから、製品がストアにない場合のジャーニーに別のパスを追加し、エンゲージメントオファーを含む通知を送信できます。 それに応じてメッセージを設定し、パーソナライゼーションデータを使用してメッセージのターゲットを強化します。

## 高度な式エディターを使用した文字列操作の例

**条件内**

この条件は、「Arlington」でトリガーされたジオフェンスイベントのみを取得します。

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

説明：これは厳密な文字列比較（大文字と小文字を区別）で、`equal to`を使用し、`Is sensitive`をオンにするシンプルモードのクエリと同じです。

`Is sensitive`がオフの同じクエリでは、詳細設定モードで次の式が生成されます。

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**アクション内**

次の式を使用して、アクションのパーソナライゼーションフィールドでCRM IDを定義できます。

```
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         }
                         ))
```

説明：この例では、`substr`関数と`lastIndexOf`関数を使用して、モバイルアプリ起動イベントで渡されるCRM IDを囲む波括弧を削除します。

高度な式エディターの使用方法について詳しくは、[このビデオ](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)をご覧ください。
