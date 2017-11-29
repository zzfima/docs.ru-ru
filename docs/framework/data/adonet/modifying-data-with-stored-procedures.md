---
title: "Изменение данных с помощью хранимых процедур"
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
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1f8f0c37e5ac84d878f1d443d2bcc1e8ded099a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="38393-102">Изменение данных с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="38393-102">Modifying Data with Stored Procedures</span></span>
<span data-ttu-id="38393-103">Хранимые процедуры могут принимать данные в виде входных параметров и возвращать их в виде выходных параметров, результирующих наборов или возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="38393-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="38393-104">Образец, приведенный ниже, показывает, как ADO.NET отправляет и получает входные и выходные параметры, а также возвращаемые значения.</span><span class="sxs-lookup"><span data-stu-id="38393-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="38393-105">Пример добавляет в таблицу новую запись, где столбец первичного ключа является столбцом идентификаторов в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="38393-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38393-106">При использовании хранимых процедур SQL Server для изменения или удаления данных с помощью <xref:System.Data.SqlClient.SqlDataAdapter> убедитесь, что в определении хранимой процедуры не указана инструкция SET NOCOUNT ON.</span><span class="sxs-lookup"><span data-stu-id="38393-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="38393-107">В таком случае возвращается число затронутых строк, равное нулю, что `DataAdapter` интерпретирует как конфликт параллелизма.</span><span class="sxs-lookup"><span data-stu-id="38393-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="38393-108">Это событие вызовет исключение <xref:System.Data.DBConcurrencyException>.</span><span class="sxs-lookup"><span data-stu-id="38393-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38393-109">Пример</span><span class="sxs-lookup"><span data-stu-id="38393-109">Example</span></span>  
 <span data-ttu-id="38393-110">Образец использует следующую хранимую процедуру для вставки новой категории в **Northwind** **категории** таблицы.</span><span class="sxs-lookup"><span data-stu-id="38393-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="38393-111">Хранимая процедура принимает значение **CategoryName** столбца в качестве входного параметра и использует SCOPE_IDENTITY() функции для получения нового значения поля идентификатора **CategoryID**и возвращает его в выходном параметре.</span><span class="sxs-lookup"><span data-stu-id="38393-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="38393-112">Инструкция RETURN использует @@ROWCOUNT функция возвращает количество вставленных строк.</span><span class="sxs-lookup"><span data-stu-id="38393-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```  
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="38393-113">Следующий пример кода использует хранимую процедуру `InsertCategory`, показанную выше, в качестве источника для свойства <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> класса <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="38393-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="38393-114">Выходной параметр `@Identity` будет отражен в наборе данных <xref:System.Data.DataSet> после вставки записи в базу данных при вызове метода `Update` объекта <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="38393-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="38393-115">Код также получает возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="38393-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38393-116">При использовании <xref:System.Data.OleDb.OleDbDataAdapter>, необходимо указать параметры с <xref:System.Data.ParameterDirection> из **ReturnValue** до указания других параметров.</span><span class="sxs-lookup"><span data-stu-id="38393-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="38393-117">См. также</span><span class="sxs-lookup"><span data-stu-id="38393-117">See Also</span></span>  
 [<span data-ttu-id="38393-118">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="38393-118">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="38393-119">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="38393-119">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="38393-120">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="38393-120">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [<span data-ttu-id="38393-121">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="38393-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
