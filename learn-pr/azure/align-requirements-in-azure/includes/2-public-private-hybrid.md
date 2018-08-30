あなたは医療関連企業で働いているとします。 レガシ システムと基幹業務システムを使用しており、将来的に新システムを使用する計画があります。 クラウド コンピューティングを使用することには利点があると聞いています。 パブリック クラウド、プライベート クラウド、ハイブリッド クラウドという異なるそれぞれのソリューション向けに、最適なデプロイ モデルをどのようにして選びますか。

## <a name="what-is-cloud-computing"></a>クラウド コンピューティングとは

クラウド コンピューティングでは、インターネット経由でサービスとアプリケーションをオンデマンドでプロビジョニングします。 サーバー、アプリケーション、データ、およびその他のリソースは、サービスとして提供されます。 

ユーザー側から見ると、サービスの詳細は抽象化されています。 コンピューティング リソースを迅速にプロビジョニングし、最小限の管理でサービスを使用できます。 クラウド コンピューティングとはインターネット経由で利用できるデータセンターだと考えるのは適切ではありません。 クラウド コンピューティングは、仮想化、低コストで入手できるハードウェア、自動化されたプロセスを使用して、セルフサービス式のユーザー エクスペリエンスを利用者に提供するものであり、公共サービスに似ています。 

クラウド コンピューティングには、パブリック クラウド、プライベート クラウド、ハイブリッド クラウドという 3 つのデプロイ モデルがあります。

![クラウド デプロイ モデル](../media/2-cloud-deployment.png)

## <a name="public-cloud"></a>パブリック クラウド

パブリック クラウドは、クラウド コンピューティングのデプロイ方法として最も一般的な方法です。 サービスはパブリック インターネット経由で提供され、サービスの購入希望者はだれでもサービスを利用できます。 サーバーやストレージなどのクラウド リソースは、サードパーティのクラウド サービス プロバイダーによって所有および運用され、インターネット経由で提供されます。 サービスには無料のものとオンデマンドで購入するものがあり、利用者は使用した CPU サイクル、ストレージ、または帯域幅の消費量に応じた料金のみを支払います。 Microsoft Azure はパブリック クラウドの一例です。 

勤務先の医療関連企業で、登録用の Web サイトが必要だとします。 そのサイトには、拡大縮小できること、年間を通して何度か発生する登録のピーク時に応答性を維持できることが求められます。 顧客は世界中の場所からサイトにアクセスします。 パブリック クラウドを使用して自動的にスケールアップし、登録のピーク時の需要に対応できます。 サイトのトラフィックが少ないときは、サイトをスケールダウンしてコストを抑えることができます。 ピーク需要時のサイトの応答性が維持され、必要になったときにだけ追加リソースを購入します。 また、複数の地理的リージョンに Web サイトをデプロイして信頼性と応答性を高めることもできます。

開発者は、Web サイト開発時に複数の開発環境を作成することで、開発プロセスを迅速化できます。 開発者はパブリック クラウドを使用して、サンドボックス環境用に仮想マシンを迅速にプロビジョニングし、ソリューションを開発できます。 開発者は不要になった環境を削除できます。

### <a name="why-public-cloud"></a>パブリック クラウドを使用する理由

パブリック クラウドは、オンプレミスのインフラストラクチャよりも迅速に、ほぼ無限の拡張性を持ったプラットフォームを使用してデプロイすることができます。 インターネットにアクセスすることさえできれば、会社のすべての従業員が、任意のデバイスを使用して、どのオフィスまたは支社からでも同じアプリケーションを利用できます。 

パブリック クラウドを使用する理由の例:

- **従量制またはサブスクリプションによるオンデマンドでのサービス消費:** オンデマンドまたはサブスクリプション モデルでは、CPU、ストレージ、その他のリソースについて、使用または予約した分だけの料金がかかります。
- **ハードウェアの初期投資が不要:** オンプレミス ハードウェアやアプリケーション インフラストラクチャを購入、管理、メンテナンスする必要はありません。 システムの管理とメンテナンスは、すべてクラウド サービス プロバイダーが担当します。 
- **自動化:** Web ポータルまたはスクリプトを使用して、または自動的に、インフラストラクチャのリソースを迅速にプロビジョニングできます。 
- **地理的な分散:** データを必要なときに手近な場所で見つけることができ、自社で多数のデータセンターを持つ必要がありません。
- **ハードウェア メンテナンスの削減:** ハードウェアのメンテナンスはサービス プロバイダーの責任において行われます。

## <a name="private-cloud"></a>プライベート クラウド

プライベート クラウドは、1 つの企業または組織に属する特定のユーザー専用のコンピューティング リソースで構成されます。 組織のオンサイト データセンターに物理的に配置される場合と、サードパーティのサービス プロバイダーによってホストされる場合があります。 プライベート クラウドという用語を、従来のオンプレミス データセンターが名称変更されたものだと考えるのは、適切ではありません。 プライベート クラウドでは、オンプレミスのインフラストラクチャとサービスを使用して、パブリック クラウドと同様の利点が提供されます。 抽象化プラットフォームを使用して、Kubernetes クラスターなどの*クラウドに似た*サービスや、Azure Stack のような完全なクラウド環境を実現できます。 ハードウェアの購入、構成、メンテナンスは、組織が行います。 システム間の通信は通常、企業が所有してメンテナンスを行うネットワーク インフラストラクチャ上で実行されます。 例として、非公開の社内ネットワークや、建物間の専用光ファイバー接続があります。

