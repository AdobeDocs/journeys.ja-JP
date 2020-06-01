---
title: データソースについて
description: 'データソースの設定方法を説明します '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 690f8c1732c7d54c234e9ba633a2cf014492f423
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 100%

---


# データソースについて {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="データソースについて"
>abstract="データソースの設定は、常に技術ユーザーが実行します。データソースを設定すると、システムへの接続を定義して、ジャーニーで使用される（条件定義、アクションのパラメーターとパーソナライズ機能データ、カスタム待機定義、カスタムタイムゾーン定義に対する）追加情報を取得できます。"

データソースを設定すると、次のような目的で、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。

* [条件定義](../building-journeys/condition-activity.md)
* [アクション](../action/action.md)のパラメーターとパーソナライズ機能データ
* [カスタム待機定義](../building-journeys/wait-activity.md#custom)
* [カスタムタイムゾーン定義](../building-journeys/timezone-management.md)

この設定は、ジャーニーがイベントペイロードからのローカルデータのみを活用する場合は必要ありません。例えば、ジャーニーがイベントとそれに続くイベントのデータのみを使用する E メールアクティビティで構成される場合、データソースを設定する必要はありません。

データソースには次の 2 種類があります。

* リアルタイム顧客プロファイルサービスへの接続を定義する、事前設定済みの Experience Platform データソース。これは組み込みのデータソースです。[](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる外部データソース。これは作成可能なデータソースです。[](../datasource/external-data-sources.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。フィールドグループは、データソースから取得できるフィールドのセットです。[](../datasource/field-groups.md)を参照してください。

Experience Platform データソースと外部データソースの設定方法、およびデータを特定してジャーニーで使用する方法について詳しくは、この[チュートリアルビデオ](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html)をご覧ください。

主なデータソース設定手順は次のとおりです。

>[!NOTE]
>
>データソースの設定は、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

1. 上部のメニューで、「**[!UICONTROL データソース]**」タブをクリックします。

   データソースのリストが表示されます。インターフェイスの詳細については、[](../about/user-interface.md)を参照してください。

   ![](../assets/journey18.png)

1. 次に、組み込みデータソースにフィールドグループを追加する（[](../datasource/adobe-experience-platform-data-source.md)を参照）か、新しい外部データソースを作成（[](../datasource/external-data-sources.md)を参照）し、関連付けられたフィールドグループを作成する（[](../datasource/field-groups.md)を参照）ことができます。

   ![](../assets/journey23.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   データソースが設定され、ジャーニーで使用できる状態になります。
