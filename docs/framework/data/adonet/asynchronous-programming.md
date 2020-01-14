---
title: Асинхронное программирование
ms.date: 10/18/2018
ms.assetid: 85da7447-7125-426e-aa5f-438a290d1f77
ms.openlocfilehash: 7bf492e45a9ebabdd36caa8e21605739bb410695
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937593"
---
# <a name="asynchronous-programming"></a>Асинхронное программирование

В этом разделе рассматривается поддержка асинхронного программирования в поставщике .NET Framework данных для SQL Server (SqlClient), включая улучшения, внесенные в поддержку асинхронного программирования, представленного в .NET Framework 4,5.

## <a name="legacy-asynchronous-programming"></a>Асинхронное программирование прежних версий

До .NET Framework 4,5 асинхронное программирование с помощью SqlClient было выполнено со следующими методами и свойством соединения `Asynchronous Processing=true`.

1. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A?displayProperty=nameWithType>

2. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A?displayProperty=nameWithType>

3. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A?displayProperty=nameWithType>

Эта функция остается в SqlClient в .NET Framework 4,5.

> [!TIP]
> Начиная с .NET Framework 4,5, для этих устаревших методов больше не требуется `Asynchronous Processing=true` в строке подключения.

## <a name="asynchronous-programming-features-added-in-net-framework-45"></a>Функции асинхронного программирования, добавленные в .NET Framework 4,5

Новые функции асинхронного программирования предоставляют простой метод создания асинхронного кода.

Дополнительные сведения о функции асинхронного программирования, представленной в .NET Framework 4,5, см. в следующих статьях:

- [Асинхронное программирование на C#](../../../csharp/async.md)

- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../../visual-basic/programming-guide/concepts/async/index.md)

