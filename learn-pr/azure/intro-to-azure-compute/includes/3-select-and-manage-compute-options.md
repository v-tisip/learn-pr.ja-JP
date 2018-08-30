利用できる Azure コンピューティング サービスの概要がわかったので、各サービスをどのようなときに使用すればよいか決められるように各サービスを順番に見ていきましょう。

## <a name="azure-virtual-machines"></a>Azure Virtual Machines

オペレーティング システムと環境を完全に制御する必要がある場合は、Virtual Machines が理想的な選択肢です。 物理コンピューターと同じように、VM で実行されているすべてのソフトウェアをカスタマイズすることができます。 これは、カスタム ソフトウェアまたはカスタム ホスト構成を実行するときに適しています。

物理サーバーからクラウドに移行するときも、VM が優れた選択肢です。 多くの場合、物理サーバーのイメージを作成し、仮想マシン内でそれをホストできます。 これにより、オペレーティング システムとアプリケーション実行環境を完全に自由に選択でき、好みのツールを使用するほぼすべての言語で開発することができます。

ただし、仮想マシンを維持する必要があります。 これは、オペレーティング システムとそこで実行されているソフトウェアを更新することを意味します。 

また、スケーリングするときもいっそうの考慮が必要です。 仮想マシンをスケールアップできます。つまり、コンピューティング リソースとメモリ リソースを追加できます。 ただし、複数のインスタンスを並列で実行する必要がある場合は、ロード バランサーのようなサービスを追加することが必要な場合があります。

小売り Web サイトをホストする Web サイトを実行しているところを想像してみてください。 VM を複製した場合、複数の Web サイト VM インスタンス間で要求をルーティングするサービスを追加する必要があります。

Azure では高度な仮想マシン サービスも利用できます。

* 同じように構成された VM で同じアプリまたはアプリ セットの常に使用可能なインスタンスを実行する場合は、**Virtual Machine Scale Sets** オプションを使用します。 何千もの同一の VM が自動的に生成されてアプリケーションが分単位で読み込まれるので、ユーザーは待つ必要がありません。 また、仮想マシンを事前にプロビジョニングする必要がないため、いつでもアプリケーションで必要なコンピューティング リソースだけが使用されます。

* 手が加えられていないコンピューティング能力またはスーパーコンピューター レベルのコンピューティング パワーが必要な場合があります。 **Batch** オプションでは、何十、何百、または数千もの VM にスケーリングする機能を備えたクラウド規模のジョブ スケジューリングおよびコンピューティング管理が提供されます。 スーパーコンピューターの機能を備えた VM を指定することさえできます。

## <a name="azure-containers"></a>Azure コンテナー

単一の仮想マシンでアプリケーションの複数のインスタンスを実行したい場合は、コンテナーが優れた選択肢です。 コンテナー オーケストレーターで、必要に応じてアプリケーション インスタンスを開始、停止、スケールアウトできます。

ただし、コンテナーがよく使用されるのは、マイクロサービス アーキテクチャを使用してソリューションを作成する場合です。 ソリューションを小さな部分に分割するためにコンテナーを使用することがよくあります。 たとえば、1 つの Web サイトを、フロントエンドをホストするコンテナー、バックエンドをホストするコンテナー、ストレージ用の 3 つ目のコンテナーに分割できます。 これにより、独立して維持、スケーリング、更新できる論理的なセクションに、アプリの部分を分離することができます。

Web サイトのバックエンドは容量に達したけれども、フロントエンドとストレージはまだ余裕がある場合を想像してください。 バックエンドを個別にスケーリングして、パフォーマンスを向上させることができます。 または、別のストレージ サービスを使用することもできます。 または、アプリケーションの他の部分に影響を与えずに、ストレージ コンテナーを置き換えることができます。

 チームが Kubernetes コンテナー オーケストレーションを使い慣れている場合は、**Azure Kubernetes Service (AKS)** オプションを検討します。 Kubernetes オーケストレーションの管理、展開、操作が簡素化および自動化されます。

## <a name="azure-functions"></a>Azure Functions

サービスを実行しているコードのみに関心があり、基になるプラットフォームやインフラストラクチャには関心がない場合は、Azure Functions が最適です。 REST 要求、タイマー、または別の Azure サービスからのメッセージによるイベントに応答して処理を実行する必要があり、数秒以内にすばやく処理を完了できる場合に、よく使用されます。

Azure Functions は自動的にスケーリングされるので、需要が変化する場合に優れた選択肢であり、関数がトリガーされたときにのみ課金されます。 たとえば、配送車群を監視するために使用されている IoT ソリューションからのメッセージを受信するような場合があります。 業務時間中は受信データが増える可能性があります。

Azure Functions はステートレスであり、イベントに応答するたびに再起動されたかのように動作します。 これは、受信データを処理するために最適です。 状態が必要な場合は、Azure ストレージ サービスに接続できます。