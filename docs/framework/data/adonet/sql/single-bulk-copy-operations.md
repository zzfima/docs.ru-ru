---
title: "Отдельные операции массового копирования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Отдельные операции массового копирования
Самый простой способ выполнения операции массового копирования в SQL Server заключается в выполнении одной операции для базы данных.  По умолчанию операция массового копирования выполняется как изолированная, без использования транзакции и без возможности отката.  
  
> [!NOTE]
>  Если в случае ошибки необходимо откатить все или часть массового копирования, можно либо воспользоваться транзакцией под управлением <xref:System.Data.SqlClient.SqlBulkCopy>, либо выполнить операцию массового копирования в рамках существующей транзакции.  Объект **SqlBulkCopy** также будет работать с <xref:System.Transactions>, если это соединение прикреплено \(явно или неявно\) к транзакции **System.Transactions**.  
>   
>  Для получения дополнительной информации см. [Операции транзакций и массового копирования](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).  
  
 Далее приведены общие шаги по выполнению операции массового копирования.  
  
1.  Подключитесь к серверу\-источнику и получите данные для копирования.  Если данные можно получить из объекта <xref:System.Data.IDataReader> или <xref:System.Data.DataTable>, они также могут поступать из других источников.  
  
2.  Подключитесь к целевому серверу \(если только не требуется, чтобы объект **SqlBulkCopy** сам установил соединение\).  
  
3.  Создайте объект <xref:System.Data.SqlClient.SqlBulkCopy>, задав необходимые свойства.  
  
4.  Задайте свойство **DestinationTableName**, чтобы указать целевую таблицу для операции массовой вставки.  
  
5.  Вызовите один из методов **WriteToServer**.  
  
6.  Кроме того, если это необходимо, можно обновить свойства и вызвать метод **WriteToServer**.  
  
7.  Вызовите метод <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A> или заключите операции массового копирования в оболочку из инструкции `Using`.  
  
> [!CAUTION]
>  Рекомендуется, чтобы типы данных исходного и целевого столбца были одинаковыми.  Если типы данных разные, объект **SqlBulkCopy** попытается преобразовать каждое исходное значение в целевой тип данных с использованием правил, применяемых методом <xref:System.Data.SqlClient.SqlParameter.Value%2A>.  Преобразования могут ухудшать производительность, а также приводить к непредвиденным ошибкам.  Например, в большинстве случаев тип данных `Double` можно преобразовать в тип данных `Decimal`, однако иногда это невозможно.  
  
## Пример  
 Следующее приложение командной строки демонстрирует, как загружать данные при помощи класса <xref:System.Data.SqlClient.SqlBulkCopy>.  В этом примере объект <xref:System.Data.SqlClient.SqlDataReader> используется, чтобы скопировать данные из таблицы **Production.Product** в базе данных [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] **AdventureWorks** в такую же таблицу в этой же базе данных.  
  
> [!IMPORTANT]
>  Этот образец не запустится до тех пор, пока не будут созданы рабочие таблицы, описанные в разделе [Подготовка к выполнению примера массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).  Данный код предназначен только для демонстрации синтаксиса использования **SqlBulkCopy**.  Если исходная и целевая таблицы расположены в одном и том же экземпляре SQL Server, легче и быстрее использовать для копирования данных инструкцию `INSERT … SELECT` языка Transact\-SQL.  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## Выполнение операции массового копирования при помощи Transact\-SQL и класса команды  
 В следующем примере иллюстрируется, как применять метод <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> для выполнения инструкции BULK INSERT.  
  
> [!NOTE]
>  Путь к файлу для источника данных указан относительно сервера.  Чтобы операция массового копирования была успешной, процесс сервера должен иметь доступ к этому пути.  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## См. также  
 [Операции массового копирования в SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)