- [Использование новых асинхронных методов SqlDataReader в .NET 4,5 (часть 1)](https://docs.microsoft.com/archive/blogs/adonet/using-sqldatareaders-new-async-methods-in-net-4-5)

- [Использование новых асинхронных методов SqlDataReader в .NET 4,5 (часть 2)](https://docs.microsoft.com/archive/blogs/adonet/using-sqldatareaders-new-async-methods-in-net-4-5-part-2-examples)

Если пользовательский интерфейс не отвечает или не удается осуществить масштабирование сервера, то, скорее всего, необходимо обеспечить большую поддержку асинхронных средств в коде. Согласно традиционному способу, создание асинхронного кода влечет за собой установку обратного вызова (называемого также продолжением) для представления логики, которая выполняется после завершения асинхронной операции. Это осложняет структуру асинхронного кода по сравнению с синхронным.

Теперь вы можете вызывать асинхронные методы без использования обратных вызовов и без разделения кода на несколько методов и лямбда-выражений.

Модификатор `async` указывает, что метод является асинхронным. При вызове метода `async` происходит возврат задачи. Когда к задаче применяется оператор `await`, текущий метод немедленно завершает работу. После завершения задачи выполнение возобновляется в том же методе.

> [!WARNING]
> Асинхронные вызовы не поддерживаются, если в приложении также используется ключевое слово строки соединения `Context Connection`.

Вызов метода `async` не приводит к выделению каких-либо дополнительных потоков. В конце он может на короткое время использовать существующий поток завершения ввода-вывода.

Следующие методы были добавлены в .NET Framework 4,5 для поддержки асинхронного программирования:

- <xref:System.Data.Common.DbConnection.OpenAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteDbDataReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbDataReader.GetFieldValueAsync%2A>

- <xref:System.Data.Common.DbDataReader.IsDBNullAsync%2A>

- <xref:System.Data.Common.DbDataReader.NextResultAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbDataReader.ReadAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlConnection.OpenAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteXmlReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlDataReader.NextResultAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlDataReader.ReadAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>

 Для поддержки [потоковой передачи SqlClient](sqlclient-streaming-support.md)были добавлены другие асинхронные члены.

> [!TIP]
> Новые асинхронные методы не занимают `Asynchronous Processing=true` в строке подключения.

### <a name="synchronous-to-asynchronous-connection-open"></a>Открытие синхронного и асинхронного соединения

Для использования новой асинхронной функции вы можете обновить существующее приложение. Например, предположим, что приложение имеет синхронный алгоритм соединения и блокирует поток пользовательского интерфейса при каждом его подключении к базе данных, а после подключения приложение вызывает хранимую процедуру, которая указывает другим пользователям БД, кто подключился.

```csharp
using SqlConnection conn = new SqlConnection("…");
{
   conn.Open();
   using (SqlCommand cmd = new SqlCommand("StoredProcedure_Logon", conn))
   {
      cmd.ExecuteNonQuery();
   }
}
```

После преобразования для использования новых асинхронных функций программа должна выглядеть следующим образом:

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {

   static async Task<int> Method(SqlConnection conn, SqlCommand cmd) {
      await conn.OpenAsync();
      await cmd.ExecuteNonQueryAsync();
      return 1;
   }

   public static void Main() {
      using (SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI")) {
         SqlCommand command = new SqlCommand("select top 2 * from orders", conn);

         int result = A.Method(conn, command).Result;

         SqlDataReader reader = command.ExecuteReader();
         while (reader.Read())
            Console.WriteLine(reader[0]);
      }
   }
}
```

### <a name="adding-the-new-asynchronous-feature-in-an-existing-application-mixing-old-and-new-patterns"></a>Добавление новой асинхронной функции в существующее приложение (смешивание старого и нового подходов)

Можно также добавить новые асинхронные возможности (SqlConnection::OpenAsync), не изменяя существующей асинхронной логики. Например, предположим, что приложение использует в настоящее время следующее:

```csharp
AsyncCallback productList = new AsyncCallback(ProductList);
SqlConnection conn = new SqlConnection("…");
conn.Open();
SqlCommand cmd = new SqlCommand("SELECT * FROM [Current Product List]", conn);
IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);
```

К использованию новой асинхронной технологии можно приступить без значительного изменения существующего алгоритма.

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {
   static void ProductList(IAsyncResult result) { }

   public static void Main() {
      // AsyncCallback productList = new AsyncCallback(ProductList);
      // SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");
      // conn.Open();
      // SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);
      // IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);

      AsyncCallback productList = new AsyncCallback(ProductList);
      SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");
      conn.OpenAsync().ContinueWith((task) => {
         SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);
         IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);
      }, TaskContinuationOptions.OnlyOnRanToCompletion);
   }
}
```

### <a name="using-the-base-provider-model-and-the-new-asynchronous-feature"></a>Использование модели базового поставщика и новых асинхронных функциональных возможностей

Может потребоваться создать инструмент, который может подключаться к разным базам данных и выполнять запросы. Можно использовать базовую модель поставщика и новую асинхронную функцию.

Для использования распределенных транзакций необходимо включить на сервере MSDTC. Сведения о включении MSDTC см. в статье [Включение MSDTC на веб-сервере](https://docs.microsoft.com/previous-versions/commerce-server/dd327979(v=cs.90)).

```csharp
using System;
using System.Data.Common;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {
   static async Task PerformDBOperationsUsingProviderModel(string connectionString, string providerName) {
      DbProviderFactory factory = DbProviderFactories.GetFactory(providerName);
      using (DbConnection connection = factory.CreateConnection()) {
         connection.ConnectionString = connectionString;
         await connection.OpenAsync();

         DbCommand command = connection.CreateCommand();
         command.CommandText = "SELECT * FROM AUTHORS";

         using (DbDataReader reader = await command.ExecuteReaderAsync()) {
            while (await reader.ReadAsync()) {
               for (int i = 0; i < reader.FieldCount; i++) {
                  // Process each column as appropriate
                  object obj = await reader.GetFieldValueAsync<object>(i);
                  Console.WriteLine(obj);
               }
            }
         }
      }
   }

   public static void Main()
   {
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();
       // replace these with your own values
       builder.DataSource = "your_server";
       builder.InitialCatalog = "pubs";
       builder.IntegratedSecurity = true;
       string provider = "System.Data.SqlClient";

       Task task = PerformDBOperationsUsingProviderModel(builder.ConnectionString, provider);
       task.Wait();
   }
}
```

### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a>Использование транзакций SQL и новой асинхронной функции

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Program {
   static void Main() {
      string connectionString =
          "Persist Security Info=False;Integrated Security=SSPI;database=Northwind;server=(local)";
      Task task = ExecuteSqlTransaction(connectionString);
      task.Wait();
   }

   static async Task ExecuteSqlTransaction(string connectionString) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         await connection.OpenAsync();

         SqlCommand command = connection.CreateCommand();
         SqlTransaction transaction = null;

         // Start a local transaction.
         transaction = await Task.Run<SqlTransaction>(
             () => connection.BeginTransaction("SampleTransaction")
             );

         // Must assign both transaction object and connection
         // to Command object for a pending local transaction
         command.Connection = connection;
         command.Transaction = transaction;

         try {
            command.CommandText =
                "Insert into Region (RegionID, RegionDescription) VALUES (555, 'Description')";
            await command.ExecuteNonQueryAsync();

            command.CommandText =
                "Insert into Region (RegionID, RegionDescription) VALUES (556, 'Description')";
            await command.ExecuteNonQueryAsync();

            // Attempt to commit the transaction.
            await Task.Run(() => transaction.Commit());
            Console.WriteLine("Both records are written to database.");
         }
         catch (Exception ex) {
            Console.WriteLine("Commit Exception Type: {0}", ex.GetType());
            Console.WriteLine("  Message: {0}", ex.Message);

            // Attempt to roll back the transaction.
            try {
               transaction.Rollback();
            }
            catch (Exception ex2) {
               // This catch block will handle any errors that may have occurred
               // on the server that would cause the rollback to fail, such as
               // a closed connection.
               Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());
               Console.WriteLine("  Message: {0}", ex2.Message);
            }
         }
      }
   }
}
```

### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a>Использование транзакций SQL и новой асинхронной функции

В приложении предприятия можно добавить распределенные транзакции в некоторых сценариях для включения транзакции между несколькими серверами баз данных. Можно использовать пространство имен System.Transactions и включить распределенную транзакцию следующим образом:

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Transactions;

class Program {
   public static void Main()
   {
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();
       // replace these with your own values
       builder.DataSource = "your_server";
       builder.InitialCatalog = "your_data_source";
       builder.IntegratedSecurity = true;

       Task task = ExecuteDistributedTransaction(builder.ConnectionString, builder.ConnectionString);
       task.Wait();
   }

   static async Task ExecuteDistributedTransaction(string connectionString1, string connectionString2) {
      using (SqlConnection connection1 = new SqlConnection(connectionString1))
      using (SqlConnection connection2 = new SqlConnection(connectionString2)) {
         using (CommittableTransaction transaction = new CommittableTransaction()) {
            await connection1.OpenAsync();
            connection1.EnlistTransaction(transaction);

            await connection2.OpenAsync();
            connection2.EnlistTransaction(transaction);

            try {
               SqlCommand command1 = connection1.CreateCommand();
               command1.CommandText = "Insert into RegionTable1 (RegionID, RegionDescription) VALUES (100, 'Description')";
               await command1.ExecuteNonQueryAsync();

               SqlCommand command2 = connection2.CreateCommand();
               command2.CommandText = "Insert into RegionTable2 (RegionID, RegionDescription) VALUES (100, 'Description')";
               await command2.ExecuteNonQueryAsync();

               transaction.Commit();
            }
            catch (Exception ex) {
               Console.WriteLine("Exception Type: {0}", ex.GetType());
               Console.WriteLine("  Message: {0}", ex.Message);

               try {
                  transaction.Rollback();
               }
               catch (Exception ex2) {
                  Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());
                  Console.WriteLine("  Message: {0}", ex2.Message);
               }
            }
         }
      }
   }
}
```

