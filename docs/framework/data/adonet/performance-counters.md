---
title: Счетчики производительности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b121b71-78f8-4ae2-9aa1-0b2e15778e57
ms.openlocfilehash: 985951180a5c8ee09460b7fe4bf3213b986c3bb6
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980071"
---
# <a name="performance-counters-in-adonet"></a>Счетчики производительности в ADO.NET
В ADO.NET 2.0 появилась расширенная поддержка счетчиков производительности, включая поддержку как <xref:System.Data.SqlClient>, так и <xref:System.Data.OracleClient>. Счетчики производительности <xref:System.Data.SqlClient> предыдущих версий ADO.NET устарели и заменены новыми счетчиками производительности, которые рассматриваются в этом разделе. Счетчики производительности ADO.NET можно использовать для контроля состояния приложения и используемых им ресурсов соединения. Показания счетчиков производительности можно отслеживать с помощью системного монитора Windows или получить к ним доступ программным путем с помощью класса <xref:System.Diagnostics.PerformanceCounter> в пространстве имен <xref:System.Diagnostics>.  
  
## <a name="available-performance-counters"></a>Доступные счетчики производительности  
 В настоящее время имеется 14 разных счетчиков производительности, доступных для <xref:System.Data.SqlClient> и <xref:System.Data.OracleClient>, как показано в следующей таблице. Обратите внимание, что имена отдельных счетчиков производительности не локализованы в региональных версиях платформы Microsoft .NET Framework.  
  
