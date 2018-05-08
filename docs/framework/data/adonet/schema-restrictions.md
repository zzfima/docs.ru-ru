---
title: Ограничения схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: c62f934561fa4a6c352ff84b8c1201461c42de39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="schema-restrictions"></a>Ограничения схемы
Вторым необязательным параметром метода **GetSchema** в противном случае возвращается ограничений, которые используются для ограничения объема сведений о схеме, и оно передается **GetSchema** метод как массив строк . Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.  
  
 Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server. Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
## <a name="specifying-restriction-values"></a>Указание значений ограничения  
 Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения. Например, чтобы ограничить таблицы, возвращаемые **GetSchema** только таблицами из схемы «Sales», присвойте второй элемент массива значение «Sales» перед передачей **GetSchema** метод.  
  
> [!NOTE]
>  Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`. Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается. Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.  
  
> [!NOTE]
>  Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>. Их может быть меньше максимального количества ограничений. Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).  
  
 Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых ограничений, вызвав **GetSchema** метод с именем коллекции схем ограничений — «Ограничения». Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.  
  
### <a name="example"></a>Пример  
 Следующие примеры демонстрируют, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных .NET Framework для SQL Server <xref:System.Data.SqlClient.SqlConnection> класса для извлечения сведений о всех таблиц, содержащихся в схеме **AdventureWorks**образца базы данных, а также для ограничения сведений возвращаются только таблицами из схемы «Sales»:  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a>Ограничения схемы SQL Server  
 В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.  
  
### <a name="users"></a>Users  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|User_Name|@Name|имя|1|  
  
### <a name="databases"></a>Databases  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|name|@Name|name|1|  
  
### <a name="tables"></a>Таблицы  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
### <a name="columns"></a>Столбцы  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
|Столбец|@Column|COLUMN_NAME|4|  
  
### <a name="structuredtypemembers"></a>StructuredTypeMembers  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
|Столбец|@Column|COLUMN_NAME|4|  
  
### <a name="views"></a>Представления  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
  
### <a name="viewcolumns"></a>ViewColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|VIEW_CATALOG|1|  
|Владелец|@Owner|VIEW_SCHEMA|2|  
|Таблица|@Table|VIEW_NAME|3|  
|Столбец|@Column|COLUMN_NAME|4|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|SPECIFIC_CATALOG|1|  
|Владелец|@Owner|SPECIFIC_SCHEMA|2|  
|name|@Name|SPECIFIC_NAME|3|  
|Параметр|@Parameter|PARAMETER_NAME|4|  
  
### <a name="procedures"></a>Процедуры  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|SPECIFIC_CATALOG|1|  
|Владелец|@Owner|SPECIFIC_SCHEMA|2|  
|name|@Name|SPECIFIC_NAME|3|  
|Тип|@Type|ROUTINE_TYPE|4|  
  
### <a name="indexcolumns"></a>IndexColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|db_name()|1|  
|Владелец|@Owner|user_name()|2|  
|Таблица|@Table|o.name|3|  
|ConstraintName|@ConstraintName|x.name|4|  
|Столбец|@Column|c.name|5|  
  
### <a name="indexes"></a>Indexes  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|db_name()|1|  
|Владелец|@Owner|user_name()|2|  
|Таблица|@Table|o.name|3|  
  
### <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|assembly_name|@AssemblyName|assemblies.name|1|  
|udt_name|@UDTName|types.assembly_class|2|  
  
### <a name="foreignkeys"></a>ForeignKeys  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|CONSTRAINT_CATALOG|1|  
|Владелец|@Owner|CONSTRAINT_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
|name|@Name|CONSTRAINT_NAME|4|  
  
## <a name="sql-server-2008-schema-restrictions"></a>Ограничения схемы SQL Server 2008  
 В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008. Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1) и SQL Server 2008. Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.  
  
### <a name="columnsetcolumns"></a>ColumnSetColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
  
### <a name="allcolumns"></a>AllColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalog|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
|Столбец|@Column|COLUMN_NAME|4|  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
