---
title: "Получение класса DbProviderFactory"
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
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 379ec77c5a291ff0fcfa535b808f8976bb416d15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="obtaining-a-dbproviderfactory"></a><span data-ttu-id="d185c-102">Получение класса DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="d185c-102">Obtaining a DbProviderFactory</span></span>
<span data-ttu-id="d185c-103">Процесс получения <xref:System.Data.Common.DbProviderFactory> состоит из передачи сведений о поставщике данных классу <xref:System.Data.Common.DbProviderFactories>.</span><span class="sxs-lookup"><span data-stu-id="d185c-103">The process of obtaining a <xref:System.Data.Common.DbProviderFactory> involves passing information about a data provider to the <xref:System.Data.Common.DbProviderFactories> class.</span></span> <span data-ttu-id="d185c-104">На основе этих сведений метод <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> создает строго типизированную фабрику поставщика.</span><span class="sxs-lookup"><span data-stu-id="d185c-104">Based on this information, the <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> method creates a strongly typed provider factory.</span></span> <span data-ttu-id="d185c-105">Например, чтобы создать фабрику <xref:System.Data.SqlClient.SqlClientFactory>, можно передать методу `GetFactory` строку с именем поставщика, указанным в формате «System.Data.SqlClient».</span><span class="sxs-lookup"><span data-stu-id="d185c-105">For example, to create a <xref:System.Data.SqlClient.SqlClientFactory>, you can pass `GetFactory` a string with the provider name specified as "System.Data.SqlClient".</span></span> <span data-ttu-id="d185c-106">Другая перегрузка метода `GetFactory` принимает <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="d185c-106">The other overload of `GetFactory` takes a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="d185c-107">После создания фабрики поставщика можно использовать ее методы для создания дополнительных объектов.</span><span class="sxs-lookup"><span data-stu-id="d185c-107">Once you create the provider factory, you can then use its methods to create additional objects.</span></span> <span data-ttu-id="d185c-108">К методам фабрики `SqlClientFactory` относятся <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> и <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.</span><span class="sxs-lookup"><span data-stu-id="d185c-108">Some of the methods of a `SqlClientFactory` include <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A>, and <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d185c-109">Классы .NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> и <xref:System.Data.OleDb.OleDbFactory> также предоставляют похожие возможности.</span><span class="sxs-lookup"><span data-stu-id="d185c-109">The .NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory>, and <xref:System.Data.OleDb.OleDbFactory> classes also provide similar functionality.</span></span>  
  
## <a name="registering-dbproviderfactories"></a><span data-ttu-id="d185c-110">Регистрация фабрик DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="d185c-110">Registering DbProviderFactories</span></span>  
 <span data-ttu-id="d185c-111">Каждый поставщик данных .NET Framework, который поддерживает фабричный класс регистрирует сведения о конфигурации в **DbProviderFactories** раздел **machine.config** файл на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d185c-111">Each .NET Framework data provider that supports a factory-based class registers configuration information in the **DbProviderFactories** section of the **machine.config** file on the local computer.</span></span> <span data-ttu-id="d185c-112">В следующем фрагменте файла конфигурации показан синтаксис и формат для <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="d185c-112">The following configuration file fragment shows the syntax and format for <xref:System.Data.SqlClient>.</span></span>  
  
```xml  
<system.data>  
  <DbProviderFactories>  
    <add name="SqlClient Data Provider"  
     invariant="System.Data.SqlClient"   
     description=".Net Framework Data Provider for SqlServer"   
     type="System.Data.SqlClient.SqlClientFactory, System.Data,   
     Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
    />  
  </DbProviderFactories>  
</system.data>  
```  
  
 <span data-ttu-id="d185c-113">**Инвариантный** атрибут определяет базовый поставщик данных.</span><span class="sxs-lookup"><span data-stu-id="d185c-113">The **invariant** attribute identifies the underlying data provider.</span></span> <span data-ttu-id="d185c-114">Этот трехкомпонентный синтаксис имени также применяется при создании новой фабрики и для определения поставщика в файле конфигурации, чтобы имя поставщика вместе со связанной с ним строкой соединения можно было получать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d185c-114">This three-part naming syntax is also used when creating a new factory and for identifying the provider in an application configuration file so that the provider name, along with its associated connection string, can be retrieved at run time.</span></span>  
  
