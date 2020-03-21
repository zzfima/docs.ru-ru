---
title: Счетчики производительности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b121b71-78f8-4ae2-9aa1-0b2e15778e57
ms.openlocfilehash: b68787980a8b64d9ee90ed8d834fab2c5c69006b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149340"
---
# <a name="performance-counters-in-adonet"></a><span data-ttu-id="f33b3-102">Счетчики производительности в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f33b3-102">Performance Counters in ADO.NET</span></span>
<span data-ttu-id="f33b3-103">В ADO.NET 2.0 появилась расширенная поддержка счетчиков производительности, включая поддержку как <xref:System.Data.SqlClient>, так и <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="f33b3-103">ADO.NET 2.0 introduced expanded support for performance counters that includes support for both <xref:System.Data.SqlClient> and <xref:System.Data.OracleClient>.</span></span> <span data-ttu-id="f33b3-104">Счетчики производительности <xref:System.Data.SqlClient> предыдущих версий ADO.NET устарели и заменены новыми счетчиками производительности, которые рассматриваются в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f33b3-104">The <xref:System.Data.SqlClient> performance counters available in previous versions of ADO.NET have been deprecated and replaced with the new performance counters discussed in this topic.</span></span> <span data-ttu-id="f33b3-105">Счетчики производительности ADO.NET можно использовать для контроля состояния приложения и используемых им ресурсов соединения.</span><span class="sxs-lookup"><span data-stu-id="f33b3-105">You can use ADO.NET performance counters to monitor the status of your application and the connection resources that it uses.</span></span> <span data-ttu-id="f33b3-106">Показания счетчиков производительности можно отслеживать с помощью системного монитора Windows или получить к ним доступ программным путем с помощью класса <xref:System.Diagnostics.PerformanceCounter> в пространстве имен <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="f33b3-106">Performance counters can be monitored by using Windows Performance Monitor or can be accessed programmatically using the <xref:System.Diagnostics.PerformanceCounter> class in the <xref:System.Diagnostics> namespace.</span></span>  
  
## <a name="available-performance-counters"></a><span data-ttu-id="f33b3-107">Доступные счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="f33b3-107">Available Performance Counters</span></span>  
 <span data-ttu-id="f33b3-108">В настоящее время имеется 14 разных счетчиков производительности, доступных для <xref:System.Data.SqlClient> и <xref:System.Data.OracleClient>, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f33b3-108">Currently there are 14 different performance counters available for <xref:System.Data.SqlClient> and <xref:System.Data.OracleClient> as described in the following table.</span></span> <span data-ttu-id="f33b3-109">Обратите внимание, что имена отдельных счетчиков производительности не локализованы в региональных версиях платформы Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f33b3-109">Note that the names for the individual counters are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="f33b3-110">Счетчик производительности</span><span class="sxs-lookup"><span data-stu-id="f33b3-110">Performance counter</span></span>|<span data-ttu-id="f33b3-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f33b3-111">Description</span></span>|  