### <a name="cancelling-an-asynchronous-operation"></a>Отмена асинхронной операции

Можно отменить асинхронный запрос с использованием <xref:System.Threading.CancellationToken>.

```csharp
using System;
using System.Data.SqlClient;
using System.Threading;
using System.Threading.Tasks;

namespace Samples {
   class CancellationSample {
      public static void Main(string[] args) {
         CancellationTokenSource source = new CancellationTokenSource();
         source.CancelAfter(2000); // give up after 2 seconds
         try {
            Task result = CancellingAsynchronousOperations(source.Token);
            result.Wait();
         }
         catch (AggregateException exception) {
            if (exception.InnerException is SqlException) {
               Console.WriteLine("Operation canceled");
            }
            else {
               throw;
            }
         }
      }

      static async Task CancellingAsynchronousOperations(CancellationToken cancellationToken) {
         using (SqlConnection connection = new SqlConnection("Server=(local);Integrated Security=true")) {
            await connection.OpenAsync(cancellationToken);

            SqlCommand command = new SqlCommand("WAITFOR DELAY '00:10:00'", connection);
            await command.ExecuteNonQueryAsync(cancellationToken);
         }
      }
   }
}
```

### <a name="asynchronous-operations-with-sqlbulkcopy"></a>Асинхронные операции с SqlBulkCopy

