---
title: Примеры кода ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 93cc0cf34d2bba23ff0938c8c13d7343d665192d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773611"
---
# <a name="adonet-code-examples"></a>Примеры кода ADO.NET
В листингах кода, приведенных в данном разделе, демонстрируется извлечение данных из базы данных с помощью следующих технологий ADO.NET.

- Поставщики данных ADO.NET:

  - [SqlClient](#sqlclient) (`System.Data.SqlClient`)

  - [OleDb](#oledb) (`System.Data.OleDb`)

  - [ODBC](#odbc) (`System.Data.Odbc`)

  - [OracleClient](#oracleclient) (`System.Data.OracleClient`)

- Платформа ADO.NET Entity Framework:

  - [LINQ to Entities](#linq-to-entities)

  - [Типизированный запрос ObjectQuery](#typed-objectquery)

  - [EntityClient](#entityclient) (`System.Data.EntityClient`)

- [LINQ to SQL](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a>Примеры использования поставщика данных ADO.NET
В приведенных ниже листингах кода демонстрируется извлечение данных из базы данных с помощью поставщиков данных ADO.NET. Данные возвращаются в классе `DataReader`. Дополнительные сведения см. в разделе [получение данных с помощью объекта DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).

### <a name="sqlclient"></a>SqlClient
В этом примере предполагается, что можно соединиться с `Northwind` образца базы данных на сервере Microsoft SQL Server. Код создает команду <xref:System.Data.SqlClient.SqlCommand> для выборки строк из таблицы Products, к которой добавляется параметр <xref:System.Data.SqlClient.SqlParameter>, ограничивающий результат строками, для которых значение UnitPrice превышает указанное значение параметра, в данном случае 5. <xref:System.Data.SqlClient.SqlConnection> Открыт внутри `using` блок, который гарантирует, что ресурсы закрытие и освобождение при выходе. Команда выполняется с помощью объекта <xref:System.Data.SqlClient.SqlDataReader>, а результаты выводятся в окно консоли.

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a>OleDb
Данный образец кода предполагает возможность подключения к образцу базы данных Northwind из Microsoft Access. Код создает команду <xref:System.Data.OleDb.OleDbCommand> для выборки строк из таблицы Products, к которой добавляется параметр <xref:System.Data.OleDb.OleDbParameter>, ограничивающий результат строками, для которых значение UnitPrice превышает указанное значение параметра, в данном случае 5. Соединение <xref:System.Data.OleDb.OleDbConnection> открывается в блоке `using`, что гарантирует закрытие и освобождение ресурсов после завершения работы кода. Команда выполняется с помощью объекта <xref:System.Data.OleDb.OleDbDataReader>, а результаты выводятся в окно консоли.

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a>Odbc
Данный образец кода предполагает возможность подключения к образцу базы данных Northwind из Microsoft Access. Код создает команду <xref:System.Data.Odbc.OdbcCommand> для выборки строк из таблицы Products, к которой добавляется параметр <xref:System.Data.Odbc.OdbcParameter>, ограничивающий результат строками, для которых значение UnitPrice превышает указанное значение параметра, в данном случае 5. <xref:System.Data.Odbc.OdbcConnection> Открыт внутри `using` блок, который гарантирует, что ресурсы закрытие и освобождение при выходе. Команда выполняется с помощью объекта <xref:System.Data.Odbc.OdbcDataReader>, а результаты выводятся в окно консоли.

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)] 
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)] 

### <a name="oracleclient"></a>OracleClient
Данный пример кода предполагает наличие соединения с базой данных DEMO.CUSTOMER на сервере Oracle. Кроме того, необходимо добавить ссылку на файл System.Data.OracleClient.dll. Этот код возвращает данные в объекте <xref:System.Data.OracleClient.OracleDataReader>.

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a>Примеры Entity Framework
В приведенных ниже листингах кода демонстрируется извлечение данных из источника данных путем выполнения запросов к сущностям модели EDM. В этих примерах используется [модель Northwind](https://msdn.microsoft.com/74521f8c-e974-48cb-8858-c08deff52638). Дополнительные сведения см. в разделе [Обзор Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).

### <a name="linq-to-entities"></a>LINQ to Entities
В данном примере кода запрос LINQ используется для возврата данных в виде объектов Categories, которые проецируются в анонимный тип, содержащий только свойства CategoryID и CategoryName. Дополнительные сведения см. в разделе [LINQ to Entities Обзор](https://msdn.microsoft.com/86d87a27-c17a-45ac-b28d-72c8500333c6).

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

Imports System
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

### <a name="typed-objectquery"></a>Типизированный запрос ObjectQuery
В данном примере кода для возврата данных в виде объектов Categories используется запрос <xref:System.Data.Objects.ObjectQuery%601>. Дополнительные сведения см. в разделе [запросы объектов](https://msdn.microsoft.com/0768033c-876f-471d-85d5-264884349276).

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

Imports System
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

### <a name="entityclient"></a>EntityClient
В данном примере кода для выполнения запроса Entity SQL используется команда <xref:System.Data.EntityClient.EntityCommand>. Этот запрос возвращает список записей, представляющих экземпляры типа сущности Categories. Для доступа к записям данных в результирующем наборе используется объект <xref:System.Data.EntityClient.EntityDataReader>. Дополнительные сведения см. в разделе [поставщик EntityClient для Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).

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

Imports System
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

## <a name="linq-to-sql"></a>LINQ to SQL
В данном примере кода запрос LINQ используется для возврата данных в виде объектов Categories, которые проецируются в анонимный тип, содержащий только свойства CategoryID и CategoryName. Этот пример основан на контексте данных Northwind. Дополнительные сведения см. в разделе [Начало работы](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).

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

Imports System
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

## <a name="see-also"></a>См. также
 [Общие сведения об ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Создание приложений для работы с данными](https://msdn.microsoft.com/library/ab334d5f-4f49-4346-bce0-3325d6130b3e)  
 [Запрос модели EDM (задачи Entity Framework)](https://msdn.microsoft.com/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)  
 [Практическое: выполнение запроса, возвращающего объекты анонимного типа](https://msdn.microsoft.com/3b264025-e911-4d73-90ce-992d2b9d189d)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)  
