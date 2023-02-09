---
product: adobe campaign
title: タイムゾーン管理
description: タイムゾーン管理について説明します。
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%

---

# タイムゾーン管理 {#timezone_management}

タイムゾーンは、ジャーニーの[プロパティ](../building-journeys/changing-properties.md)で定義できます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含むジャーニーのすべてのアクティビティで使用されます。

* [時間条件](../building-journeys/condition-activity.md#time_condition)
* [日付条件](../building-journeys/condition-activity.md#date_condition)
* [カスタム待機](../building-journeys/wait-activity.md#custom)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するかを選択できます。

>[!NOTE]
>
>プロファイルタイムゾーンは、**環境設定詳細** フィールドグループにある **timeZone** フィールドと連携します。

## 固定タイムゾーンの定義 {#fixed-timezone}

タイムゾーンを固定することもできます。定義済みのタイムゾーンをクリアし、ドロップダウンリストからタイムゾーンを選択します。固定タイムゾーンを使用すると、ジャーニーにエントリするすべての個人のタイムゾーンは同じになります。

これをおこなうには、「**[!UICONTROL プロパティ]**」でタイムゾーンを選択します。

![](../assets/journey72.png)

## プロファイルを使用したジャーニータイムゾーンの定義 {#timezone-from-profiles}

ジャーニーのエントリイベントに名前空間がある（ジャーニーが Adobe Experience Platform のリアルタイム顧客プロファイルサービスにアクセスする）場合、プロファイルレベルで定義されたタイムゾーンを使用できます。 これを行うには、**プロパティ**&#x200B;で、「**タイマーと条件でプロファイルのタイムゾーンを使用する**」のチェックをオンにします。このオプションは、デフォルトではオンになっていません。

プロファイルのタイムゾーンが定義されている場合、そのタイムゾーンが取得され、ジャーニーで使用されます。 タイムゾーンが定義されていない場合、使用されるタイムゾーンは、 タイムゾーンフィールドで定義されたタイムゾーンになります。

![](../assets/journey73.png)

## タイムゾーン式の使用 {#timezone-in-expressions}

ジャーニーの開始日と終了日を特定のタイムゾーンにリンクすることはできません。これらはインスタンスのタイムゾーンに自動的に関連付けられます。
