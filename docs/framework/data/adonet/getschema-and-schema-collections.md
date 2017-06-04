---
title: "Метод GetSchema и коллекции схем | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Метод GetSchema и коллекции схем
Классы **Connection** в каждом из управляемых поставщиков .NET Framework реализуют метод **GetSchema**, который используется для получения сведений о схеме базы данных, с которой в данный момент установлено соединение, и метод **GetSchema** возвращает сведения о схеме в виде объекта <xref:System.Data.DataTable>.  **GetSchema** — перегружаемый метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.  
  
## Указание коллекций схем  
 Первым необязательным параметром метода **GetSchema** является имя коллекции, указанное в виде строки.  Существует два типа коллекций схем: стандартные \(общие для всех поставщиков\) и специальные \(определенные для каждого поставщика\).  
  
 Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых коллекций схем, вызвав метод **GetSchema** без аргументов или с именем коллекции схем MetaDataCollections.  При этом будет возвращена <xref:System.Data.DataTable> со списком поддерживаемых коллекций схем, число ограничений, которые каждая из них поддерживает, и число идентификационных частей, которые в них используются.  
  
### Получение примера коллекций схем  
 В следующем примере демонстрируется использование метода <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> поставщика данных .NET Framework для SQL Server класса <xref:System.Data.SqlClient.SqlConnection> для получения сведений схем обо всех таблицах, содержащихся в образце базы данных **AdventureWorks**:  
  
 \[Visual Basic\]  
  
```  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
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
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
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
  
## См. также  
 [Получение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)