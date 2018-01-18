---
title: "Статистика поставщика для SQL Server"
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
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 43cafc8feb6cee761baffcb2efe41aec18e98abb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="provider-statistics-for-sql-server"></a>Статистика поставщика для SQL Server
Начиная с .NET Framework 2.0, поставщик данных .NET Framework для SQL Server поддерживает получение статистики во время выполнения. После создания допустимого объекта соединения необходимо включить статистику путем присвоения свойству <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> объекта <xref:System.Data.SqlClient.SqlConnection> значения `True`. После включения статистики ее можно просмотреть в виде «моментального снимка во времени» путем получения ссылки <xref:System.Collections.IDictionary> через метод <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> объекта <xref:System.Data.SqlClient.SqlConnection>. Для обработки списка может использоваться набор элементов словаря, представленных в виде пар «имя/значение». Эти пары «имя/значение» являются неупорядоченными. Для сброса счетчиков можно в любое время вызвать метод <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> объекта <xref:System.Data.SqlClient.SqlConnection>. Если сбор статистики не был включен, исключение не формируется. Кроме того, если <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> вызывается перед вызовом <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A>, полученные значения являются первоначальными для каждой записи. Если статистика включена, запустите приложение и через некоторое время отключите статистику. Полученные значения будут отражать значения, собранные до момента отключения статистики. Все собранные статистические значения относятся к конкретному соединению.  
  