|-------------------------|-----------------|  
|`HardConnectsPerSecond`|<span data-ttu-id="f33b3-112">Количество соединений с сервером базы данных в секунду.</span><span class="sxs-lookup"><span data-stu-id="f33b3-112">The number of connections per second that are being made to a database server.</span></span>|  
|`HardDisconnectsPerSecond`|<span data-ttu-id="f33b3-113">Количество разрывов соединений с сервером базы данных в секунду.</span><span class="sxs-lookup"><span data-stu-id="f33b3-113">The number of disconnects per second that are being made to a database server.</span></span>|  
|`NumberOfActiveConnectionPoolGroups`|<span data-ttu-id="f33b3-114">Количество уникальных активных групп пулов соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-114">The number of unique connection pool groups that are active.</span></span> <span data-ttu-id="f33b3-115">Этот счетчик управляется числом уникальных строк соединения, найденных в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="f33b3-115">This counter is controlled by the number of unique connection strings that are found in the AppDomain.</span></span>|  
|`NumberOfActiveConnectionPools`|<span data-ttu-id="f33b3-116">Общее число пулов соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-116">The total number of connection pools.</span></span>|  
|`NumberOfActiveConnections`|<span data-ttu-id="f33b3-117">Количество текущих активных соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-117">The number of active connections that are currently in use.</span></span> <span data-ttu-id="f33b3-118">**Примечание:**  Этот счетчик производительности не включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f33b3-118">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="f33b3-119">Для включения этого счетчика производительности [см.](#ActivatingOffByDefault)</span><span class="sxs-lookup"><span data-stu-id="f33b3-119">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`NumberOfFreeConnections`|<span data-ttu-id="f33b3-120">Количество соединений, доступных в пулах соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-120">The number of connections available for use in the connection pools.</span></span> <span data-ttu-id="f33b3-121">**Примечание:**  Этот счетчик производительности не включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f33b3-121">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="f33b3-122">Для включения этого счетчика производительности [см.](#ActivatingOffByDefault)</span><span class="sxs-lookup"><span data-stu-id="f33b3-122">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`NumberOfInactiveConnectionPoolGroups`|<span data-ttu-id="f33b3-123">Количество уникальных групп пулов соединений, отмеченных для усечения.</span><span class="sxs-lookup"><span data-stu-id="f33b3-123">The number of unique connection pool groups that are marked for pruning.</span></span> <span data-ttu-id="f33b3-124">Этот счетчик управляется числом уникальных строк соединения, найденных в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="f33b3-124">This counter is controlled by the number of unique connection strings that are found in the AppDomain.</span></span>|  
|`NumberOfInactiveConnectionPools`|<span data-ttu-id="f33b3-125">Количество неактивных пулов соединений, не участвовавших в последних операциях и ожидающих удаления.</span><span class="sxs-lookup"><span data-stu-id="f33b3-125">The number of inactive connection pools that have not had any recent activity and are waiting to be disposed.</span></span>|  
|`NumberOfNonPooledConnections`|<span data-ttu-id="f33b3-126">Количество активных соединений, не помещенных в пулы.</span><span class="sxs-lookup"><span data-stu-id="f33b3-126">The number of active connections that are not pooled.</span></span>|  
|`NumberOfPooledConnections`|<span data-ttu-id="f33b3-127">Количество активных соединений, которые управляются инфраструктурой пулов соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-127">The number of active connections that are being managed by the connection pooling infrastructure.</span></span>|  
|`NumberOfReclaimedConnections`|<span data-ttu-id="f33b3-128">Количество соединений, затребованных сборкой мусора, в которой приложение не вызывает методы `Close` и `Dispose`.</span><span class="sxs-lookup"><span data-stu-id="f33b3-128">The number of connections that have been reclaimed through garbage collection where `Close` or `Dispose` was not called by the application.</span></span> <span data-ttu-id="f33b3-129">Если соединения не закрывать и не удалять явно, производительность может снижаться.</span><span class="sxs-lookup"><span data-stu-id="f33b3-129">Not explicitly closing or disposing connections hurts performance.</span></span>|  
|`NumberOfStasisConnections`|<span data-ttu-id="f33b3-130">Количество соединений, ожидающих в настоящий момент завершения действия и поэтому доступных для приложения.</span><span class="sxs-lookup"><span data-stu-id="f33b3-130">The number of connections currently awaiting completion of an action and which are therefore unavailable for use by your application.</span></span>|  
|`SoftConnectsPerSecond`|<span data-ttu-id="f33b3-131">Количество активных соединений, извлекаемых из пула соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-131">The number of active connections being pulled from the connection pool.</span></span> <span data-ttu-id="f33b3-132">**Примечание:**  Этот счетчик производительности не включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f33b3-132">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="f33b3-133">Для включения этого счетчика производительности [см.](#ActivatingOffByDefault)</span><span class="sxs-lookup"><span data-stu-id="f33b3-133">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`SoftDisconnectsPerSecond`|<span data-ttu-id="f33b3-134">Количество активных соединений, возвращаемых в пул соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-134">The number of active connections that are being returned to the connection pool.</span></span> <span data-ttu-id="f33b3-135">**Примечание:**  Этот счетчик производительности не включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f33b3-135">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="f33b3-136">Для включения этого счетчика производительности [см.](#ActivatingOffByDefault)</span><span class="sxs-lookup"><span data-stu-id="f33b3-136">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
  
### <a name="connection-pool-groups-and-connection-pools"></a><span data-ttu-id="f33b3-137">Группы пула соединений и пулы соединений</span><span class="sxs-lookup"><span data-stu-id="f33b3-137">Connection Pool Groups and Connection Pools</span></span>  
 <span data-ttu-id="f33b3-138">При использовании проверки подлинности Windows (встроенная безопасность) необходимо следить за счетчиками `NumberOfActiveConnectionPoolGroups` и `NumberOfActiveConnectionPools`.</span><span class="sxs-lookup"><span data-stu-id="f33b3-138">When using Windows Authentication (integrated security), you must monitor both the `NumberOfActiveConnectionPoolGroups` and `NumberOfActiveConnectionPools` performance counters.</span></span> <span data-ttu-id="f33b3-139">Причина в том, что группы пулов соединений сопоставлены с уникальными строками соединений.</span><span class="sxs-lookup"><span data-stu-id="f33b3-139">The reason is that connection pool groups map to unique connection strings.</span></span> <span data-ttu-id="f33b3-140">Если используется встроенная безопасность, то пулы соединений сопоставляются со строками соединений и дополнительно создают специальные пулы для отдельных идентификаторов Windows.</span><span class="sxs-lookup"><span data-stu-id="f33b3-140">When integrated security is used, connection pools map to connection strings and additionally create separate pools for individual Windows identities.</span></span> <span data-ttu-id="f33b3-141">Например, если Кирилл и Мария, находящиеся в одном домене приложений, используют строку соединения `"Data Source=MySqlServer;Integrated Security=true"`, создается группа пула соединений для этой строки соединения и два дополнительных пула - один для Кирилла, другой для Марии.</span><span class="sxs-lookup"><span data-stu-id="f33b3-141">For example, if Fred and Julie, each within the same AppDomain, both use the connection string `"Data Source=MySqlServer;Integrated Security=true"`, a connection pool group is created for the connection string, and two additional pools are created, one for Fred and one for Julie.</span></span> <span data-ttu-id="f33b3-142">Если Джон и Марта используют строку соединения с `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`идентичным логином сервера S'L, то для **идентификации lowPrivUser** создается только один пул.</span><span class="sxs-lookup"><span data-stu-id="f33b3-142">If John and Martha use a connection string with an identical SQL Server login, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`, then only a single pool is created for the **lowPrivUser** identity.</span></span>  
  
<a name="ActivatingOffByDefault"></a>
### <a name="activating-off-by-default-counters"></a><span data-ttu-id="f33b3-143">Активация счетчиков, отключенных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f33b3-143">Activating Off-By-Default Counters</span></span>  
 <span data-ttu-id="f33b3-144">Счетчики производительности `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond` и `SoftConnectsPerSecond` отключены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f33b3-144">The performance counters `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond`, and `SoftConnectsPerSecond` are off by default.</span></span> <span data-ttu-id="f33b3-145">Чтобы включить их, добавьте в файл конфигурации приложения следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f33b3-145">Add the following information to the application's configuration file to enable them:</span></span>  
  
```xml  
<system.diagnostics>  
  <switches>  
    <add name="ConnectionPoolPerformanceCounterDetail"  
         value="4"/>  
  </switches>  
</system.diagnostics>  
```  
  
## <a name="retrieving-performance-counter-values"></a><span data-ttu-id="f33b3-146">Получение значений счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="f33b3-146">Retrieving Performance Counter Values</span></span>  
 <span data-ttu-id="f33b3-147">В следующем приложении командной строки показан способ получения значений счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="f33b3-147">The following console application shows how to retrieve performance counter values in your application.</span></span> <span data-ttu-id="f33b3-148">Чтобы возвратить данные для всех счетчиков производительности ADO.NET, соединения должны быть открыты и активны.</span><span class="sxs-lookup"><span data-stu-id="f33b3-148">Connections must be open and active for information to be returned for all of the ADO.NET performance counters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f33b3-149">В этом примере используется образец базы данных **AdventureWorks,** включенный в состав сервера S'L.</span><span class="sxs-lookup"><span data-stu-id="f33b3-149">This example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="f33b3-150">Строка соединения, представленная в образце кода, предполагает, что база данных установлена и доступна на локальном компьютере с именем экземпляра SqlExpress, и что созданы имена входа SQL Server, соответствующие представленным в строках соединения.</span><span class="sxs-lookup"><span data-stu-id="f33b3-150">The connection strings provided in the sample code assume that the database is installed and available on the local computer with an instance name of SqlExpress, and that you have created SQL Server logins that match those supplied in the connection strings.</span></span> <span data-ttu-id="f33b3-151">Имена входа SQL Server придется создать, если сервер использует параметры безопасности по умолчанию, разрешающие только проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f33b3-151">You may need to enable SQL Server logins if your server is configured using the default security settings which allow only Windows Authentication.</span></span> <span data-ttu-id="f33b3-152">При необходимости измените строки соединения, чтобы они соответствовали среде.</span><span class="sxs-lookup"><span data-stu-id="f33b3-152">Modify the connection strings as necessary to suit your environment.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f33b3-153">Пример</span><span class="sxs-lookup"><span data-stu-id="f33b3-153">Example</span></span>  
  
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

## <a name="see-also"></a><span data-ttu-id="f33b3-154">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f33b3-154">See also</span></span>

- [<span data-ttu-id="f33b3-155">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="f33b3-155">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="f33b3-156">Организация пулов соединений OLE DB, ODBC и Oracle</span><span class="sxs-lookup"><span data-stu-id="f33b3-156">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)
- <span data-ttu-id="f33b3-157">[Счетчики производительности для ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/fxk122b4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f33b3-157">[Performance Counters for ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/fxk122b4(v=vs.100))</span></span>
- [<span data-ttu-id="f33b3-158">Профилирование времени выполнения</span><span class="sxs-lookup"><span data-stu-id="f33b3-158">Runtime Profiling</span></span>](../../debug-trace-profile/runtime-profiling.md)
- <span data-ttu-id="f33b3-159">[Введение в мониторинг пороговых значений производительности](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f33b3-159">[Introduction to Monitoring Performance Thresholds](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))</span></span>
- [<span data-ttu-id="f33b3-160">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f33b3-160">ADO.NET Overview</span></span>](ado-net-overview.md)