Асинхронные возможности были также добавлены в <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType> с <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>.

```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Data.Odbc;
using System.Data.SqlClient;
using System.Linq;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace SqlBulkCopyAsyncCodeSample {
   class Program {
      static string selectStatement = "SELECT * FROM [pubs].[dbo].[titles]";
      static string createDestTableStatement =
          @"CREATE TABLE {0} (
            [title_id] [varchar](6) NOT NULL,
            [title] [varchar](80) NOT NULL,
            [type] [char](12) NOT NULL,
            [pub_id] [char](4) NULL,
            [price] [money] NULL,
            [advance] [money] NULL,
            [royalty] [int] NULL,
            [ytd_sales] [int] NULL,
            [notes] [varchar](200) NULL,
            [pubdate] [datetime] NOT NULL)";

      // Replace the connection string if needed, for instance to connect to SQL Express: @"Server=(local)\SQLEXPRESS;Database=Demo;Integrated Security=true"
      // static string connectionString = @"Server=(localdb)\V11.0;Database=Demo";
      static string connectionString = @"Server=(local);Database=Demo;Integrated Security=true";

      // static string odbcConnectionString = @"Driver={SQL Server};Server=(localdb)\V11.0;UID=oledb;Pwd=1Password!;Database=Demo";
      static string odbcConnectionString = @"Driver={SQL Server};Server=(local);Database=Demo;Integrated Security=true";

      // static string marsConnectionString = @"Server=(localdb)\V11.0;Database=Demo;MultipleActiveResultSets=true;";
      static string marsConnectionString = @"Server=(local);Database=Demo;MultipleActiveResultSets=true;Integrated Security=true";

      // Replace the Server name with your actual sql azure server name and User ID/Password
      static string azureConnectionString = @"Server=SqlAzure;User ID=myUserID;Password=myPassword;Database=Demo";

      static void Main(string[] args) {
         SynchronousSqlBulkCopy();
         AsyncSqlBulkCopy().Wait();
         MixSyncAsyncSqlBulkCopy().Wait();
         AsyncSqlBulkCopyNotifyAfter().Wait();
         AsyncSqlBulkCopyDataRows().Wait();
         // AsyncSqlBulkCopySqlServerToSqlAzure().Wait();
         // AsyncSqlBulkCopyCancel().Wait();
         AsyncSqlBulkCopyMARS().Wait();
      }

      // 3.1.1 Synchronous bulk copy in .NET 4.5
      private static void SynchronousSqlBulkCopy() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            conn.Open();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               cmd.ExecuteNonQuery();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  bcp.WriteToServer(dt);
               }
            }
         }

      }

      // 3.1.2 Asynchronous bulk copy in .NET 4.5
      private static async Task AsyncSqlBulkCopy() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  await bcp.WriteToServerAsync(dt);
               }
            }
         }
      }

      // 3.2 Add new Async.NET capabilities in an existing application (Mixing synchronous and asynchronous calls)
      private static async Task MixSyncAsyncSqlBulkCopy() {
         using (OdbcConnection odbcconn = new OdbcConnection(odbcConnectionString)) {
            odbcconn.Open();
            using (OdbcCommand odbccmd = new OdbcCommand(selectStatement, odbcconn)) {
               using (OdbcDataReader odbcreader = odbccmd.ExecuteReader()) {
                  using (SqlConnection conn = new SqlConnection(connectionString)) {
                     await conn.OpenAsync();
                     string temptable = "temptable";//"[#" + Guid.NewGuid().ToString("N") + "]";
                     SqlCommand createCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), conn);
                     await createCmd.ExecuteNonQueryAsync();
                     using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                        bcp.DestinationTableName = temptable;
                        await bcp.WriteToServerAsync(odbcreader);
                     }
                  }
               }
            }
         }
      }

      // 3.3 Using the NotifyAfter property
      private static async Task AsyncSqlBulkCopyNotifyAfter() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  bcp.NotifyAfter = 5;
                  bcp.SqlRowsCopied += new SqlRowsCopiedEventHandler(OnSqlRowsCopied);
                  await bcp.WriteToServerAsync(dt);
               }
            }
         }
      }

      private static void OnSqlRowsCopied(object sender, SqlRowsCopiedEventArgs e) {
         Console.WriteLine("Copied {0} so far...", e.RowsCopied);
      }

      // 3.4 Using the new SqlBulkCopy Async.NET capabilities with DataRow[]
      private static async Task AsyncSqlBulkCopyDataRows() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);
               DataRow[] rows = dt.Select();

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  await bcp.WriteToServerAsync(rows);
               }
            }
         }
      }

      // 3.5 Copying data from SQL Server to SQL Azure in .NET 4.5
      //private static async Task AsyncSqlBulkCopySqlServerToSqlAzure() {
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {
      //      await srcConn.OpenAsync();
      //      await destConn.OpenAsync();
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatement, srcConn)) {
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync()) {
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
      //               await destCmd.ExecuteNonQueryAsync();
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
      //                  bcp.DestinationTableName = temptable;
      //                  await bcp.WriteToServerAsync(reader);
      //               }
      //            }
      //         }
      //      }
      //   }
      //}

      // 3.6 Cancelling an Asynchronous Operation to SQL Azure
      //private static async Task AsyncSqlBulkCopyCancel() {
      //   CancellationTokenSource cts = new CancellationTokenSource();
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {
      //      await srcConn.OpenAsync(cts.Token);
      //      await destConn.OpenAsync(cts.Token);
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatement, srcConn)) {
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync(cts.Token)) {
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
      //               await destCmd.ExecuteNonQueryAsync(cts.Token);
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
      //                  bcp.DestinationTableName = temptable;
      //                  await bcp.WriteToServerAsync(reader, cts.Token);
      //                  //Cancel Async SqlBulCopy Operation after 200 ms
      //                  cts.CancelAfter(200);
      //               }
      //            }
      //         }
      //      }
      //   }
      //}

      // 3.7 Using Async.Net and MARS
      private static async Task AsyncSqlBulkCopyMARS() {
         using (SqlConnection marsConn = new SqlConnection(marsConnectionString)) {
            await marsConn.OpenAsync();

            SqlCommand titlesCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[titles]", marsConn);
            SqlCommand authorsCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[authors]", marsConn);
            //With MARS we can have multiple active results sets on the same connection
            using (SqlDataReader titlesReader = await titlesCmd.ExecuteReaderAsync())
            using (SqlDataReader authorsReader = await authorsCmd.ExecuteReaderAsync()) {
               await authorsReader.ReadAsync();

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               using (SqlConnection destConn = new SqlConnection(connectionString)) {
                  await destConn.OpenAsync();
                  using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
                     await destCmd.ExecuteNonQueryAsync();
                     using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
                        bcp.DestinationTableName = temptable;
                        await bcp.WriteToServerAsync(titlesReader);
                     }
                  }
               }
            }
         }
      }
   }
}
```