## <a name="statistical-values-available"></a>Доступные статистические значения  
 На данный момент существует 18 различных элементов, доступ к которым предоставляется поставщиком Microsoft SQL Server. Число доступных элементов, доступных через **число** свойство <xref:System.Collections.IDictionary> ссылки, возвращенный интерфейс <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>. Для всех счетчиков статистики поставщика используется среда <xref:System.Int64> типа (**long** в C# и Visual Basic), который является 64-разрядные. Максимальное значение **int64** тип данных, в соответствии с определением **int64. MaxValue** , равно ((2^63) 1)). После достижения значениями счетчиков этого максимального значения их больше нельзя считать точными. Это означает, что **int64. MaxValue**-1((2^63)-2) фактически является максимальным действительным значением любого статистического показателя.  
  
> [!NOTE]
>  Для возврата статистики поставщика используется словарь, поскольку количество, имена и последовательность возвращаемых статистических данных в будущем может измениться. Функционирование приложений не должно зависеть от того, будет ли найдено в словаре какое-то определенное значение; вместо этого следует проверять наличие значения и с учетом результатов этой проверки переходить в ту или иную часть приложения.  
  
 В следующей таблице описаны доступные текущие статистические значения. Обратите внимание, что имена ключей для отдельных значений в региональных версиях Microsoft .NET Framework не локализованы.  
  
|Имя ключа|Описание|  
|--------------|-----------------|  
|`BuffersReceived`|Возвращает число пакетов TDS, полученных поставщиком от SQL Server после начала использования приложением поставщика и включения статистики.|  
|`BuffersSent`|Возвращает число пакетов TDS, отправленных на SQL Server поставщиком после включения статистики. Для больших по размеру команд может потребоваться несколько буферов. Например, если на сервер отправляется команда, состоящая из большого объема текста, и для ее передачи требуется шесть пакетов, то значение `ServerRoundtrips` увеличивается на единицу, а значение `BuffersSent` - на шесть.|  
|`BytesReceived`|Возвращает число байтов данных в пакетах TDS, полученных поставщиком от SQL Server после начала использования приложением поставщика и включения статистики.|  
|`BytesSent`|Возвращает число байтов данных, отправленных на SQL Server в пакетах TDS после начала использования приложением поставщика и включения статистики.|  
|`ConnectionTime`|Время (в миллисекундах), в течение которого было открыто соединение после включения статистики (или полное время соединения, если статистика была включена до открытия соединения).|  
|`CursorOpens`|Возвращает число операций открытия курсора в соединении после начала использования приложением поставщика и включения статистики.<br /><br /> Обратите внимание, что однопроходные результаты только для чтения, возвращаемые инструкциями SELECT, не рассматриваются как курсоры, поэтому не влияют на значение этого счетчика.|  
|`ExecutionTime`|Возвращает совокупное количество времени (в миллисекундах), которое поставщик потратил на обработку после включения статистики, с учетом того времени, которое потрачено на ожидание ответов от сервера, а также времени, потраченного на выполнение кода самим поставщиком.<br /><br /> Код учета времени входит в следующие классы:<br /><br /> SqlConnection<br /><br /> SqlCommand<br /><br /> SqlDataReader<br /><br /> SqlDataAdapter<br /><br /> SqlTransaction<br /><br /> SqlCommandBuilder<br /><br /> Для следующих членов учет времени не предусмотрен, что позволяет свести к минимуму число членов, функционирование которых может быть нарушено в условиях низкой производительности:<br /><br /> SqlDataReader<br /><br /> оператор this[] (все перегруженные варианты)<br /><br /> GetBoolean<br /><br /> GetChar<br /><br /> GetDateTime<br /><br /> GetDecimal<br /><br /> GetDouble<br /><br /> GetFloat<br /><br /> GetGuid<br /><br /> GetInt16<br /><br /> GetInt32<br /><br /> GetInt64<br /><br /> GetName<br /><br /> GetOrdinal<br /><br /> GetSqlBinary<br /><br /> GetSqlBoolean<br /><br /> GetSqlByte<br /><br /> GetSqlDateTime<br /><br /> GetSqlDecimal<br /><br /> GetSqlDouble<br /><br /> GetSqlGuid<br /><br /> GetSqlInt16<br /><br /> GetSqlInt32<br /><br /> GetSqlInt64<br /><br /> GetSqlMoney<br /><br /> GetSqlSingle<br /><br /> GetSqlString<br /><br /> GetString<br /><br /> IsDBNull|  
|`IduCount`|Возвращает общее число инструкций INSERT, DELETE и UPDATE, выполненных в составе соединения после начала использования приложением поставщика и включения статистики.|  
|`IduRows`|Возвращает общее число строк, затронутых инструкциями INSERT, DELETE и UPDATE, которые выполнены в составе соединения после начала использования приложением поставщика и включения статистики.|  
|`NetworkServerTime`|Возвращает совокупное количество времени (в миллисекундах), которое поставщик потратил на ожидание ответов от сервера после начала использования приложением поставщика и включения статистики.|  
|`PreparedExecs`|Возвращает число подготовленных команд, выполненных в соединении после начала использования приложением поставщика и включения статистики.|  
|`Prepares`|Возвращает число инструкций, подготовленных в соединении после начала использования приложением поставщика и включения статистики.|  
|`SelectCount`|Возвращает число инструкций SELECT, выполненных в соединении после начала использования приложением поставщика и включения статистики. Это число включает инструкции FETCH, применявшиеся для получения строк из курсоров, причем данные о количестве инструкций SELECT обновляются по достижении конца данных в объекте <xref:System.Data.SqlClient.SqlDataReader>.|  
|`SelectRows`|Возвращает число строк, выбранных после начала использования приложением поставщика и включения статистики. Данный счетчик отражает все строки, созданные инструкциями SQL, даже те, которые фактически не использовались вызывающим объектом. Например, значение этого счетчика не изменилось бы и после закрытия модуля чтения данных до чтения всего результирующего набора. Сюда входят строки, полученные из курсоров с помощью инструкций FETCH.|  
|`ServerRoundtrips`|Возвращает данные о том, сколько раз в соединении были отправлены команды на сервер и получен ответ после начала использования приложением поставщика и включения статистики.|  
|`SumResultSets`|Возвращает число результирующих наборов, использованных после начала использования приложением поставщика и включения статистики. Например, в это число входит любой результирующий набор, возвращенный клиенту. Применительно к курсорам результат каждой операции выборки строк или блоков рассматривается как независимый результирующий набор.|  
|`Transactions`|Возвращает число пользовательских транзакций, запущенных после начала использования приложением поставщика и включения статистики, с учетом откатов. Если соединение выполняется в режиме автоматической фиксации, каждая команда считается транзакцией.<br /><br /> Данный счетчик увеличивает счетчик транзакций, как только выполняется инструкция BEGIN TRAN, независимо от того, была ли зафиксирована транзакция или в последующем произошел ее откат.|  
|`UnpreparedExecs`|Возвращает число неподготовленных инструкций, выполненных в соединении после начала использования приложением поставщика и включения статистики.|  
  
### <a name="retrieving-a-value"></a>Получение значения  
 Следующее приложение командной строки показывает включение статистики при соединении, получение четырех отдельных статистических значений и их запись в окно консоли.  
  
> [!NOTE]
>  В следующем примере используется образец **AdventureWorks** базы данных, входящий в состав [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Представленная в образце кода строка соединения предполагает, что база данных установлена и доступна на локальном компьютере. Измените строку соединения при необходимости в соответствии с вашей средой.  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =   
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a>Получение всех значений  
 Следующее приложение командной строки показывает включение статистики при соединении, получение всех доступных статистических значений с помощью перечислителя и их запись в окно консоли.  
  
> [!NOTE]
>  В следующем примере используется образец **AdventureWorks** базы данных, входящий в состав [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Представленная в образце кода строка соединения предполагает, что база данных установлена и доступна на локальном компьютере. Измените строку соединения при необходимости в соответствии с вашей средой.  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
