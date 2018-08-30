これで温度サービスを実装する準備ができました。 前のユニットでは、サーバーのないソリューションが自分のニーズに最適であることがわかりました。 サーバーなしの Azure 関数を実装するには、"家と呼べる" 場所を与える必要があります。 この "家" が Azure 関数アプリです。

## <a name="azure-function-app-overview"></a>Azure 関数アプリの概要
Azure 関数は、関数アプリと呼ばれているコンテナーでホストされます。 関数を論理的にグループ化し、構造化する目的で、Azure に関数アプリを定義します。 関数アプリは Azure のコンピューティング リソースです。 エレベーターの例では、たとえば、エスカレーター駆動歯車の温度サービスをホストする関数アプリを作成します。 関数アプリを作成するためには、いくつかの決定を行う必要があります。サービス プランを選択し、互換性のあるストレージ アカウントを選択する必要があります。

### <a name="choosing-a-service-plan"></a>サービス プランの選択
関数アプリでは、2 種類のサービス プランのいずれかを使用できます。 最初のサービス プランは、従量課金サービス プランです。 これは、Azure のサーバーレス アプリケーション プラットフォームを使用するときに選択するプランです。 従量課金サービス プランでは、自動スケーリングを提供し、関数が実行されているときに課金します。 従量課金プランには、関数の実行に対して構成可能なタイムアウト期間が付属します。 既定は 5 分ですが、最長 10 分までのタイムアウトを構成できます。 

2 つ目のプランは Azure App Service プランと呼ばれています。 このプランでは、VM で関数を連続的に実行できます。 関数が連続的に使用される場合、あるいは従量課金プランよりも多くの処理能力または実行時間が必要な場合に、このオプションを選択します。 

### <a name="storage-account-requirements"></a>ストレージ アカウントの要件
関数アプリを作成すると、そのアプリは通常、Azure Blob、Queue、Table ストレージをサポートするストレージ アカウントにリンクされます。 関数アプリでは、関数実行の記録や実行トリガーの管理など、内部操作のためにこのストレージ アカウントが使用されます。 これは、従量課金サービス プランで、Azure 関数コードと構成ファイルが格納される場所でもあります。 