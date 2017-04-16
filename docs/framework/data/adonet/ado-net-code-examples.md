---
title: "Примеры кода ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Примеры кода ADO.NET
В листингах кода, приведенных в данном разделе, демонстрируется извлечение данных из базы данных с помощью следующих технологий ADO.NET.  
  
-   Поставщики данных ADO.NET:  
  
    -   [SqlClient](#_SqlClient) (`System.Data.SqlClient`)  
  
    -   [OleDb](#_OleDb) (`System.Data.OleDb`)  
  
    -   [Odbc](#_Odbc) (`System.Data.Odbc`)  
  
    -   [OracleClient](#_OracleClient) (`System.Data.OracleClient`)  
  
-   Платформа ADO.NET Entity Framework:  
  
    -   [LINQ to Entities](#_LINQ)  
  
    -   [Типизированный запрос ObjectQuery](#_QBM)  
  
    -   [EntityClient](#_EntityClient) (`System.Data.EntityClient`)  
  
-   [LINQ to SQL](#_LINQ2SQL)  
  
## <a name="adonet-data-provider-examples"></a>Примеры использования поставщика данных ADO.NET  
 В приведенных ниже листингах кода демонстрируется извлечение данных из базы данных с помощью поставщиков данных ADO.NET. Данные возвращаются в классе `DataReader`. Дополнительные сведения см. в разделе [получение данных с помощью объекта DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).  
  
<a name="_SqlClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 Данный образец кода предполагает возможность подключения к образцу базы данных `Northwind` из Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]. Код создает <xref:System.Data.SqlClient.SqlCommand> для выборки строк из таблицы Products, добавление <xref:System.Data.SqlClient.SqlParameter> , ограничивающий результаты строками с значение UnitPrice превышает указанное значение параметра, в данном случае 5. <xref:System.Data.SqlClient.SqlConnection> открывается в `using` блок, который гарантирует закрыто и удаляется при выходе ресурсов. Команда выполняется с помощью <xref:System.Data.SqlClient.SqlDataReader>и отображает результаты в окне консоли.  
  
  [DataWorks SampleApp.SqlClient#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient#1)]  
  
 [[В начало]](#_TOP)  
  
<a name="_OleDb"></a>   
### <a name="oledb"></a>OleDb  
 Данный образец кода предполагает возможность подключения к образцу базы данных Northwind из Microsoft Access. Код создает <xref:System.Data.OleDb.OleDbCommand> для выборки строк из таблицы Products, добавление <xref:System.Data.OleDb.OleDbParameter> , ограничивающий результаты строками с значение UnitPrice превышает указанное значение параметра, в данном случае 5. <xref:System.Data.OleDb.OleDbConnection> открывается в `using` блок, который гарантирует закрыто и удаляется при выходе ресурсов. Команда выполняется с помощью <xref:System.Data.OleDb.OleDbDataReader>и отображает результаты в окне консоли.  
  
  [DataWorks SampleApp.OleDb#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb#1)]  
  
 [[В начало]](#_TOP)  
  
<a name="_Odbc"></a>   
### <a name="odbc"></a>Odbc  
 Данный образец кода предполагает возможность подключения к образцу базы данных Northwind из Microsoft Access. Код создает <xref:System.Data.Odbc.OdbcCommand> для выборки строк из таблицы Products, добавление <xref:System.Data.Odbc.OdbcParameter> , ограничивающий результаты строками с значение UnitPrice превышает указанное значение параметра, в данном случае 5. <xref:System.Data.Odbc.OdbcConnection> открывается в `using` блок, который гарантирует закрыто и удаляется при выходе ресурсов. Выполняет команду с помощью <xref:System.Data.Odbc.OdbcDataReader>и отображает результаты в окне консоли.  
  
<!-- TODO: review snippet reference  [!CODE [DataWorksSampleApp.Odbc#1](DataWorksSampleApp.Odbc#1)]  -->  
  
 [[В начало]](#_TOP)  
  
<a name="_OracleClient"></a>   
### <a name="oracleclient"></a>OracleClient  
 Данный пример кода предполагает наличие соединения с базой данных DEMO.CUSTOMER на сервере Oracle. Кроме того, необходимо добавить ссылку на файл System.Data.OracleClient.dll. Этот код возвращает данные в <xref:System.Data.OracleClient.OracleDataReader>.  
  
  [DataWorks SampleApp.Oracle#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle#1)]  
  
 [[В начало]](#_TOP)  
  
## <a name="entity-framework-examples"></a>Примеры использования платформы Entity Framework  
 В приведенных ниже листингах кода демонстрируется извлечение данных из источника данных путем выполнения запросов к сущностям модели EDM. В этих примерах используются [модель Northwind](http://msdn.microsoft.com/ru-ru/74521f8c-e974-48cb-8858-c08deff52638). Дополнительные сведения см. в разделе [Обзор Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
<a name="_LINQ"></a>   
### <a name="linq-to-entities"></a>LINQ to Entities  
 В данном примере кода запрос LINQ используется для возврата данных в виде объектов Categories, которые проецируются в анонимный тип, содержащий только свойства CategoryID и CategoryName. Дополнительные сведения см. в разделе [LINQ to Entities Обзор](http://msdn.microsoft.com/ru-ru/86d87a27-c17a-45ac-b28d-72c8500333c6).  
  
```  
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
  
 В C#:  
  
```  
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
  
 [[В начало]](#_TOP)  
  
<a name="_QBM"></a>   
### <a name="typed-objectquery"></a>Типизированный запрос ObjectQuery  
 В данном примере кода используется <xref:System.Data.Objects.ObjectQuery%601> для возврата данных в виде объектов Categories. Дополнительные сведения см. в разделе [запросы объектов](http://msdn.microsoft.com/ru-ru/0768033c-876f-471d-85d5-264884349276).  
  
```  
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
  
 В C#:  
  
```  
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
  
 [[В начало]](#_TOP)  
  
<a name="_EntityClient"></a>   
### <a name="entityclient"></a>EntityClient  
 В данном примере кода используется <xref:System.Data.EntityClient.EntityCommand> выполнение запроса Entity SQL. Этот запрос возвращает список записей, представляющих экземпляры типа сущности Categories. <xref:System.Data.EntityClient.EntityDataReader> используется для доступа к записям данных в результирующем наборе. Дополнительные сведения см. в разделе [поставщик EntityClient для Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
```  
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
  
 В C#:  
  
```  
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
  
 [[В начало]](#_TOP)  
  
<a name="_LINQ2SQL"></a>   
## <a name="linq-to-sql"></a>LINQ to SQL  
 В данном примере кода запрос LINQ используется для возврата данных в виде объектов Categories, которые проецируются в анонимный тип, содержащий только свойства CategoryID и CategoryName. Этот пример основан на контексте данных Northwind. Дополнительные сведения см. в разделе [Приступая к работе](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).  
  
```  
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
  
 В C#:  
  
```  
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
  
 [[В начало]](#_TOP)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Создание приложений данных](../Topic/Creating%20Data%20Applications.md)   
 [Запрос модели EDM (задачи Entity Framework)](http://msdn.microsoft.com/ru-ru/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)   
 [Практическое руководство: выполнение запроса, возвращающего объекты анонимного типа](http://msdn.microsoft.com/ru-ru/3b264025-e911-4d73-90ce-992d2b9d189d)   
 [Управляемые поставщики ADO.NET и Центр разработчиков DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)