## <a name="asynchronously-using-multiple-commands-with-mars"></a>Асинхронное использование нескольких команд с помощью режима MARS

В этом примере открывается одно соединение с базой данных **AdventureWorks** . С помощью объекта <xref:System.Data.SqlClient.SqlCommand> создается объект <xref:System.Data.SqlClient.SqlDataReader>. После использования модуля чтения данных открывается второй объект <xref:System.Data.SqlClient.SqlDataReader>, использующий данные из первого объекта <xref:System.Data.SqlClient.SqlDataReader> в качестве входа для предложения WHERE второго модуля чтения данных.

> [!NOTE]
> В следующем примере используется образец базы данных **AdventureWorks**, входящий в состав SQL Server. Представленная в образце кода строка соединения предполагает, что база данных установлена и доступна на локальном компьютере. Измените строку соединения при необходимости в соответствии с вашей средой.

```csharp
using System;
using System.Data;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Class1 {
   static void Main() {
      Task task = MultipleCommands();
      task.Wait();
   }

   static async Task MultipleCommands() {
      // By default, MARS is disabled when connecting to a MARS-enabled.
      // It must be enabled in the connection string.
      string connectionString = GetConnectionString();

      int vendorID;
      SqlDataReader productReader = null;
      string vendorSQL =
        "SELECT VendorId, Name FROM Purchasing.Vendor";
      string productSQL =
        "SELECT Production.Product.Name FROM Production.Product " +
        "INNER JOIN Purchasing.ProductVendor " +
        "ON Production.Product.ProductID = " +
        "Purchasing.ProductVendor.ProductID " +
        "WHERE Purchasing.ProductVendor.VendorID = @VendorId";

      using (SqlConnection awConnection =
        new SqlConnection(connectionString)) {
         SqlCommand vendorCmd = new SqlCommand(vendorSQL, awConnection);
         SqlCommand productCmd =
           new SqlCommand(productSQL, awConnection);

         productCmd.Parameters.Add("@VendorId", SqlDbType.Int);

         await awConnection.OpenAsync();
         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {
            while (await vendorReader.ReadAsync()) {
               Console.WriteLine(vendorReader["Name"]);

               vendorID = (int)vendorReader["VendorId"];

               productCmd.Parameters["@VendorId"].Value = vendorID;
               // The following line of code requires a MARS-enabled connection.
               productReader = await productCmd.ExecuteReaderAsync();
               using (productReader) {
                  while (await productReader.ReadAsync()) {
                     Console.WriteLine("  " +
                       productReader["Name"].ToString());
                  }
               }
            }
         }
      }
   }

   private static string GetConnectionString() {
      // To avoid storing the connection string in your code, you can retrieve it from a configuration file.
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";
   }
}
```

