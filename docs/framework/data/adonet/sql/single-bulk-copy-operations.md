---
title: "Отдельные операции массового копирования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 961981fcdf9709a336d76df99c8f65448e76b98a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="5ccbe-102">Отдельные операции массового копирования</span><span class="sxs-lookup"><span data-stu-id="5ccbe-102">Single Bulk Copy Operations</span></span>
<span data-ttu-id="5ccbe-103">Самый простой способ выполнения операции массового копирования в SQL Server заключается в выполнении одной операции для базы данных.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-103">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="5ccbe-104">По умолчанию операция массового копирования выполняется как изолированная, без использования транзакции и без возможности отката.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-104">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ccbe-105">Если в случае ошибки необходимо откатить все или часть массового копирования, можно либо воспользоваться транзакцией под управлением <xref:System.Data.SqlClient.SqlBulkCopy>, либо выполнить операцию массового копирования в рамках существующей транзакции.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-105">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="5ccbe-106">**SqlBulkCopy** также будет работать с <xref:System.Transactions> Если соединение прикреплено (явно или неявно) в **System.Transactions** транзакции.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-106">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>  
>   
>  <span data-ttu-id="5ccbe-107">Дополнительные сведения см. в разделе [транзакции и операции массового копирования](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5ccbe-107">For more information, see [Transaction and Bulk Copy Operations](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="5ccbe-108">Далее приведены общие шаги по выполнению операции массового копирования.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-108">The general steps for performing a bulk copy operation are as follows:</span></span>  
  
1.  <span data-ttu-id="5ccbe-109">Подключитесь к серверу-источнику и получите данные для копирования.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-109">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="5ccbe-110">Если данные можно получить из объекта <xref:System.Data.IDataReader> или <xref:System.Data.DataTable>, они также могут поступать из других источников.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-110">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>  
  
2.  <span data-ttu-id="5ccbe-111">Подключение к серверу назначения (если не требуется **SqlBulkCopy** для установления соединения автоматически).</span><span class="sxs-lookup"><span data-stu-id="5ccbe-111">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>  
  
3.  <span data-ttu-id="5ccbe-112">Создайте объект <xref:System.Data.SqlClient.SqlBulkCopy>, задав необходимые свойства.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-112">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>  
  
4.  <span data-ttu-id="5ccbe-113">Задать **DestinationTableName** свойство, указывающее целевую таблицу для массовой операции вставки.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-113">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>  
  
5.  <span data-ttu-id="5ccbe-114">Вызовите один из **WriteToServer** методы.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-114">Call one of the **WriteToServer** methods.</span></span>  
  
6.  <span data-ttu-id="5ccbe-115">При необходимости обновите свойства и вызвать метод **WriteToServer** еще раз при необходимости.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-115">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>  
  
7.  <span data-ttu-id="5ccbe-116">Вызовите метод <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A> или заключите операции массового копирования в оболочку из инструкции `Using`.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-116">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5ccbe-117">Рекомендуется, чтобы типы данных исходного и целевого столбца были одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-117">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="5ccbe-118">Если типы данных не совпадают, **SqlBulkCopy** попытается преобразовать каждое исходное значение в целевой тип данных, с помощью правил, применяемых методом <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-118">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="5ccbe-119">Преобразования могут ухудшать производительность, а также приводить к непредвиденным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-119">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="5ccbe-120">Например, в большинстве случаев тип данных `Double` можно преобразовать в тип данных `Decimal`, однако иногда это невозможно.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-120">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ccbe-121">Пример</span><span class="sxs-lookup"><span data-stu-id="5ccbe-121">Example</span></span>  
 <span data-ttu-id="5ccbe-122">Следующее приложение командной строки демонстрирует, как загружать данные при помощи класса <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-122">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="5ccbe-123">В этом примере <xref:System.Data.SqlClient.SqlDataReader> используется для копирования данных из **Production.Product** в таблицу [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] **AdventureWorks** базы данных в аналогичную таблицу в той же базе данных.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-123">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]**AdventureWorks** database to a similar table in the same database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ccbe-124">Этот образец не запустится, пока вы не создадите рабочие таблицы, как описано в [пример настройки массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="5ccbe-124">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="5ccbe-125">Данный код предназначен для демонстрации синтаксиса использования **SqlBulkCopy** только.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-125">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="5ccbe-126">Если исходная и целевая таблицы расположены в одном и том же экземпляре SQL Server, легче и быстрее использовать для копирования данных инструкцию `INSERT … SELECT` языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-126">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="5ccbe-127">Выполнение операции массового копирования при помощи Transact-SQL и класса команды</span><span class="sxs-lookup"><span data-stu-id="5ccbe-127">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>  
 <span data-ttu-id="5ccbe-128">В следующем примере иллюстрируется, как применять метод <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> для выполнения инструкции BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-128">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ccbe-129">Путь к файлу для источника данных указан относительно сервера.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-129">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="5ccbe-130">Чтобы операция массового копирования была успешной, процесс сервера должен иметь доступ к этому пути.</span><span class="sxs-lookup"><span data-stu-id="5ccbe-130">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ccbe-131">См. также</span><span class="sxs-lookup"><span data-stu-id="5ccbe-131">See Also</span></span>  
 [<span data-ttu-id="5ccbe-132">Операции массового копирования в SQL Server</span><span class="sxs-lookup"><span data-stu-id="5ccbe-132">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="5ccbe-133">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5ccbe-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
