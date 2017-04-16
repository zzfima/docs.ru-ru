---
title: "Ограничения схемы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Ограничения схемы
Вторым необязательным параметром метода **GetSchema** являются ограничения, используемые для ограничения объема возвращаемых сведений о схеме, передаваемых методу **GetSchema** в виде массива строк.  Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.  
  
 Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server.  Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|рисунка|@Owner|TABLE\_SCHEMA|2|  
|Таблица|@Name|TABLE\_NAME|3|  
|TableType|@TableType|TABLE\_TYPE|4|  
  
## Указание значений ограничения  
 Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения.  Например, чтобы ограничить таблицы, возвращаемые методом **GetSchema** только таблицами из схемы «Sales», присвойте перед передачей массива методу **GetSchema** второму элементу массива значение «Sales».  
  
> [!NOTE]
>  Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`.  Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается.  Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.  
  
> [!NOTE]
>  Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>.  Их может быть меньше максимального количества ограничений.  Предполагается, что отсутствующие ограничения имеют значение NULL \(без ограничений\).  
  
 Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых ограничений, вызвав метод **GetSchema** с именем коллекции схем ограничений Restrictions.  Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.  
  
### Пример  
 В приведенных ниже примерах демонстрируется использование метода <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> класса поставщика данных .NET Framework для SQL Server <xref:System.Data.SqlClient.SqlConnection> для извлечения данных схемы о всех таблицах, содержащихся в учебной базе данных **AdventureWorks**, а также для ограничения возвращаемых данных только таблицами из схемы «Sales».  
  
 \[Visual Basic\]  
  
```  
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
  
 \[C\#\]  
  
```  
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
  
## Ограничения схемы SQL Server  
 В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.  
  
### Users  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|User\_Name|@Name|имя|1|  
  
### Databases  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Имя|@Name|Имя|1|  
  
### Таблицы  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|рисунка|@Owner|TABLE\_SCHEMA|2|  
|Таблица|@Name|TABLE\_NAME|3|  
|TableType|@TableType|TABLE\_TYPE|4|  
  
### Столбцы  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|рисунка|@Owner|TABLE\_SCHEMA|2|  
|Таблица|@Table|TABLE\_NAME|3|  
|Столбец|@Column|COLUMN\_NAME|4|  
  
### StructuredTypeMembers  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|рисунка|@Owner|TABLE\_SCHEMA|2|  
|Таблица|@Table|TABLE\_NAME|3|  
|Столбец|@Column|COLUMN\_NAME|4|  
  
### Представления  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|рисунка|@Owner|TABLE\_SCHEMA|2|  
|Таблица|@Table|TABLE\_NAME|3|  
  
### ViewColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|VIEW\_CATALOG|1|  
|рисунка|@Owner|VIEW\_SCHEMA|2|  
|Таблица|@Table|VIEW\_NAME|3|  
|Столбец|@Column|COLUMN\_NAME|4|  
  
### ProcedureParameters  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|SPECIFIC\_CATALOG|1|  
|рисунка|@Owner|SPECIFIC\_SCHEMA|2|  
|Имя|@Name|SPECIFIC\_NAME|3|  
|Параметр|@Parameter|PARAMETER\_NAME|4|  
  
### Процедуры  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|SPECIFIC\_CATALOG|1|  
|рисунка|@Owner|SPECIFIC\_SCHEMA|2|  
|Имя|@Name|SPECIFIC\_NAME|3|  
|Тип|@Type|ROUTINE\_TYPE|4|  
  
### IndexColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|db\_name\(\)|1|  
|рисунка|@Owner|user\_name\(\)|2|  
|Таблица|@Table|o.  имя|3|  
|ConstraintName|@ConstraintName|x.  имя|4|  
|Столбец|@Column|В.  имя|5|  
  
### Indexes  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|db\_name\(\)|1|  
|рисунка|@Owner|user\_name\(\)|2|  
|Таблица|@Table|o.  имя|3|  
  
### UserDefinedTypes  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|assembly\_name|@AssemblyName|сборки.  имя|1|  
|udt\_name|@UDTName|types.assembly\_class|2|  
  
### ForeignKeys  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|CONSTRAINT\_CATALOG|1|  
|рисунка|@Owner|CONSTRAINT\_SCHEMA|2|  
|Таблица|@Table|TABLE\_NAME|3|  
|Имя|@Name|CONSTRAINT\_NAME|4|  
  
## Ограничения схемы SQL Server 2008  
 В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008.  Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 \(SP1\) и SQL Server 2008.  Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.  
  
### ColumnSetColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|рисунка|@Owner|TABLE\_SCHEMA|2|  
|Таблица|@Table|TABLE\_NAME|3|  
  
### AllColumns  
  
|Имя ограничения|Имя параметра|Значение ограничения по умолчанию|Номер ограничения|  
|---------------------|-------------------|---------------------------------------|-----------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|рисунка|@Owner|TABLE\_SCHEMA|2|  
|Таблица|@Table|TABLE\_NAME|3|  
|Столбец|@Column|COLUMN\_NAME|4|  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)