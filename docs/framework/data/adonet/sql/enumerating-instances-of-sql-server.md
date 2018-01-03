---
title: "Перечисление экземпляров SQL Server (ADO.NET)"
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
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 679196a6cc21705c8cc07e373a928f3c77c6befb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="bed64-102">Перечисление экземпляров SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="bed64-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="bed64-103"> позволяет приложениям находить экземпляры [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] в существующей сети.</span><span class="sxs-lookup"><span data-stu-id="bed64-103"> permits applications to find [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] instances within the current network.</span></span> <span data-ttu-id="bed64-104">Класс <xref:System.Data.Sql.SqlDataSourceEnumerator> обеспечивает доступ к этим сведениям разработчику приложения, предоставляя объект <xref:System.Data.DataTable> с данными обо всех видимых серверах.</span><span class="sxs-lookup"><span data-stu-id="bed64-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="bed64-105">Эта возвращенная таблица содержит список экземпляров сервера, доступен в сети, который совпадает со списком, предоставляемым при попытке пользователя создать новое соединение и дополняет раскрывающегося списка, содержащий все доступные серверы в **подключения Свойства** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="bed64-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="bed64-106">Отображаемые результаты не всегда являются полными.</span><span class="sxs-lookup"><span data-stu-id="bed64-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bed64-107">Как и применительно к большинству служб Windows, лучше всего использовать службу браузера SQL с наименьшими возможными правами.</span><span class="sxs-lookup"><span data-stu-id="bed64-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="bed64-108">Дополнительные сведения о службе браузера SQL и о том, как управлять ее работой, см. в электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed64-108">See [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="bed64-109">Получение экземпляра перечислителя</span><span class="sxs-lookup"><span data-stu-id="bed64-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="bed64-110">Чтобы получить таблицу с данными о доступных экземплярах [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], вначале необходимо получить перечислитель с помощью общего и (или) статического свойства <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>:</span><span class="sxs-lookup"><span data-stu-id="bed64-110">In order to retrieve the table containing information about the available [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="bed64-111">После получения статического экземпляра можно вызвать метод <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>, который возвращает таблицу <xref:System.Data.DataTable> со сведениями о доступных серверах:</span><span class="sxs-lookup"><span data-stu-id="bed64-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="bed64-112">Таблица, возвращенная в результате вызова этого метода, содержит следующие столбцы, причем все эти столбцы содержат значения `string`:</span><span class="sxs-lookup"><span data-stu-id="bed64-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="bed64-113">Столбец</span><span class="sxs-lookup"><span data-stu-id="bed64-113">Column</span></span>|<span data-ttu-id="bed64-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="bed64-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bed64-115">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="bed64-115">**ServerName**</span></span>|<span data-ttu-id="bed64-116">Имя сервера.</span><span class="sxs-lookup"><span data-stu-id="bed64-116">Name of the server.</span></span>|  
|<span data-ttu-id="bed64-117">**Имя_экземпляра**</span><span class="sxs-lookup"><span data-stu-id="bed64-117">**InstanceName**</span></span>|<span data-ttu-id="bed64-118">Имя экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="bed64-118">Name of the server instance.</span></span> <span data-ttu-id="bed64-119">Является пустым, если сервер работает в качестве экземпляра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bed64-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="bed64-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="bed64-120">**IsClustered**</span></span>|<span data-ttu-id="bed64-121">Показывает, является ли сервер частью кластера.</span><span class="sxs-lookup"><span data-stu-id="bed64-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="bed64-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="bed64-122">**Version**</span></span>|<span data-ttu-id="bed64-123">Версия сервера.</span><span class="sxs-lookup"><span data-stu-id="bed64-123">Version of the server.</span></span> <span data-ttu-id="bed64-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="bed64-124">For example:</span></span><br /><br /> <span data-ttu-id="bed64-125">-9, 00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])</span><span class="sxs-lookup"><span data-stu-id="bed64-125">-   9.00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])</span></span><br /><span data-ttu-id="bed64-126">-10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])</span><span class="sxs-lookup"><span data-stu-id="bed64-126">-   10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])</span></span><br /><span data-ttu-id="bed64-127">-10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])</span><span class="sxs-lookup"><span data-stu-id="bed64-127">-   10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])</span></span><br /><span data-ttu-id="bed64-128">-11.0.xx ([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 г.)</span><span class="sxs-lookup"><span data-stu-id="bed64-128">-   11.0.xx ([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="bed64-129">Ограничения перечисления</span><span class="sxs-lookup"><span data-stu-id="bed64-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="bed64-130">Могут перечисляться все или не все доступные серверы.</span><span class="sxs-lookup"><span data-stu-id="bed64-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="bed64-131">Содержимое списка может изменяться в зависимости от таких факторов, как время ожидания и сетевой трафик.</span><span class="sxs-lookup"><span data-stu-id="bed64-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="bed64-132">Это может привести к тому, что при двух последовательных вызовах будут получены разные списки.</span><span class="sxs-lookup"><span data-stu-id="bed64-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="bed64-133">В список входят только серверы, находящиеся в одной сети.</span><span class="sxs-lookup"><span data-stu-id="bed64-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="bed64-134">Широковещательные пакеты обычно не проходят через маршрутизаторы, поэтому некоторый сервер может отсутствовать в списке, но будет стабильно работать.</span><span class="sxs-lookup"><span data-stu-id="bed64-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="bed64-135">Сведения о серверах из списка могут включать или не включать такие дополнительные данные, как `IsClustered` и версия.</span><span class="sxs-lookup"><span data-stu-id="bed64-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="bed64-136">Это зависит от того, каким образом был получен список.</span><span class="sxs-lookup"><span data-stu-id="bed64-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="bed64-137">В списках серверов, полученных с помощью службы браузера [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], присутствует больше сведений, чем в списках серверов, найденных с помощью инфраструктуры Windows и содержащих только имена.</span><span class="sxs-lookup"><span data-stu-id="bed64-137">Servers listed through the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bed64-138">Перечисление серверов становится доступным только при выполнении процедуры с полным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="bed64-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="bed64-139">Сборки, работающие в среде с неполным доверием, не могут использовать это перечисление, даже если для них задано разрешение CAS <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="bed64-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="bed64-140">В версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] сведения для <xref:System.Data.Sql.SqlDataSourceEnumerator> предоставляются с использованием внешней службы Windows, называемой браузером SQL.</span><span class="sxs-lookup"><span data-stu-id="bed64-140">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="bed64-141">Применение этой службы разрешено по умолчанию, но администраторы могут ее выключать или запрещать, в результате чего соответствующий экземпляр сервера становится невидимым для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="bed64-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed64-142">Пример</span><span class="sxs-lookup"><span data-stu-id="bed64-142">Example</span></span>  
 <span data-ttu-id="bed64-143">Следующее консольное приложение получает сведения обо всех видимых экземплярах [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] и отображает эти сведения в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="bed64-143">The following console application retrieves information about all of the visible [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] instances and displays the information in the console window.</span></span>  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
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
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
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
  
## <a name="see-also"></a><span data-ttu-id="bed64-144">См. также</span><span class="sxs-lookup"><span data-stu-id="bed64-144">See Also</span></span>  
 [<span data-ttu-id="bed64-145">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bed64-145">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="bed64-146">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bed64-146">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
