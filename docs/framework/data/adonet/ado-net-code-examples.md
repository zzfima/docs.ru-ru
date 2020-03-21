---
title: Примеры кода
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 6e0c34e1db50030c78db295f26fcc25b431d3dde
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111807"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="cc505-102">ADO.NET примеры кода</span><span class="sxs-lookup"><span data-stu-id="cc505-102">ADO.NET code examples</span></span>

<span data-ttu-id="cc505-103">В объявлениях кода на этой странице показано, как получить данные из базы данных с помощью следующих ADO.NET технологий:</span><span class="sxs-lookup"><span data-stu-id="cc505-103">The code listings on this page demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="cc505-104">Поставщики данных ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="cc505-104">ADO.NET data providers:</span></span>

  - <span data-ttu-id="cc505-105">[SqlКлиент](#sqlclient) `System.Data.SqlClient`()</span><span class="sxs-lookup"><span data-stu-id="cc505-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="cc505-106">[ОлеДб](#oledb) `System.Data.OleDb`( )</span><span class="sxs-lookup"><span data-stu-id="cc505-106">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="cc505-107">[Одбк](#odbc) (`System.Data.Odbc`)</span><span class="sxs-lookup"><span data-stu-id="cc505-107">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="cc505-108">[OracleClient](#oracleclient) `System.Data.OracleClient`( )</span><span class="sxs-lookup"><span data-stu-id="cc505-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="cc505-109">Платформа ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="cc505-109">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="cc505-110">ЛИНЗ для юридических лиц</span><span class="sxs-lookup"><span data-stu-id="cc505-110">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="cc505-111">Типизированный запрос ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="cc505-111">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="cc505-112">[СущностьКлиент](#entityclient) ()`System.Data.EntityClient`</span><span class="sxs-lookup"><span data-stu-id="cc505-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="cc505-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cc505-113">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="cc505-114">примеры ADO.NET поставщика данных</span><span class="sxs-lookup"><span data-stu-id="cc505-114">ADO.NET data provider examples</span></span>
<span data-ttu-id="cc505-115">В приведенных ниже листингах кода демонстрируется извлечение данных из базы данных с помощью поставщиков данных ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="cc505-115">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="cc505-116">Данные возвращаются в классе `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="cc505-116">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="cc505-117">Для получения дополнительной [информации см.](retrieving-data-using-a-datareader.md)</span><span class="sxs-lookup"><span data-stu-id="cc505-117">For more information, see [Retrieving Data Using a DataReader](retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="cc505-118">SqlClient</span><span class="sxs-lookup"><span data-stu-id="cc505-118">SqlClient</span></span>
<span data-ttu-id="cc505-119">Код в этом примере предполагает, что `Northwind` вы можете подключиться к выборочной базе данных на сервере Microsoft S'L.</span><span class="sxs-lookup"><span data-stu-id="cc505-119">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="cc505-120">Код создает команду <xref:System.Data.SqlClient.SqlCommand> для выборки строк из таблицы Products, к которой добавляется параметр <xref:System.Data.SqlClient.SqlParameter>, ограничивающий результат строками, для которых значение UnitPrice превышает указанное значение параметра, в данном случае 5.</span><span class="sxs-lookup"><span data-stu-id="cc505-120">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="cc505-121">Открывается <xref:System.Data.SqlClient.SqlConnection> внутри `using` блока, что гарантирует, что ресурсы будут закрыты и удалены при выходе кода.</span><span class="sxs-lookup"><span data-stu-id="cc505-121">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="cc505-122">Команда выполняется с помощью объекта <xref:System.Data.SqlClient.SqlDataReader>, а результаты выводятся в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="cc505-122">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="cc505-123">OleDb</span><span class="sxs-lookup"><span data-stu-id="cc505-123">OleDb</span></span>
<span data-ttu-id="cc505-124">Данный образец кода предполагает возможность подключения к образцу базы данных Northwind из Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="cc505-124">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="cc505-125">Код создает команду <xref:System.Data.OleDb.OleDbCommand> для выборки строк из таблицы Products, к которой добавляется параметр <xref:System.Data.OleDb.OleDbParameter>, ограничивающий результат строками, для которых значение UnitPrice превышает указанное значение параметра, в данном случае 5.</span><span class="sxs-lookup"><span data-stu-id="cc505-125">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="cc505-126">Соединение <xref:System.Data.OleDb.OleDbConnection> открывается в блоке `using`, что гарантирует закрытие и освобождение ресурсов после завершения работы кода.</span><span class="sxs-lookup"><span data-stu-id="cc505-126">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="cc505-127">Команда выполняется с помощью объекта <xref:System.Data.OleDb.OleDbDataReader>, а результаты выводятся в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="cc505-127">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="cc505-128">ODBC</span><span class="sxs-lookup"><span data-stu-id="cc505-128">Odbc</span></span>
<span data-ttu-id="cc505-129">Данный образец кода предполагает возможность подключения к образцу базы данных Northwind из Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="cc505-129">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="cc505-130">Код создает команду <xref:System.Data.Odbc.OdbcCommand> для выборки строк из таблицы Products, к которой добавляется параметр <xref:System.Data.Odbc.OdbcParameter>, ограничивающий результат строками, для которых значение UnitPrice превышает указанное значение параметра, в данном случае 5.</span><span class="sxs-lookup"><span data-stu-id="cc505-130">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="cc505-131">Открывается <xref:System.Data.Odbc.OdbcConnection> внутри `using` блока, что гарантирует, что ресурсы будут закрыты и удалены при выходе кода.</span><span class="sxs-lookup"><span data-stu-id="cc505-131">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="cc505-132">Команда выполняется с помощью объекта <xref:System.Data.Odbc.OdbcDataReader>, а результаты выводятся в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="cc505-132">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)]
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)]

### <a name="oracleclient"></a><span data-ttu-id="cc505-133">OracleClient</span><span class="sxs-lookup"><span data-stu-id="cc505-133">OracleClient</span></span>
<span data-ttu-id="cc505-134">Данный пример кода предполагает наличие соединения с базой данных DEMO.CUSTOMER на сервере Oracle.</span><span class="sxs-lookup"><span data-stu-id="cc505-134">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="cc505-135">Кроме того, необходимо добавить ссылку на файл System.Data.OracleClient.dll.</span><span class="sxs-lookup"><span data-stu-id="cc505-135">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="cc505-136">Этот код возвращает данные в объекте <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="cc505-136">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="cc505-137">Примеры рамочных систем</span><span class="sxs-lookup"><span data-stu-id="cc505-137">Entity Framework examples</span></span>
<span data-ttu-id="cc505-138">В приведенных ниже листингах кода демонстрируется извлечение данных из источника данных путем выполнения запросов к сущностям модели EDM.</span><span class="sxs-lookup"><span data-stu-id="cc505-138">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="cc505-139">В этих примерах используется модель, основанная на базе данных образца Northwind.</span><span class="sxs-lookup"><span data-stu-id="cc505-139">These examples use a model based on the Northwind sample database.</span></span> <span data-ttu-id="cc505-140">Для получения дополнительной информации [Entity Framework Overview](./ef/overview.md)о рамочной базе сущности см.</span><span class="sxs-lookup"><span data-stu-id="cc505-140">For more information about Entity Framework, see [Entity Framework Overview](./ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="cc505-141">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="cc505-141">LINQ to Entities</span></span>
<span data-ttu-id="cc505-142">В данном примере кода запрос LINQ используется для возврата данных в виде объектов Categories, которые проецируются в анонимный тип, содержащий только свойства CategoryID и CategoryName.</span><span class="sxs-lookup"><span data-stu-id="cc505-142">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="cc505-143">Для получения дополнительной [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md)информации см.</span><span class="sxs-lookup"><span data-stu-id="cc505-143">For more information, see [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md).</span></span>

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a><span data-ttu-id="cc505-144">Типизированный запрос ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="cc505-144">Typed ObjectQuery</span></span>
<span data-ttu-id="cc505-145">В данном примере кода для возврата данных в виде объектов Categories используется запрос <xref:System.Data.Objects.ObjectQuery%601>.</span><span class="sxs-lookup"><span data-stu-id="cc505-145">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="cc505-146">Для получения дополнительной [информации см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cc505-146">For more information, see [Object Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span></span>

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a><span data-ttu-id="cc505-147">EntityClient</span><span class="sxs-lookup"><span data-stu-id="cc505-147">EntityClient</span></span>
<span data-ttu-id="cc505-148">В данном примере кода для выполнения запроса Entity SQL используется команда <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="cc505-148">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="cc505-149">Этот запрос возвращает список записей, представляющих экземпляры типа сущности Categories.</span><span class="sxs-lookup"><span data-stu-id="cc505-149">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="cc505-150">Для доступа к записям данных в результирующем наборе используется объект <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="cc505-150">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="cc505-151">Для получения дополнительной [EntityClient Provider for the Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md)информации см.</span><span class="sxs-lookup"><span data-stu-id="cc505-151">For more information, see [EntityClient Provider for the Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr =
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

## <a name="linq-to-sql"></a><span data-ttu-id="cc505-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cc505-152">LINQ to SQL</span></span>
<span data-ttu-id="cc505-153">В данном примере кода запрос LINQ используется для возврата данных в виде объектов Categories, которые проецируются в анонимный тип, содержащий только свойства CategoryID и CategoryName.</span><span class="sxs-lookup"><span data-stu-id="cc505-153">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="cc505-154">Этот пример основан на контексте данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="cc505-154">This example is based on the Northwind data context.</span></span> <span data-ttu-id="cc505-155">Для получения дополнительной информации, [см.](./sql/linq/getting-started.md)</span><span class="sxs-lookup"><span data-stu-id="cc505-155">For more information, see [Getting Started](./sql/linq/getting-started.md).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="cc505-156">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc505-156">See also</span></span>

- [<span data-ttu-id="cc505-157">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cc505-157">ADO.NET Overview</span></span>](ado-net-overview.md)
- [<span data-ttu-id="cc505-158">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cc505-158">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- <span data-ttu-id="cc505-159">[Создание приложений для работы с данными](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="cc505-159">[Creating Data Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span></span>
- <span data-ttu-id="cc505-160">[Запросы к модели EDM (задачи Entity Framework)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cc505-160">[Querying an Entity Data Model (Entity Framework Tasks)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span></span>
- <span data-ttu-id="cc505-161">[Практическое руководство. Выполнение запроса, возвращающего объекты анонимного типа](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cc505-161">[How to: Execute a Query that Returns Anonymous Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>