## <a name="retrieving-provider-information"></a><span data-ttu-id="d185c-115">Извлечения сведений поставщика</span><span class="sxs-lookup"><span data-stu-id="d185c-115">Retrieving Provider Information</span></span>  
 <span data-ttu-id="d185c-116">Сведения обо всех поставщиках, установленных на локальном компьютере, можно получить с помощью метода <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>.</span><span class="sxs-lookup"><span data-stu-id="d185c-116">You can retrieve information about all of the data providers installed on the local computer by using the <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> method.</span></span> <span data-ttu-id="d185c-117">Он возвращает <xref:System.Data.DataTable> с именем **DbProviderFactories** , содержащий столбцы, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d185c-117">It returns a <xref:System.Data.DataTable> named **DbProviderFactories** that contains the columns described in the following table.</span></span>  
  
|<span data-ttu-id="d185c-118">Порядковый номер столбца</span><span class="sxs-lookup"><span data-stu-id="d185c-118">Column ordinal</span></span>|<span data-ttu-id="d185c-119">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="d185c-119">Column name</span></span>|<span data-ttu-id="d185c-120">Пример результата</span><span class="sxs-lookup"><span data-stu-id="d185c-120">Example output</span></span>|<span data-ttu-id="d185c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d185c-121">Description</span></span>|  
|--------------------|-----------------|--------------------|-----------------|  
|<span data-ttu-id="d185c-122">0</span><span class="sxs-lookup"><span data-stu-id="d185c-122">0</span></span>|<span data-ttu-id="d185c-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="d185c-123">**Name**</span></span>|<span data-ttu-id="d185c-124">Поставщик данных SqlClient</span><span class="sxs-lookup"><span data-stu-id="d185c-124">SqlClient Data Provider</span></span>|<span data-ttu-id="d185c-125">Понятное имя поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="d185c-125">Readable name for the data provider</span></span>|  
|<span data-ttu-id="d185c-126">1</span><span class="sxs-lookup"><span data-stu-id="d185c-126">1</span></span>|<span data-ttu-id="d185c-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d185c-127">**Description**</span></span>|<span data-ttu-id="d185c-128">Поставщик данных .NET Framework для SqlServer</span><span class="sxs-lookup"><span data-stu-id="d185c-128">.Net Framework Data Provider for SqlServer</span></span>|<span data-ttu-id="d185c-129">Понятное описание поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="d185c-129">Readable description of the data provider</span></span>|  
|<span data-ttu-id="d185c-130">2</span><span class="sxs-lookup"><span data-stu-id="d185c-130">2</span></span>|<span data-ttu-id="d185c-131">**InvariantName**</span><span class="sxs-lookup"><span data-stu-id="d185c-131">**InvariantName**</span></span>|<span data-ttu-id="d185c-132">System.Data.SqlClient</span><span class="sxs-lookup"><span data-stu-id="d185c-132">System.Data.SqlClient</span></span>|<span data-ttu-id="d185c-133">Имя, которое можно использовать программно, чтобы ссылаться на поставщик данных.</span><span class="sxs-lookup"><span data-stu-id="d185c-133">Name that can be used programmatically to refer to the data provider</span></span>|  
|<span data-ttu-id="d185c-134">3</span><span class="sxs-lookup"><span data-stu-id="d185c-134">3</span></span>|<span data-ttu-id="d185c-135">**AssemblyQualifiedName**</span><span class="sxs-lookup"><span data-stu-id="d185c-135">**AssemblyQualifiedName**</span></span>|<span data-ttu-id="d185c-136">System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="d185c-136">System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</span></span>|<span data-ttu-id="d185c-137">Полное имя фабричного класса, которое содержит достаточно данных для создания экземпляров объектов.</span><span class="sxs-lookup"><span data-stu-id="d185c-137">Fully qualified name of the factory class, which contains enough information to instantiate the object</span></span>|  
  
 <span data-ttu-id="d185c-138">Эту таблицу `DataTable` можно применять, чтобы дать пользователям возможность выбирать <xref:System.Data.DataRow> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d185c-138">This `DataTable` can be used to enable a user to select a <xref:System.Data.DataRow> at run time.</span></span> <span data-ttu-id="d185c-139">Выбранная строка `DataRow` затем может передаваться методу <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> для создания строго типизированной фабрики <xref:System.Data.Common.DbProviderFactory>.</span><span class="sxs-lookup"><span data-stu-id="d185c-139">The selected `DataRow` can then be passed to the <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> method to create a strongly typed <xref:System.Data.Common.DbProviderFactory>.</span></span> <span data-ttu-id="d185c-140">Выбранная строка <xref:System.Data.DataRow> затем может передаваться методу `GetFactory` для создания нужного объекта `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="d185c-140">A selected <xref:System.Data.DataRow> can be passed to the `GetFactory` method to create the desired `DbProviderFactory` object.</span></span>  
  
