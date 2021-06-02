---
product: adobe campaign
title: データソースについて
description: 'データソースの設定方法を説明します '
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 81%

---

# データソースについて {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="データソースについて"
>abstract="データソースの設定を使用すると、システムへの接続を定義して、ジャーニーで使用される追加情報を取得できます。"

データソースを設定すると、次のような目的で、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。

* [条件定義](../building-journeys/condition-activity.md)
* [アクション](../action/action.md)のパラメーターとパーソナライズ機能データ
* [カスタム待機定義](../building-journeys/wait-activity.md#custom)
* [タイムゾーン定義](../building-journeys/timezone-management.md)

この設定は、ジャーニーがイベントペイロードからのローカルデータのみを活用する場合は必要ありません。例えば、ジャーニーがイベントとそれに続くイベントのデータのみを使用する電子メールアクティビティで構成される場合、データソースを設定する必要はありません。

データソースには次の 2 種類があります。

* リアルタイム顧客プロファイルサービスへの接続を定義する、事前設定済みの Adobe Experience Platform データソース。これは組み込みのデータソースです。[このページ](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる外部データソース。これは作成可能なデータソースです。[このページ](../datasource/external-data-sources.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。フィールドグループは、データソースから取得できるフィールドのセットです。[このページ](../datasource/field-groups.md)を参照してください。

Adobe Experience Platform データソースと外部データソースの設定方法、およびデータを特定してジャーニーで使用する方法について詳しくは、この[チュートリアル動画](https://docs.adobe.com/content/help/ja-JP/journey-orchestration-learn/tutorials/configure-data-sources.html)をご覧ください。

主なデータソース設定手順は次のとおりです。

>[!NOTE]
>
>データソースの設定は、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

1. 上部のメニューで、「**[!UICONTROL データソース]**」タブをクリックします。

   データソースのリストが表示されます。インターフェイスの詳細については、[このページ](../about/user-interface.md)を参照してください。

   ![](../assets/journey18.png)

1. 次に、組み込みデータソースにフィールドグループを追加する（[このページ](../datasource/adobe-experience-platform-data-source.md)を参照）か、新しい外部データソースを作成（[このページ](../datasource/external-data-sources.md)を参照）し、関連するフィールドグループを作成します（[このページ](../datasource/field-groups.md)を参照）。

   ![](../assets/journey23.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   データソースが設定され、ジャーニーで使用できる状態になります。
