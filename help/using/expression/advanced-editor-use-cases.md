---
product: adobe campaign
solution: Journey Orchestration
title: 高度な式エディターの使用
description: 高度な式の作成方法を説明します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 2%

---


# 高度な式の例

アドバンス式エディターを使用して、ジャーニー内のユーザーをフィルターするための条件を作成できます。 これらの条件を使用すると、ジャーニー内で再ターゲティングできるように、ユーザーを時間、日付、場所、期間、または買い物かごの購入や放棄などのアクションにターゲットできます。

>[!NOTE]
>
>@を含むイベント開始、#を含むデータソース。

## エクスペリエンスイベントに基づく条件の作成

アドバンス式エディターは、購入のリストやメッセージに対する過去のクリック数などの時系列のクエリを実行する場合に必須です。 このようなクエリは、単純なエディターを使用して実行することはできません。

エクスペリエンスイベントは、暦の逆順にコレクションとしてAdobe Experience Platformから取得されます。したがって、次のようになります。

* 最初の関数は、最新のイベントを返します
* 最後の関数は最も古い関数を返します。

例えば、顧客が過去7日間に買い物かごを放棄したことをターゲットし、顧客が店舗に近づくときにメッセージを送信し、希望する品目をオファーして店舗に入れたいとします。

**次の条件を作成する必要があります。**

まず、オンラインストアを閲覧したが、過去7日間に注文を完了しなかったターゲットのお客様。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**この式は、過去7日間に指定された、このユーザーのすべてのイベントを探します。**

次に、completePurchaseに変換されなかったすべてのaddtocartイベントを選択します。

>[!NOTE]
>
>式にフィールドをすばやく挿入するには、エディターの左パネルにあるフィールドを重複クリックします。

指定したタイムスタンプが日付時間の値として機能し、2番目のタイムスタンプは日数です。

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

**次に、製品が在庫しているかどうかを確認する式を作成します**

* 在庫で、この式は製品の数量フィールドを探し、0より大きい値を指定します。

`#{Inventory.fieldgroup3.quantity} > 0`

* 右側に、必要な値が指定されています。ここでは、イベント「ArriveLumaStudio」の場所からマッピングされたストアの場所を取得する必要があります。

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* また、関数`first`を使用して、最新の「addToCart」インタラクションを取得し、SKUを指定します。

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

製品がストアにない場合の別のパスをジャーニーに追加し、エンゲージメントオファーと共に通知を送信できます。 それに応じてメッセージを設定し、パーソナライズデータを使用してメッセージのターゲットを強化します。

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

説明：これは厳密な文字列比較（大文字と小文字が区別されます）で、`Is sensitive`がチェックされた`equal to`を使用するシンプルモードのクエリと同じです。

`Is sensitive`がオフになっている同じクエリは、アドバンスモードで次の式を生成します。

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**アクション内**

次の式では、アクションのパーソナライゼーションフィールドでCRM IDを定義できます。

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

説明：この例では、`substr`関数と`lastIndexOf`関数を使用して、モバイルアプリの起動イベントで渡されるCRM IDを囲む波括弧を削除します。

アドバンス式エディタの使用方法について詳しくは、[このビデオ](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)をご覧ください。