## <a name="listing-the-installed-provider-factory-classes"></a><span data-ttu-id="d185c-141">Перечисление классов установленной фабрики поставщика</span><span class="sxs-lookup"><span data-stu-id="d185c-141">Listing the Installed Provider Factory Classes</span></span>  
 <span data-ttu-id="d185c-142">В этом примере демонстрируется, как использовать метод <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> для возвращения таблицы <xref:System.Data.DataTable> со сведениями об установленных поставщиках.</span><span class="sxs-lookup"><span data-stu-id="d185c-142">This example demonstrates how to use the <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> method to return a <xref:System.Data.DataTable> containing information about the installed providers.</span></span> <span data-ttu-id="d185c-143">В коде выполняется просмотр каждой строки в таблице `DataTable` с выводом сведений по каждому поставщику в консольном окне.</span><span class="sxs-lookup"><span data-stu-id="d185c-143">The code iterates through each row in the `DataTable`, displaying information for each installed provider in the console window.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## <a name="using-application-configuration-files-to-store-factory-information"></a><span data-ttu-id="d185c-144">Использование файлов конфигурации приложений для хранения сведений о фабрике</span><span class="sxs-lookup"><span data-stu-id="d185c-144">Using Application Configuration Files to Store Factory Information</span></span>  
 <span data-ttu-id="d185c-145">Модель использования фабрик включает хранение поставщика и данные строки подключения в файле конфигурации приложения, например **app.config** для приложения Windows, и **web.config**  для приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d185c-145">The design pattern used for working with factories entails storing provider and connection string information in an application configuration file, such as **app.config** for a Windows application, and **web.config** for an ASP.NET application.</span></span>  
  
 <span data-ttu-id="d185c-146">В следующем фрагменте файла конфигурации демонстрируется, как сохранять две именованные строки соединения «NorthwindSQL» для соединения с базой данных Northwind в SQL Server и «NorthwindAccess» для соединения с базой данных Northwind в Access/Jet.</span><span class="sxs-lookup"><span data-stu-id="d185c-146">The following configuration file fragment demonstrates how to save two named connection strings, "NorthwindSQL" for a connection to the Northwind database in SQL Server, and "NorthwindAccess" for a connection to the Northwind database in Access/Jet.</span></span> <span data-ttu-id="d185c-147">**Инвариантный** имя будет использоваться для **providerName** атрибута.</span><span class="sxs-lookup"><span data-stu-id="d185c-147">The **invariant** name is used for the **providerName** attribute.</span></span>  
  
```xml  
<configuration>  
  <connectionStrings>  
    <clear/>  
    <add name="NorthwindSQL"   
     providerName="System.Data.SqlClient"   
     connectionString=  
     "Data Source=MSSQL1;Initial Catalog=Northwind;Integrated Security=true"  
    />  
  
    <add name="NorthwindAccess"   
     providerName="System.Data.OleDb"   
     connectionString=  
     "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Data\Northwind.mdb;"  
    />  
  </connectionStrings>  
</configuration>  
```  
  
