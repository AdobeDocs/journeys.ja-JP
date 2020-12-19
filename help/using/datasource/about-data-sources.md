---
product: adobe campaign
solution: Journey Orchestration
title: データソースについて
description: 'データソースの設定方法を説明します '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# データソースについて {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="データソースについて"
>abstract="データソースの設定は、常に技術ユーザーが実行します。データソースを設定すると、システムへの接続を定義して、ジャーニーで使用される（条件定義、アクションのパラメーターとパーソナライゼーションデータ、カスタム待機定義、タイムゾーン定義に対する）追加情報を取得できます。"

データソースを設定すると、次のような目的で、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。

* [条件定義](../building-journeys/condition-activity.md)
* [アクション](../action/action.md)のパラメーターとパーソナライズ機能データ
* [カスタム待機定義](../building-journeys/wait-activity.md#custom)
* [タイムゾーン定義](../building-journeys/timezone-management.md)

この設定は、ジャーニーがイベントペイロードからのローカルデータのみを活用する場合は必要ありません。例えば、ジャーニーがイベントとそれに続くイベントのデータのみを使用する E メールアクティビティで構成される場合、データソースを設定する必要はありません。

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

   データソースのリストが表示されます。インターフェイスの詳細は、[このページ](../about/user-interface.md)を参照してください。

   ![](../assets/journey18.png)

1. 次に、組み込みデータソースにフィールドグループを追加する（「[このページ](../datasource/adobe-experience-platform-data-source.md)」を参照）か、新しい外部データソースを作成し（「[このページ](../datasource/external-data-sources.md)」を参照）、関連フィールドグループを作成します（「[このページ](../datasource/field-groups.md)」を参照）。

   ![](../assets/journey23.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   データソースが設定され、ジャーニーで使用できる状態になります。
