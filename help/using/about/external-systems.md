---
product: adobe campaign
solution: Journey Orchestration
title: 外部システムとの統合
description: 外部システムを統合する際のベストプラクティスを説明します
feature: ジャーニー
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# 外部システムとの統合{#external-systems}

このページでは、外部システムを統合する際にJourney Orchestrationが提供する様々なガードレールと、ベストプラクティスを示します。制限APIを使用して外部システムの保護を最適化する方法、ジャーニータイムアウトの設定方法、再試行の仕組み。

Journey Orchestrationを使用すると、カスタムデータソースおよびカスタムアクションを介した外部システムへの接続を設定できます。 これにより、例えば、外部の予約システムからのデータを使用してジャーニーをエンリッチメントしたり、EpsilonやFacebookなどのサードパーティシステムを使用してメッセージを送信したりできます。

外部システムを統合する際に、いくつかの問題が発生したり、システムが低速になったり、応答が停止したり、大量に処理できない場合があります。 Journey Orchestrationには、システムを過負荷から保護するためのガードレールがいくつか用意されています。

外部システムは、パフォーマンスの点で異なります。 各使用例に合わせて設定を調整する必要があります。

Journey Orchestrationが外部APIの呼び出しを実行する場合、テクニカルガードレールは次のように実行されます。

1. キャッピング：キャッピングルールが適用されます。
2. タイムアウトと再試行：

## 制限

組み込みのCapping APIは、外部システムの保護に役立つアップストリームの技術ガードレールを提供します。 事前に、外部APIの処理能力を評価する必要があります。 例えば、Journey Orchestrationが1秒あたり1000件の呼び出しを送信し、システムが1秒あたり100件の呼び出しのみをサポートする場合、システムが飽和しないように制限ルールを定義する必要があります。

キャッピングルールは、特定のエンドポイント（URL呼び出し）のサンドボックスレベルで定義されます。 実行時に、Journey Orchestrationは、制限ルールが定義されているかどうかを検証し、そのエンドポイントへの呼び出し中に、定義された率を適用します。 呼び出しの数が定義された速度を超えると、残りの呼び出しは破棄されます。

キャッピングルールは、1つのエンドポイントに固有ですが、サンドボックスのすべてのジャーニーに対してグローバルです。 つまり、呼び出しスロットは、サンドボックスのすべてのジャーニー間で共有されます。 例えば、外部システムで、1秒あたり100コールの制限が定義され、10種類のジャーニーのカスタムアクションによって呼び出されたとします。 1つのジャーニーが1秒あたり200通の呼び出しを受け取った場合、100個のスロットが使用可能なままになり、残りの100個のスロットは破棄されます。 最大率は既に超えているので、他の9つのジャーニーには使用可能なスロットはありません。 この精度は、外部システムを過負荷やクラッシュから保護するのに役立ちます。

制限によって破棄された呼び出しは、レポートではエラーとしてカウントされます。

キャッピングルールの設定方法については、[このページ](../api/timezone-management.md)を参照してください。

## タイムアウトと再試行

Ensuite ->タイムアウト定義、et qui定義le temps maximal qu&#39;on aloue a lappel au sys externale. ペンダントce temps là, on essie de faire des appels. fait un appel, si&#39;appel dure moinre longtemps le timeout ca marche, si plus longtemps on voit ca comme une timeout error, et coté reporting compabilisé comme une erreur. si&#39;appel echoue, （プランタースール500 outre），再試行します。 3再試行最大、パスは設定可能 SI ca excede le timeoutglobal (par exemple 2 essais, mais depasse le timeout) erreur de timeout. plsu de temps que nesiare（プル・デ・テンプス・ク・ニセア） タイムアウトdurée max qu&#39;on alloue a appel et aux再試行はerreursです。

