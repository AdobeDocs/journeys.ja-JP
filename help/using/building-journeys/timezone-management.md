---
product: adobe campaign
title: タイムゾーン管理
description: タイムゾーン管理について説明します。
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 77%

---

# タイムゾーン管理 {#timezone_management}

タイムゾーンは、ジャーニーの[プロパティ](../building-journeys/changing-properties.md)で定義できます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含むジャーニーのすべてのアクティビティで使用されます。

* [時間条件](../building-journeys/condition-activity.md#time_condition)
* [日付条件](../building-journeys/condition-activity.md#date_condition)
* [カスタム待機](../building-journeys/wait-activity.md#custom)
* [固定日待機](../building-journeys/wait-activity.md#fixed_date)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するかを選択できます。

>[!NOTE]
>
>プロファイルタイムゾーンは、**環境設定詳細** フィールドグループにある **timeZone** フィールドと連携します。

## 固定タイムゾーンの定義 {#fixed-timezone}

タイムゾーンを固定することもできます。定義済みのタイムゾーンをクリアし、ドロップダウンリストからタイムゾーンを選択します。固定タイムゾーンを使用すると、ジャーニーにエントリするすべての個人のタイムゾーンは同じになります。

これをおこなうには、「**[!UICONTROL プロパティ]**」でタイムゾーンを選択します。

![](../assets/journey72.png)

## プロファイルを使用したジャーニータイムゾーンの定義 {#timezone-from-profiles}

ジャーニーのエントリイベントに名前空間 ( ジャーニーがAdobe Experience Platformのリアルタイム顧客プロファイルサービスに到達できる ) がある場合、タイムゾーンは、ジャーニーを流れる個人のプロファイルで指定されたタイムゾーンで事前定義されます。

タイムゾーンがAdobe Experience Platformプロファイルで定義されている場合、そのタイムゾーンはジャーニーで取得できます。

個人のプロファイルにタイムゾーンが含まれていない場合、取得されるタイムゾーンはタイムゾーンフィールドに定義されているものになります。

これをおこなうには、「**[!UICONTROL プロパティ]**」で、「**[!UICONTROL タイマーと条件でプロファイルのタイムゾーンを使用する]**」をチェックします。

![](../assets/journey73.png)

## タイムゾーン式の使用 {#timezone-in-expressions}

ジャーニーの開始日と終了日を特定のタイムゾーンにリンクすることはできません。これらはインスタンスのタイムゾーンに自動的に関連付けられます。
