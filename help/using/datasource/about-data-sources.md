---
title: データソースについて
description: 'データソースの設定方法を学びます。 '
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
ht-degree: 3%

---


# データソースについて {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="データソースについて"
>abstract="データソースの設定は、常に技術ユーザーが実行します。 データソース設定を使用すると、次のような目的で、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。 条件の定義、アクションのパラメーターとパーソナライゼーションデータ、カスタム待機の定義、カスタムタイムゾーンの定義"

データソース設定を使用すると、次のような目的で、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。

* [条件定義](../building-journeys/condition-activity.md)
* アク [ション内のパラメーターとパーソナライゼーションデータ](../action/action.md)
* [カスタムの待機の定義](../building-journeys/wait-activity.md#custom)
* [カスタムタイムゾーンの定義](../building-journeys/timezone-management.md)

この設定は、ジャーニーがイベントペイロードからのローカルデータのみを利用する場合は必要ありません。 例えば、イベントとその後にイベントのデータのみを使用する電子メールアクティビティが続く情報で構成される場合、データソースを設定する必要はありません。

データソースには次の2種類があります。

* Real-time Customer Platform Serviceへの接続を定義する、事前設定済みのExperience Platformデータソース。 これは組み込みのデータソースです。 [](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる外部データソース。 以下は作成可能なものです。 [](../datasource/external-data-sources.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。 フィールドグループは、データソースから取得できるフィールドのセットです。 [](../datasource/field-groups.md)を参照してください。

エクスペリエンスプラットフォームデータソースと外部データソースの設定方法、およびデータを探して遍歴で使用する方法について詳しくは、この [チュートリアルビデオをご覧ください](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html)。

主なデータソース設定手順は次のとおりです。

>[!NOTE]
>
>データソースの設定は、常に **技術ユーザーが実行します**。

1. 上部のメニューで、「 **[!UICONTROL データソース]** 」タブをクリックします。

   データソースのリストが表示されます。 インターフェイス [](../about/user-interface.md) の詳細については、を参照してください。

   ![](../assets/journey18.png)

1. 次に、組み込みデータソースにフィールドグループを追加する（を参照）か、新しい外部データソースを作成し（を参照）、関連付けられたフィールドグループ [](../datasource/adobe-experience-platform-data-source.md)を作成する(を参照 [](../datasource/external-data-sources.md)[](../datasource/field-groups.md))ことができます。

   ![](../assets/journey23.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   これで、データソースが設定され、ジャーニーで使用できる状態になりました。
