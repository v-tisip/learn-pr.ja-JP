<!--TODO: Explain how to do ExecuteNext (pages closer to SDK imp) vs ToList (continuation token)--> ご利用のアプリケーションでドキュメントが作成されました。それでは、アプリケーションからドキュメントにクエリを実行してみましょう。 Azure Cosmos DB では、SQL クエリと LINQ クエリが使用されます。 SQL クエリとそれをポータルで実行する方法については、「**Add data and query data in your database**」 (データベースでデータを追加し、クエリを実行する) モジュールで説明します。 

そのため、この演習では、アプリケーションから SQL クエリと LINQ クエリを実行する方法について重点的に取り上げます。

オンライン小売店アプリケーションのために作成したユーザー ドキュメントを利用し、これらのクエリをテストします。

## <a name="linq-query-basics"></a>LINQ クエリの基本

LINQ は、計算処理をオブジェクトのストリームに対するクエリとして表現する .NET プログラミング モデルです。 Azure Cosmos DB に直接照会する **IQueryable** オブジェクトを作成できます。照会すると、LINQ クエリが Cosmos DB クエリに変換されます。 次にクエリが Azure Cosmos DB サーバーに渡されることで、結果セットが JSON 形式で取得されます。 返された結果は、クライアント側で .NET オブジェクトのストリームに逆シリアル化されます。 LINQ クエリはアプリケーション コードにおけるオブジェクトとの連携方法とデータベースで実行されるクエリ ロジックの表現方法に 1 つの一貫性のあるプログラミング モデルを提供するため、開発者の多くは LINQ クエリを好みます。

次の表は、LINQ クエリが SQL に変換されるしくみをまとめたものです。

| LINQ 式 | SQL 変換 |
|---|---|
| `input.Select(family => family.parents[0].familyName);`| `SELECT VALUE f.parents[0].familyName FROM Families f` |
|`input.Select(family => family.children[0].grade + c); // c is an int variable` | `SELECT VALUE f.children[0].grade + c FROM Families f` |
|`input.Select(family => new { name = family.children[0].familyName, grade = family.children[0].grade + 3});`| `SELECT VALUE {"name":f.children[0].familyName, "grade": f.children[0].grade + 3 } FROM Families f`|
|`input.Where(family=> family.parents[0].familyName == "Smith");`|`SELECT * FROM Families f WHERE f.parents[0].familyName = "Smith"`|

## <a name="run-sql-and-linq-queries"></a>SQL クエリと LINQ クエリの実行

1. 次のサンプルでは、.NET コードから SQL、LINQ、LINQ lambda でクエリが実行される様子を確認できます。 コードをコピーし、**DeleteUserDocument**メソッドの後に追加します。

    ```csharp
    private void ExecuteSimpleQuery(string databaseName, string collectionName)
    {
        // Set some common query options
        FeedOptions queryOptions = new FeedOptions { MaxItemCount = -1 };
    
            // Here we find the Andersen family via its LastName
            IQueryable<USer> userQuery = this.client.CreateDocumentQuery<Family>(
                    UriFactory.CreateDocumentCollectionUri(databaseName, collectionName), queryOptions)
                    .Where(u => u.LastName == "Sun");
    
            // The query is executed synchronously here, but can also be executed asynchronously via the IDocumentQuery<T> interface
            Console.WriteLine("Running LINQ query...");
            foreach (User user in userQuery)
            {
                Console.WriteLine("\tRead {0}", user);
            }
    
            // Now execute the same query via direct SQL
            IQueryable<User> userQueryInSql = this.client.CreateDocumentQuery<User>(
                    UriFactory.CreateDocumentCollectionUri(databaseName, collectionName),
                    "SELECT * FROM User WHERE User.LastName = 'Sun'",
                    queryOptions);
    
            Console.WriteLine("Running direct SQL query...");
            foreach (User user in userQueryInSql)
            {
                    Console.WriteLine("\tRead {0}", user);
            }
    
            Console.WriteLine("Press any key to continue ...");
            Console.ReadKey();
    }
    ```

2. 次のコードをコピーし、**BasicOperations** メソッドの `await this.DeleteUserDocument("Users", "WebCustomers", "1");` 行の前に貼り付けます。

    ```csharp
    this.ExecuteSimpleQuery("Users", "WebCustomers");
    ```

3. Program.cs ファイルを保存し、統合ターミナルで次のコマンドを実行します。
    
    ```
    dotnet run
    ```

    コンソールには次の出力が表示されます。

    ```
    Running LINQ query...
    Running direct SQL query...
    Press any key to continue ...
    ```

    お疲れさまでした。 SQL クエリと LINQ クエリを使用し、ユーザーの Azure Cosmos DB コレクションを用意できました。

## <a name="summary"></a>まとめ

この演習では、LINQ クエリについて学習し、LINQ クエリと SQL クエリをアプリケーションに追加し、ユーザー レコードを取得しました。