### <a name="retrieving-a-connection-string-by-provider-name"></a><span data-ttu-id="d185c-148">Извлечение строки соединения по имени поставщика</span><span class="sxs-lookup"><span data-stu-id="d185c-148">Retrieving a Connection String by Provider Name</span></span>  
 <span data-ttu-id="d185c-149">Чтобы создать фабрику поставщика, необходимо предоставить строку соединения, а также имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="d185c-149">In order to create a provider factory, you must supply a connection string as well as the provider name.</span></span> <span data-ttu-id="d185c-150">В этом примере показано, как получить строку соединения из файла конфигурации приложения путем передачи имени поставщика в неизменяемом формате «*System.Data.ProviderName*».</span><span class="sxs-lookup"><span data-stu-id="d185c-150">This example demonstrates how to retrieve a connection string from an application configuration file by passing the provider name in the invariant format "*System.Data.ProviderName*".</span></span> <span data-ttu-id="d185c-151">В коде выполняется просмотр элементов коллекции <xref:System.Configuration.ConnectionStringSettingsCollection>.</span><span class="sxs-lookup"><span data-stu-id="d185c-151">The code iterates through the <xref:System.Configuration.ConnectionStringSettingsCollection>.</span></span> <span data-ttu-id="d185c-152">В случае успеха возвращается <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>; в противном случае - `null` (`Nothing` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d185c-152">It returns the <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> on success; otherwise `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="d185c-153">При наличии нескольких записей для поставщика возвращается первая найденная.</span><span class="sxs-lookup"><span data-stu-id="d185c-153">If there are multiple entries for a provider, the first one found is returned.</span></span> <span data-ttu-id="d185c-154">Дополнительные сведения и примеры получении строк соединения из файлов конфигурации см. в разделе [строки соединения и файлы конфигурации](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="d185c-154">For more information and examples of retrieving connection strings from configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d185c-155">Для выполнения этого кода необходима ссылка на файл `System.Configuration.dll`.</span><span class="sxs-lookup"><span data-stu-id="d185c-155">A reference to `System.Configuration.dll` is required in order for the code to run.</span></span>  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a><span data-ttu-id="d185c-156">Создание DbProviderFactory и DbConnection</span><span class="sxs-lookup"><span data-stu-id="d185c-156">Creating the DbProviderFactory and DbConnection</span></span>  
 <span data-ttu-id="d185c-157">В этом примере демонстрируется создание <xref:System.Data.Common.DbProviderFactory> и <xref:System.Data.Common.DbConnection> путем передачи имени поставщика в формате «*System.Data.ProviderName*» и строки соединения.</span><span class="sxs-lookup"><span data-stu-id="d185c-157">This example demonstrates how to create a <xref:System.Data.Common.DbProviderFactory> and <xref:System.Data.Common.DbConnection> object by passing it the provider name in the format "*System.Data.ProviderName*" and a connection string.</span></span> <span data-ttu-id="d185c-158">В случае успеха возвращается объект `DbConnection`; в случае любой ошибки - `null` (`Nothing` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d185c-158">A `DbConnection` object is returned on success; `null` (`Nothing` in Visual Basic) on any error.</span></span>  
  
 <span data-ttu-id="d185c-159">Этот код получает `DbProviderFactory` путем вызова <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>.</span><span class="sxs-lookup"><span data-stu-id="d185c-159">The code obtains the `DbProviderFactory` by calling <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>.</span></span> <span data-ttu-id="d185c-160">Затем метод <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> создает объект <xref:System.Data.Common.DbConnection>, а свойству <xref:System.Data.Common.DbConnection.ConnectionString%2A> присваивается значение строки соединения.</span><span class="sxs-lookup"><span data-stu-id="d185c-160">Then the <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> method creates the <xref:System.Data.Common.DbConnection> object and the <xref:System.Data.Common.DbConnection.ConnectionString%2A> property is set to the connection string.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d185c-161">См. также</span><span class="sxs-lookup"><span data-stu-id="d185c-161">See Also</span></span>  
 [<span data-ttu-id="d185c-162">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="d185c-162">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="d185c-163">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="d185c-163">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="d185c-164">Использование классов конфигурации</span><span class="sxs-lookup"><span data-stu-id="d185c-164">Using the Configuration Classes</span></span>](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [<span data-ttu-id="d185c-165">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d185c-165">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
