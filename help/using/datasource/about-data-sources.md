---
title: データソースについて
description: 'データソースの設定方法 '
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
source-git-commit: d0a7bbb43ae62fbdcf7ef34b0b56b1d437047ad2

---


# データソースについて {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;データソースについて&quot;
>abstract=&quot;データソースの設定は、常に技術ユーザーが実行します。 データソース設定を使用すると、次の目的で、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。条件の定義、アクション内のパラメーターとパーソナライゼーションデータ、カスタムの待機の定義、カスタムのタイムゾーンの定義。」

データソースの設定は、常に技術ユーザーが実 **行します**。

データソース設定を使用すると、次の目的で、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。

* 条件定義
* アクション内のパラメーターとパーソナライゼーションデータ
* カスタムの待機定義
* カスタムタイムゾーンの定義

この設定は、ジャーニーがイベントペイロードからのローカルデータのみを利用する場合は不要です。 例えば、旅行がイベントに続いて、そのイベントのデータのみを使用する電子メールアクティビティで構成されている場合は、データソースを設定する必要はありません。

データソースには2種類あります。

* Real-time Customer Profile Serviceへの接続を定義する、事前設定済みのExperience Platformデータソース。 これは組み込みデータソースです。 [](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる外部データソース。 これらを作成できます。 [](../datasource/external-data-sources.md)を参照してください。

各データソースに対して、フィールドグループを使用して取得する情報を定義します。 [](../datasource/field-groups.md)を参照してください。

以下に、主なデータソース設定手順を示します。

1. 上部のメニューで、タブをクリック **[!UICONTROL Data Sources]**します。

   データソースのリストが表示されます。 インターフ [](../about/user-interface.md) ェイスの詳細については、を参照してください。

   ![](../assets/journey18.png)

1. 次に、組み込みデータソースにフィールドグループを追加する(「 」を参照 [](../datasource/adobe-experience-platform-data-source.md))か、新しい外部データソースを作成し（「 」を参照）、関連するフィールドグループを作成 [](../datasource/external-data-sources.md)する(「 」を参照 [](../datasource/field-groups.md))ことができます。

   ![](../assets/journey23.png)

1. クリック **[!UICONTROL Save]**.

   これで、データソースが設定され、ジャーニーで使用できる状態になりました。