## <a name="asynchronously-reading-and-updating-data-with-mars"></a>Асинхронное чтение и обновление данных с помощью режима MARS

Режим MARS позволяет использовать соединение как для операций чтения, так и для операций языка DML более чем с одной отложенной операцией. Эта возможность избавляет приложение от необходимости решения ошибок занятости соединения. Кроме того, режим MARS позволяет заменить серверные курсоры, которые, как правило, потребляют много ресурсов. Наконец, несколько операций могут осуществляться одновременно в одном соединении, поэтому в них может совместно использоваться один и тот же контекст транзакции, в результате чего отпадает необходимость использования системных хранимых процедур **sp_getbindtoken** и **sp_bindsession**.

Следующее приложение командной строки демонстрирует использование двух модулей <xref:System.Data.SqlClient.SqlDataReader> с тремя объектами <xref:System.Data.SqlClient.SqlCommand> и одним объектом <xref:System.Data.SqlClient.SqlConnection> с включенным режимом MARS. Первый объект команды получает список поставщиков, оценка кредитоспособности которых равна 5. Второй объект команды по идентификатору поставщика из объекта <xref:System.Data.SqlClient.SqlDataReader> загружает второй объект <xref:System.Data.SqlClient.SqlDataReader>, содержащий все продукты данного поставщика. Каждая запись продукта обрабатывается вторым модулем <xref:System.Data.SqlClient.SqlDataReader>. Для определения нового состояния **OnOrderQty** выполняется вычисление. Затем используется третий объект команды для занесения в таблицу **ProductVendor** нового значения. Весь процесс выполняется в пределах одной транзакции, для которой в конце выполняется откат.