|Счетчик производительности|Описание|  
|-------------------------|-----------------|  
|`HardConnectsPerSecond`|Количество соединений с сервером базы данных в секунду.|  
|`HardDisconnectsPerSecond`|Количество разрывов соединений с сервером базы данных в секунду.|  
|`NumberOfActiveConnectionPoolGroups`|Количество уникальных активных групп пулов соединений. Этот счетчик управляется числом уникальных строк соединения, найденных в домене приложения.|  
|`NumberOfActiveConnectionPools`|Общее число пулов соединений.|  
|`NumberOfActiveConnections`|Количество текущих активных соединений. **Примечание.**  Этот счетчик производительности не включен по умолчанию. Сведения о включении этого счетчика производительности см. в разделе [Активация счетчиков по умолчанию](#ActivatingOffByDefault).|  
|`NumberOfFreeConnections`|Количество соединений, доступных в пулах соединений. **Примечание.**  Этот счетчик производительности не включен по умолчанию. Сведения о включении этого счетчика производительности см. в разделе [Активация счетчиков по умолчанию](#ActivatingOffByDefault).|  
|`NumberOfInactiveConnectionPoolGroups`|Количество уникальных групп пулов соединений, отмеченных для усечения. Этот счетчик управляется числом уникальных строк соединения, найденных в домене приложения.|  
|`NumberOfInactiveConnectionPools`|Количество неактивных пулов соединений, не участвовавших в последних операциях и ожидающих удаления.|  
|`NumberOfNonPooledConnections`|Количество активных соединений, не помещенных в пулы.|  
|`NumberOfPooledConnections`|Количество активных соединений, которые управляются инфраструктурой пулов соединений.|  
|`NumberOfReclaimedConnections`|Количество соединений, затребованных сборкой мусора, в которой приложение не вызывает методы `Close` и `Dispose`. Если соединения не закрывать и не удалять явно, производительность может снижаться.|  
|`NumberOfStasisConnections`|Количество соединений, ожидающих в настоящий момент завершения действия и поэтому доступных для приложения.|  
|`SoftConnectsPerSecond`|Количество активных соединений, извлекаемых из пула соединений. **Примечание.**  Этот счетчик производительности не включен по умолчанию. Сведения о включении этого счетчика производительности см. в разделе [Активация счетчиков по умолчанию](#ActivatingOffByDefault).|  
|`SoftDisconnectsPerSecond`|Количество активных соединений, возвращаемых в пул соединений. **Примечание.**  Этот счетчик производительности не включен по умолчанию. Сведения о включении этого счетчика производительности см. в разделе [Активация счетчиков по умолчанию](#ActivatingOffByDefault).|  
  
### <a name="connection-pool-groups-and-connection-pools"></a>Группы пула соединений и пулы соединений  
 При использовании проверки подлинности Windows (встроенная безопасность) необходимо следить за счетчиками `NumberOfActiveConnectionPoolGroups` и `NumberOfActiveConnectionPools`. Причина в том, что группы пулов соединений сопоставлены с уникальными строками соединений. Если используется встроенная безопасность, то пулы соединений сопоставляются со строками соединений и дополнительно создают специальные пулы для отдельных идентификаторов Windows. Например, если Кирилл и Мария, находящиеся в одном домене приложений, используют строку соединения `"Data Source=MySqlServer;Integrated Security=true"`, создается группа пула соединений для этой строки соединения и два дополнительных пула - один для Кирилла, другой для Марии. Если Джон и марта используют строку подключения с идентичным именем входа SQL Server, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`, то для удостоверения **ловпривусер** создается только один пул.  
  
<a name="ActivatingOffByDefault"></a>   
### <a name="activating-off-by-default-counters"></a>Активация счетчиков, отключенных по умолчанию  
 Счетчики производительности `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond` и `SoftConnectsPerSecond` отключены по умолчанию. Чтобы включить их, добавьте в файл конфигурации приложения следующие данные:  
  
```xml  
<system.diagnostics>  
  <switches>  
    <add name="ConnectionPoolPerformanceCounterDetail"  
         value="4"/>  
  </switches>  
</system.diagnostics>  
```  
  
## <a name="retrieving-performance-counter-values"></a>Получение значений счетчиков производительности  
 В следующем приложении командной строки показан способ получения значений счетчиков производительности. Чтобы возвратить данные для всех счетчиков производительности ADO.NET, соединения должны быть открыты и активны.  
  
> [!NOTE]
> В этом примере используется образец базы данных **AdventureWorks** , входящий в состав SQL Server. Строка соединения, представленная в образце кода, предполагает, что база данных установлена и доступна на локальном компьютере с именем экземпляра SqlExpress, и что созданы имена входа SQL Server, соответствующие представленным в строках соединения. Имена входа SQL Server придется создать, если сервер использует параметры безопасности по умолчанию, разрешающие только проверку подлинности Windows. При необходимости измените строки соединения, чтобы они соответствовали среде.  
  
### <a name="example"></a>Пример  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System.Data.SqlClient  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Class Program  
  
    Private PerfCounters(9) As PerformanceCounter  
    Private connection As SqlConnection = New SqlConnection  
  
    Public Shared Sub Main()  
        Dim prog As Program = New Program  
        ' Open a connection and create the performance counters.   
        prog.connection.ConnectionString = _  
           GetIntegratedSecurityConnectionString()  
        prog.SetUpPerformanceCounters()  
        Console.WriteLine("Available Performance Counters:")  
  
        ' Create the connections and display the results.  
        prog.CreateConnections()  
        Console.WriteLine("Press Enter to finish.")  
        Console.ReadLine()  
    End Sub  
  
    Private Sub CreateConnections()  
        ' List the Performance counters.  
        WritePerformanceCounters()  
  
        ' Create 4 connections and display counter information.  
        Dim connection1 As SqlConnection = New SqlConnection( _  
           GetIntegratedSecurityConnectionString)  
        connection1.Open()  
        Console.WriteLine("Opened the 1st Connection:")  
        WritePerformanceCounters()  
  
        Dim connection2 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionStringDifferent)  
        connection2.Open()  
        Console.WriteLine("Opened the 2nd Connection:")  
        WritePerformanceCounters()  
  
        Console.WriteLine("Opened the 3rd Connection:")  
        Dim connection3 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection3.Open()  
        WritePerformanceCounters()  
  
        Dim connection4 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection4.Open()  
        Console.WriteLine("Opened the 4th Connection:")  
        WritePerformanceCounters()  
  
        connection1.Close()  
        Console.WriteLine("Closed the 1st Connection:")  
        WritePerformanceCounters()  
  
        connection2.Close()  
        Console.WriteLine("Closed the 2nd Connection:")  
        WritePerformanceCounters()  
  
        connection3.Close()  
        Console.WriteLine("Closed the 3rd Connection:")  
        WritePerformanceCounters()  
  
        connection4.Close()  
        Console.WriteLine("Closed the 4th Connection:")  
        WritePerformanceCounters()  
    End Sub  
  
    Private Enum ADO_Net_Performance_Counters  
        NumberOfActiveConnectionPools  
        NumberOfReclaimedConnections  
        HardConnectsPerSecond  
        HardDisconnectsPerSecond  
        NumberOfActiveConnectionPoolGroups  
        NumberOfInactiveConnectionPoolGroups  
        NumberOfInactiveConnectionPools  
        NumberOfNonPooledConnections  
        NumberOfPooledConnections  
        NumberOfStasisConnections  
        ' The following performance counters are more expensive to track.  
        ' Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        '     SoftConnectsPerSecond  
        '     SoftDisconnectsPerSecond  
        '     NumberOfActiveConnections  
        '     NumberOfFreeConnections  
    End Enum  
  
    Private Sub SetUpPerformanceCounters()  
        connection.Close()  
        Me.PerfCounters(9) = New PerformanceCounter()  
  
        Dim instanceName As String = GetInstanceName()  
        Dim apc As Type = GetType(ADO_Net_Performance_Counters)  
        Dim i As Integer = 0  
        Dim s As String = ""  
        For Each s In [Enum].GetNames(apc)  
            Me.PerfCounters(i) = New PerformanceCounter()  
            Me.PerfCounters(i).CategoryName = ".NET Data Provider for SqlServer"  
            Me.PerfCounters(i).CounterName = s  
            Me.PerfCounters(i).InstanceName = instanceName  
            i = (i + 1)  
        Next  
    End Sub  
  
    Private Declare Function GetCurrentProcessId Lib "kernel32.dll" () As Integer  
  
    Private Function GetInstanceName() As String  
        'This works for Winforms apps.   
        Dim instanceName As String = _  
           System.Reflection.Assembly.GetEntryAssembly.GetName.Name  
  
        ' Must replace special characters like (, ), #, /, \\   
        Dim instanceName2 As String = _  
           AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
           .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        'For ASP.NET applications your instanceName will be your CurrentDomain's   
        'FriendlyName. Replace the line above that sets the instanceName with this:   
        'instanceName = AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
        '    .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        Dim pid As String = GetCurrentProcessId.ToString  
        instanceName = (instanceName + ("[" & (pid & "]")))  
        Console.WriteLine("Instance Name: {0}", instanceName)  
        Console.WriteLine("---------------------------")  
        Return instanceName  
    End Function  
  
    Private Sub WritePerformanceCounters()  
        Console.WriteLine("---------------------------")  
        For Each p As PerformanceCounter In Me.PerfCounters  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue)  
        Next  
        Console.WriteLine("---------------------------")  
    End Sub  
  
    Private Shared Function GetIntegratedSecurityConnectionString() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Data Source=.\SqlExpress;Integrated Security=True;" &   
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionString() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" &   
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionStringDifferent() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" & _  
          "User Id=LowPriv;Password=Data!05;")  
    End Function  
End Class  
```  

```csharp  
using System;  
using System.Data.SqlClient;  
using System.Diagnostics;  
using System.Runtime.InteropServices;  
  
class Program  
{  
    PerformanceCounter[] PerfCounters = new PerformanceCounter[10];  
    SqlConnection connection = new SqlConnection();  
  
    static void Main()  
    {  
        Program prog = new Program();  
        // Open a connection and create the performance counters.  
        prog.connection.ConnectionString =  
           GetIntegratedSecurityConnectionString();  
        prog.SetUpPerformanceCounters();  
        Console.WriteLine("Available Performance Counters:");  
  
        // Create the connections and display the results.  
        prog.CreateConnections();  
        Console.WriteLine("Press Enter to finish.");  
        Console.ReadLine();  
    }  
  
    private void CreateConnections()  
    {  
        // List the Performance counters.  
        WritePerformanceCounters();  
  
        // Create 4 connections and display counter information.  
        SqlConnection connection1 = new SqlConnection(  
              GetIntegratedSecurityConnectionString());  
        connection1.Open();  
        Console.WriteLine("Opened the 1st Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection2 = new SqlConnection(  
              GetSqlConnectionStringDifferent());  
        connection2.Open();  
        Console.WriteLine("Opened the 2nd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection3 = new SqlConnection(  
              GetSqlConnectionString());  
        connection3.Open();  
        Console.WriteLine("Opened the 3rd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection4 = new SqlConnection(  
              GetSqlConnectionString());  
        connection4.Open();  
        Console.WriteLine("Opened the 4th Connection:");  
        WritePerformanceCounters();  
  
        connection1.Close();  
        Console.WriteLine("Closed the 1st Connection:");  
        WritePerformanceCounters();  
  
        connection2.Close();  
        Console.WriteLine("Closed the 2nd Connection:");  
        WritePerformanceCounters();  
  
        connection3.Close();  
        Console.WriteLine("Closed the 3rd Connection:");  
        WritePerformanceCounters();  
  
        connection4.Close();  
        Console.WriteLine("Closed the 4th Connection:");  
        WritePerformanceCounters();  
    }  
  
    private enum ADO_Net_Performance_Counters  
    {  
        NumberOfActiveConnectionPools,  
        NumberOfReclaimedConnections,  
        HardConnectsPerSecond,  
        HardDisconnectsPerSecond,  
        NumberOfActiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPools,  
        NumberOfNonPooledConnections,  
        NumberOfPooledConnections,  
        NumberOfStasisConnections  
        // The following performance counters are more expensive to track.  
        // Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        //     SoftConnectsPerSecond  
        //     SoftDisconnectsPerSecond  
        //     NumberOfActiveConnections  
        //     NumberOfFreeConnections  
    }  
  
    private void SetUpPerformanceCounters()  
    {  
        connection.Close();  
        this.PerfCounters = new PerformanceCounter[10];  
        string instanceName = GetInstanceName();  
        Type apc = typeof(ADO_Net_Performance_Counters);  
        int i = 0;  
        foreach (string s in Enum.GetNames(apc))  
        {  
            this.PerfCounters[i] = new PerformanceCounter();  
            this.PerfCounters[i].CategoryName = ".NET Data Provider for SqlServer";  
            this.PerfCounters[i].CounterName = s;  
            this.PerfCounters[i].InstanceName = instanceName;  
            i++;  
        }  
    }  
  
    [DllImport("kernel32.dll", SetLastError = true)]  
    static extern int GetCurrentProcessId();  
  
    private string GetInstanceName()  
    {  
        //This works for Winforms apps.  
        string instanceName =  
            System.Reflection.Assembly.GetEntryAssembly().GetName().Name;  
  
        // Must replace special characters like (, ), #, /, \\  
        string instanceName2 =  
            AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(', '[')  
            .Replace(')', ']').Replace('#', '_').Replace('/', '_').Replace('\\', '_');  
  
        // For ASP.NET applications your instanceName will be your CurrentDomain's   
        // FriendlyName. Replace the line above that sets the instanceName with this:  
        // instanceName = AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(','[')  
        // .Replace(')',']').Replace('#','_').Replace('/','_').Replace('\\','_');  
  
        string pid = GetCurrentProcessId().ToString();  
        instanceName = instanceName + "[" + pid + "]";  
        Console.WriteLine("Instance Name: {0}", instanceName);  
        Console.WriteLine("---------------------------");  
        return instanceName;  
    }  
  
    private void WritePerformanceCounters()  
    {  
        Console.WriteLine("---------------------------");  
        foreach (PerformanceCounter p in this.PerfCounters)  
        {  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue());  
        }  
        Console.WriteLine("---------------------------");  
    }  
  
    private static string GetIntegratedSecurityConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;Integrated Security=True;" +  
          "Initial Catalog=AdventureWorks";  
    }  
    private static string GetSqlConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" +  
          "Initial Catalog=AdventureWorks";  
    }  
  
    private static string GetSqlConnectionStringDifferent()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" +  
          "User Id=LowPriv;Password=Data!05;";  
    }  
}  
```  

## <a name="see-also"></a>См. также:

- [Подключение к источнику данных](connecting-to-a-data-source.md)
- [Организация пулов соединений OLE DB, ODBC и Oracle](ole-db-odbc-and-oracle-connection-pooling.md)
- [Счетчики производительности для ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/fxk122b4(v=vs.100))
- [Профилирование среды выполнения](../../debug-trace-profile/runtime-profiling.md)
- [Общие сведения о мониторинге пороговых значений производительности](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))
- [Общие сведения об ADO.NET](ado-net-overview.md)