あなたが勤務している医療関連企業が、自社データセンターのうちの 1 つにおいて、あるアプリケーションを使用しているとします。 その運用環境はパブリック クラウドにレプリケートできません。 新しい要件として、別のデータセンターにあるデータにアクセスする必要があります。 そのデータを含むデータベースは、規制に対するコンプライアンスのために、他の拠点に置いておく必要があります。 このシナリオはプライベート クラウドです。 あなたの勤務先の組織が所有する 2 つのデータセンターがあります。 インターネット経由のパブリック クラウド VPN をデータセンター間の接続に使用することが可能です。 ただし、このシナリオは、ソリューションがこの組織以外には非公開であるためプライベート クラウドと考えることができます。

### <a name="why-private-cloud"></a>プライベート クラウドを使用する理由

プライベート クラウドを使用すると、組織に柔軟性がもたらされます。 組織は、特定のビジネス ニーズを満たすために、使用するクラウド環境をカスタマイズできます。 リソースを他の組織と共有しないので、高度なコントロールとセキュリティを実現することが可能です。 また、プライベート クラウドでは一定レベルの拡張性と効率性も得られます。

プライベート クラウドを使用する理由の例:

- **既存の環境:** 既存の運用環境をパブリック クラウドにレプリケートすることができない。 ハードウェアへの、およびソリューションの専門知識を持った人材への大規模な投資。 大規模な組織がコンピューティング リソースのコモディティ化を選択する場合。
- **レガシ アプリケーション:** 配置先を物理的に変更することが容易でない、ビジネスに不可欠なレガシ アプリケーション。
- **データの管轄とセキュリティ:** 政治的な境界線、法的要件によって、データが物理的にどこに存在できるかが指定される場合があります。
- **規制に対するコンプライアンス/認定:** PCI または HIPAA コンプライアンス。 認定されたオンプレミス データセンター。

## <a name="hybrid-cloud"></a>ハイブリッド クラウド

ハイブリッド クラウドは、パブリック クラウドとプライベート クラウドを組み合わせ、それらのクラウド間でデータとアプリケーションを共有できるようにしたコンピューティング環境です。 ハイブリッド クラウド コンピューティングでは、コンピューティングと処理の需要が変動したときに、企業はオンプレミス インフラストラクチャをパブリック クラウドにまでシームレスにスケールアップして、オーバーフローを処理することができます。サードパーティのデータセンターに対して、自社データ全体へのアクセス権を与える必要はありません。 組織は、ビジネスに不可欠なアプリケーションとデータをオンプレミスに、つまり企業のファイアウォールの内側に安全に保持しながら、基本的なコンピューティング タスクと機密性が高くないコンピューティング タスク用に、パブリック クラウドの柔軟性とコンピューティング能力を手に入れることができます。

ハイブリッド クラウドを使用すると、短期的な需要の急増を処理するために事前の設備投資を行う必要性を排除できます。 また、クラウドにあるリソースに対して、どのリソースをローカルなリソースとするかを管理できる柔軟性があります。 企業は、長期的にはアイドル状態のままになる可能性がある、追加のリソースや設備の購入、プログラム、メンテナンスを行うのではなく、一時的に使用したリソースの料金を支払います。 通常、統合は、Azure のようなクラウド プロバイダーとオンプレミスのデータセンターとの間で、セキュリティで保護された VPN を経由して行われます。

勤務先の医療関連企業で、顧客が自分の医療情報にアクセスできるアプリケーションを使用しているとします。 規制により、データを物理的な場所に保管する必要があります。 顧客向け Web サイトは、世界中の多数のユーザーに応答できる必要があります。  ソリューションとして、データベースをオンプレミスのデータセンター内でホストし、Web サイトをパブリック クラウド内でホストすることが考えられます。 オンプレミスのデータセンターとパブリック クラウドとの間には VPN を使用します。 このシナリオは、ハイブリッド クラウドになります。

### <a name="why-hybrid-cloud"></a>ハイブリッド クラウドを使用する理由

ハイブリッド クラウドを使用すると、組織は機密性の高いアセット向けにプライベート インフラストラクチャを制御し、メンテナンスすることができます。 また、必要になったときにパブリック クラウド内の追加リソースを利用できる柔軟性が得られます。 パブリック クラウドにまでスケールアップできるため、追加のコンピューティング能力に対する支出は、必要なときだけしか発生しません。 クラウドへの移行も容易になります。 時間をかけて段階的に、徐々にワークロードを移行できます。

ハイブリッド クラウドを使用する理由の例:

- **既存のハードウェア投資:** ビジネス上の理由により、既存の運用環境とハードウェアを使用する必要がある場合。
- **規制による要件:** 規制により、データを物理的な場所に保管することが必要な場合。
- **独自の運用環境:** 従来の運用環境をパブリック クラウドにレプリケートできない場合。
- **移行:** ワークロードを徐々にクラウドに移行する場合。