> [!NOTE]
> В следующем примере используется образец базы данных **AdventureWorks**, входящий в состав SQL Server. Представленная в образце кода строка соединения предполагает, что база данных установлена и доступна на локальном компьютере. Измените строку соединения при необходимости в соответствии с вашей средой.

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Data;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Program {
   static void Main() {
      Task task = ReadingAndUpdatingData();
      task.Wait();
   }

   static async Task ReadingAndUpdatingData() {
      // By default, MARS is disabled when connecting to a MARS-enabled host.
      // It must be enabled in the connection string.
      string connectionString = GetConnectionString();

      SqlTransaction updateTx = null;
      SqlCommand vendorCmd = null;
      SqlCommand prodVendCmd = null;
      SqlCommand updateCmd = null;

      SqlDataReader prodVendReader = null;

      int vendorID = 0;
      int productID = 0;
      int minOrderQty = 0;
      int maxOrderQty = 0;
      int onOrderQty = 0;
      int recordsUpdated = 0;
      int totalRecordsUpdated = 0;

      string vendorSQL =
          "SELECT VendorID, Name FROM Purchasing.Vendor " +
          "WHERE CreditRating = 5";
      string prodVendSQL =
          "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " +
          "FROM Purchasing.ProductVendor " +
          "WHERE VendorID = @VendorID";
      string updateSQL =
          "UPDATE Purchasing.ProductVendor " +
          "SET OnOrderQty = @OrderQty " +
          "WHERE ProductID = @ProductID AND VendorID = @VendorID";

      using (SqlConnection awConnection =
        new SqlConnection(connectionString)) {
         await awConnection.OpenAsync();
         updateTx = await Task.Run(() => awConnection.BeginTransaction());

         vendorCmd = new SqlCommand(vendorSQL, awConnection);
         vendorCmd.Transaction = updateTx;

         prodVendCmd = new SqlCommand(prodVendSQL, awConnection);
         prodVendCmd.Transaction = updateTx;
         prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int);

         updateCmd = new SqlCommand(updateSQL, awConnection);
         updateCmd.Transaction = updateTx;
         updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int);
         updateCmd.Parameters.Add("@ProductID", SqlDbType.Int);
         updateCmd.Parameters.Add("@VendorID", SqlDbType.Int);

         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {
            while (await vendorReader.ReadAsync()) {
               Console.WriteLine(vendorReader["Name"]);

               vendorID = (int)vendorReader["VendorID"];
               prodVendCmd.Parameters["@VendorID"].Value = vendorID;
               prodVendReader = await prodVendCmd.ExecuteReaderAsync();

               using (prodVendReader) {
                  while (await prodVendReader.ReadAsync()) {
                     productID = (int)prodVendReader["ProductID"];

                     if (prodVendReader["OnOrderQty"] == DBNull.Value) {
                        minOrderQty = (int)prodVendReader["MinOrderQty"];
                        onOrderQty = minOrderQty;
                     }
                     else {
                        maxOrderQty = (int)prodVendReader["MaxOrderQty"];
                        onOrderQty = (int)(maxOrderQty / 2);
                     }

                     updateCmd.Parameters["@OrderQty"].Value = onOrderQty;
                     updateCmd.Parameters["@ProductID"].Value = productID;
                     updateCmd.Parameters["@VendorID"].Value = vendorID;

                     recordsUpdated = await updateCmd.ExecuteNonQueryAsync();
                     totalRecordsUpdated += recordsUpdated;
                  }
               }
            }
         }
         Console.WriteLine("Total Records Updated: ", totalRecordsUpdated.ToString());
         await Task.Run(() => updateTx.Rollback());
         Console.WriteLine("Transaction Rolled Back");
      }
   }

   private static string GetConnectionString() {
      // To avoid storing the connection string in your code, you can retrieve it from a configuration file.
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";
   }
}
```

## <a name="see-also"></a>См. также:

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
