多くのアプリケーションは、いくつかの別のコンピューターまたはデバイスで実行されるプログラムで構成されています。 このような分散アプリケーションでは、メッセージは、ネットワークの各地へ長距離でコンポーネント間で送信される必要があります。 同じサーバーやデータ センター上にあった場合でも、アーキテクチャの結合が弱い場合、コンポーネントの通信にはメカニズムが必要です。 信頼できるメッセージングは、しばしば重要な問題となります。

音楽を共有するアプリケーションを開発しているソフトウェア企業で働いてるとします。 ミュージシャンは、Web フロント エンドまたはモバイル アプリを使用して作成した音楽を、使用しているプラットフォームにアップロードできます。 彼らは、他のメンバーの作品を聴いたり、それにコメントすることができます。 このアプリケーションは、ご利用の ISP で実行される Web サイト、ユーザーのモバイル デバイスで実行されるモバイル アプリ、Azure で実行される Web API、データが格納される Azure SQL Database で構成されます。

需要が高いときに、一部の音楽ファイルが正常にアップロードされなかったり、一部のコメントが投稿されないことが確認されました。 テスト結果では、フロントエンドのコンポーネントと Web API 間でメッセージが削除されることによってこれらの問題が発生していることがわかりました。 ストレージ キュー、Event Hubs、Event Grid、Service Bus の Azure テクノロジの 1 つ以上を使用してこれらの問題を解決しようと計画しています。

ここでは、分散アプリケーションのそれぞれの通信タスク用に、Azure の正しいメッセージング技術を選択する方法を学習します。

## <a name="learning-objectives"></a>学習の目的

- イベントとメッセージを説明し、分散アプリケーションで解決するための課題について説明します。
- アプリケーションのメッセージング テクノロジとして、Azure Storage キューが最良であるシナリオを特定する。
- アプリケーションのメッセージング テクノロジとして、Azure Event Grid が最良であるシナリオを特定する。
- アプリケーションのメッセージング テクノロジとして、Azure Event Hubs が最良であるシナリオを特定する。
- アプリケーションのメッセージング テクノロジとして、Azure Service Bus が最良であるシナリオを特定する。