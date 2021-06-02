---
product: adobe campaign
title: タイムゾーン管理
description: タイムゾーン管理の詳細
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 2%

---

# タイムゾーン管理 {#timezone_management}

タイムゾーンは、ジャーニーの[プロパティ](../building-journeys/changing-properties.md)で定義できます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含むジャーニーのすべてのアクティビティで使用されます。

* [時間条件](../building-journeys/condition-activity.md#time_condition)
* [日付条件](../building-journeys/condition-activity.md#date_condition)
* [カスタム待機](../building-journeys/wait-activity.md#custom)
* [固定日の待機](../building-journeys/wait-activity.md#fixed_date)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するかを選択できます。

## 固定タイムゾーンの定義{#fixed-timezone}

タイムゾーンは固定することもできます。 事前定義済みのタイムゾーンをクリアし、ドロップダウンリストからタイムゾーンを選択します。 固定タイムゾーンを使用する場合、ジャーニーに入るすべてのユーザーが同じタイムゾーンになります。

それには、**[!UICONTROL プロパティ]**&#x200B;でタイムゾーンを選択します。

![](../assets/journey72.png)

## プロファイルを使用したジャーニータイムゾーンの定義{#timezone-from-profiles}

ジャーニーのエントリイベントに名前空間(ジャーニーがAdobe Experience Platformのリアルタイム顧客プロファイルサービスに到達できる)がある場合、タイムゾーンは、ジャーニーをフローする個人のプロファイルで指定されたタイムゾーンで事前定義されます。

タイムゾーンがAdobe Experience Platformプロファイルで定義されている場合、そのタイムゾーンはジャーニーで取得できます。

個人のプロファイルにタイムゾーンが含まれていない場合、取得されるタイムゾーンは、 timezoneフィールドで定義されたタイムゾーンになります。

これをおこなうには、**[!UICONTROL プロパティ]**&#x200B;で、「**[!UICONTROL タイマーと条件でプロファイルタイムゾーンを使用する]**」をオンにします。

![](../assets/journey73.png)

## 式{#timezone-in-expressions}でのタイムゾーンの使用

ジャーニーの開始日と終了日を特定のタイムゾーンにリンクすることはできません。 インスタンスのタイムゾーンに自動的に関連付けられます。
