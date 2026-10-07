---
product: adobe campaign
title: データソースについて
description: データソースの設定方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 100%
---
# データソースについて {#concept_s1s_dqt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_



>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="データソースについて"
>abstract="データソース設定では、ジャーニーで使用する追加情報を取得するためにシステムへの接続を定義できます。"

データソース設定を使用すると、システムへの接続を定義して、ジャーニーにおいて次の目的でジャーニーで使用される追加情報を取得できます。

* [条件の定義](../building-journeys/condition-activity.md)
* [アクション](../action/action.md)のパラメーターとパーソナライゼーションデータ
* [カスタムの待機の定義](../building-journeys/wait-activity.md#custom)
* [タイムゾーンの定義](../building-journeys/timezone-management.md)

ジャーニーがイベントペイロードからのローカルデータのみを活用する場合、この設定は必要ありません。 例えば、ジャーニーがイベントとそれに続くイベントのデータのみを使用する電子メールアクティビティで構成される場合、データソースを設定する必要はありません。

データソースには次の 2 種類があります。

* リアルタイム顧客プロファイルサービスへの接続を定義する、事前設定済みの Adobe Experience Platform データソース。 これはビルトインのデータソースです。 [このページ](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる外部データソース。 これは作成可能なデータソースです。 [このページ](../datasource/external-data-sources.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。 フィールドグループは、データソースから取得できるフィールドのセットです。 [このページ](../datasource/field-groups.md)を参照してください。

主なデータソース設定手順は次のとおりです。

>[!NOTE]
>
>データソースの設定は、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

1. メニューウィンドウで、「**[!UICONTROL 管理者]**」を選択します。 「**[!UICONTROL データソース]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。

   データソースのリストが表示されます。 インターフェイスの詳細については、[このページ](../about/user-interface.md)を参照してください。

   ![](../assets/journey18.png)

1. 次に、ビルトインデータソースにフィールドグループを追加するか（[このページ](../datasource/adobe-experience-platform-data-source.md)を参照）、新しい外部データソース（[このページ](../datasource/external-data-sources.md)を参照）および関連付けられたフィールドグループを作成する（[このページ](../datasource/field-groups.md)を参照）ことができます。

   ![](../assets/journey23.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   データソースが設定され、ジャーニーで使用できる状態になります。
