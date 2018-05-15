---
title: Действия доступа к базе данных
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: e9c7627738d3c5313a4f3e6e4451daf78b87839a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="database-access-activities"></a><span data-ttu-id="dfa7b-102">Действия доступа к базе данных</span><span class="sxs-lookup"><span data-stu-id="dfa7b-102">Database Access Activities</span></span>
<span data-ttu-id="dfa7b-103">Действия доступа к базе данных позволяют обращаться к базе данных из рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="dfa7b-104">Эти действия позволяют доступ к базам данных, чтобы вернуть или изменить сведения, а также использовать [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) для доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfa7b-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dfa7b-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dfa7b-107">Если этот каталог не существует, перейдите на загрузки страницы, чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dfa7b-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`  
  
## <a name="database-activities"></a><span data-ttu-id="dfa7b-109">Действия базы данных</span><span class="sxs-lookup"><span data-stu-id="dfa7b-109">Database Activities</span></span>  
 <span data-ttu-id="dfa7b-110">В следующих разделах приведен список действий, входящих в этот образец.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-110">The following sections detail the list of activities included in this sample.</span></span>  
  
## <a name="dbupdate"></a><span data-ttu-id="dfa7b-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="dfa7b-111">DbUpdate</span></span>  
 <span data-ttu-id="dfa7b-112">Выполняет SQL-запрос, который реализует изменение в базе данных (вставку, обновление, удаление или иные изменения).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>  
  
 <span data-ttu-id="dfa7b-113">Этот класс выполняет работу асинхронно (он является производным от класса <xref:System.Activities.AsyncCodeActivity> и использует его возможности для асинхронной работы).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>  
  
 <span data-ttu-id="dfa7b-114">Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="dfa7b-115">Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="dfa7b-116">После выполнения `DbUpdate` количество измененных записей возвращается в свойстве `AffectedRecords`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>  
  
```  
Public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }       
}  
```  
  
|<span data-ttu-id="dfa7b-117">Аргумент</span><span class="sxs-lookup"><span data-stu-id="dfa7b-117">Argument</span></span>|<span data-ttu-id="dfa7b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="dfa7b-118">Description</span></span>|  
|-|-|  
|<span data-ttu-id="dfa7b-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-119">ProviderName</span></span>|<span data-ttu-id="dfa7b-120">Неизменяемое имя поставщика ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="dfa7b-121">Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-122">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="dfa7b-122">ConnectionString</span></span>|<span data-ttu-id="dfa7b-123">Строка соединения для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-123">Connection string to connect to the database.</span></span> <span data-ttu-id="dfa7b-124">Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-124">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-125">ConfigName</span></span>|<span data-ttu-id="dfa7b-126">Имя раздела файла конфигурации, в котором хранятся сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="dfa7b-127">Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="dfa7b-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="dfa7b-128">CommandType</span></span>|<span data-ttu-id="dfa7b-129">Тип выполняемой команды <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-130">Sql</span><span class="sxs-lookup"><span data-stu-id="dfa7b-130">Sql</span></span>|<span data-ttu-id="dfa7b-131">Выполняемая команда SQL.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-131">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfa7b-132">Parameters</span></span>|<span data-ttu-id="dfa7b-133">Коллекция параметров SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-133">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="dfa7b-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="dfa7b-134">AffectedRecords</span></span>|<span data-ttu-id="dfa7b-135">Количество записей, на которые повлияла последняя операция.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-135">Number of records affected by the last operation.</span></span>|  
  
## <a name="dbqueryscalar"></a><span data-ttu-id="dfa7b-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="dfa7b-136">DbQueryScalar</span></span>  
 <span data-ttu-id="dfa7b-137">Выполняет запрос, возвращающий единичное значение данные из базы данных.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-137">Executes a query that retrieves a single value from the database.</span></span>  
  
 <span data-ttu-id="dfa7b-138">Этот класс выполняет работу асинхронно (он является производным от класса <xref:System.Activities.AsyncCodeActivity%601> и использует его возможности для асинхронной работы).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>  
  
 <span data-ttu-id="dfa7b-139">Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="dfa7b-140">Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="dfa7b-141">После `DbQueryScalar` — выполняется, скалярное значение возвращается в `Result``out` аргумент (типа `TResult`, который определен в базовом классе <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>  
  
```  
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
}  
```  
  
|<span data-ttu-id="dfa7b-142">Аргумент</span><span class="sxs-lookup"><span data-stu-id="dfa7b-142">Argument</span></span>|<span data-ttu-id="dfa7b-143">Описание</span><span class="sxs-lookup"><span data-stu-id="dfa7b-143">Description</span></span>|  
|-|-|  
|<span data-ttu-id="dfa7b-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-144">ProviderName</span></span>|<span data-ttu-id="dfa7b-145">Неизменяемое имя поставщика ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="dfa7b-146">Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-147">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="dfa7b-147">ConnectionString</span></span>|<span data-ttu-id="dfa7b-148">Строка соединения для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-148">Connection string to connect to the database.</span></span> <span data-ttu-id="dfa7b-149">Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-149">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-150">ConfigName</span></span>|<span data-ttu-id="dfa7b-151">Имя раздела файла конфигурации, в котором хранятся сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="dfa7b-152">Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="dfa7b-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="dfa7b-153">CommandType</span></span>|<span data-ttu-id="dfa7b-154">Тип выполняемой команды <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-155">Sql</span><span class="sxs-lookup"><span data-stu-id="dfa7b-155">Sql</span></span>|<span data-ttu-id="dfa7b-156">Выполняемая команда SQL.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-156">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-157">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfa7b-157">Parameters</span></span>|<span data-ttu-id="dfa7b-158">Коллекция параметров SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-158">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="dfa7b-159">Результат</span><span class="sxs-lookup"><span data-stu-id="dfa7b-159">Result</span></span>|<span data-ttu-id="dfa7b-160">Скаляр, полученный после выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="dfa7b-161">Этот аргумент имеет тип `TResult`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-161">This argument is of type `TResult`.</span></span>|  
  
## <a name="dbquery"></a><span data-ttu-id="dfa7b-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="dfa7b-162">DbQuery</span></span>  
 <span data-ttu-id="dfa7b-163">Выполняет запрос, который возвращает список объектов.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="dfa7b-164">После выполнения запроса выполняется функция сопоставления (это может быть <xref:System.Func%601> < `DbDataReader`, `TResult`> или <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="dfa7b-165">Эта функция сопоставления получает запись в `DbDataReader` и сопоставляет ее возвращаемому объекту.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>  
  
 <span data-ttu-id="dfa7b-166">Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="dfa7b-167">Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="dfa7b-168">Результаты SQL-запроса извлекаются с использованием `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="dfa7b-169">Действие выполняет перебор по `DbDataReader` и сопоставляет строки в `DbDataReader` с экземпляром `TResult`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="dfa7b-170">Пользователь `DbQuery` должен предоставить код сопоставления, что это можно сделать двумя способами: с помощью <xref:System.Func%601> < `DbDataReader`, `TResult`> или <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="dfa7b-171">В первом случае сопоставление совершается на одном шаге выполнения.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="dfa7b-172">Поэтому этот способ быстрее, но сериализация в XAML невозможна.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="dfa7b-173">Во втором случае сопоставление выполняется в несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="dfa7b-174">Поэтому может потребоваться больше времени, зато возможны сериализация в XAML и декларативное авторство (любое существующее действие может участвовать в сопоставлении).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>  
  
```  
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [OverloadGroup("DirectMapping")]  
    [DefaultValue(null)]  
    public Func<DbDataReader, TResult> Mapper { get; set; }  
  
    [OverloadGroup("MultiplePulseMapping")]  
    [DefaultValue(null)]  
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }  
}  
```  
  
|<span data-ttu-id="dfa7b-175">Аргумент</span><span class="sxs-lookup"><span data-stu-id="dfa7b-175">Argument</span></span>|<span data-ttu-id="dfa7b-176">Описание</span><span class="sxs-lookup"><span data-stu-id="dfa7b-176">Description</span></span>|  
|-|-|  
|<span data-ttu-id="dfa7b-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-177">ProviderName</span></span>|<span data-ttu-id="dfa7b-178">Неизменяемое имя поставщика ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="dfa7b-179">Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-180">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="dfa7b-180">ConnectionString</span></span>|<span data-ttu-id="dfa7b-181">Строка соединения для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-181">Connection string to connect to the database.</span></span> <span data-ttu-id="dfa7b-182">Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-182">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-183">ConfigName</span></span>|<span data-ttu-id="dfa7b-184">Имя раздела файла конфигурации, в котором хранятся сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="dfa7b-185">Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="dfa7b-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="dfa7b-186">CommandType</span></span>|<span data-ttu-id="dfa7b-187">Тип выполняемой команды <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-188">Sql</span><span class="sxs-lookup"><span data-stu-id="dfa7b-188">Sql</span></span>|<span data-ttu-id="dfa7b-189">Выполняемая команда SQL.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-189">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-190">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfa7b-190">Parameters</span></span>|<span data-ttu-id="dfa7b-191">Коллекция параметров SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-191">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="dfa7b-192">Сопоставитель</span><span class="sxs-lookup"><span data-stu-id="dfa7b-192">Mapper</span></span>|<span data-ttu-id="dfa7b-193">Функция сопоставления (<xref:System.Func%601><`DbDataReader`, `TResult`>), принимает запись в `DataReader` полученном в результате выполнения запроса и возвращает экземпляр объекта типа `TResult` для добавления `Result` коллекции.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="dfa7b-194">В этом случае сопоставление совершается на одном шаге выполнения, но декларативное авторство с использованием конструктора невозможно.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|  
|<span data-ttu-id="dfa7b-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="dfa7b-195">MapperFunc</span></span>|<span data-ttu-id="dfa7b-196">Функция сопоставления (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>), принимает запись в `DataReader` полученном в результате выполнения запроса и возвращает экземпляр объекта типа `TResult` для добавления `Result` коллекции.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="dfa7b-197">В этом случае сопоставление совершается в несколько шагов выполнения.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="dfa7b-198">Для этой функции возможны сериализация в XAML и декларативное авторство (любое существующее действие может участвовать в сопоставлении).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|  
|<span data-ttu-id="dfa7b-199">Результат</span><span class="sxs-lookup"><span data-stu-id="dfa7b-199">Result</span></span>|<span data-ttu-id="dfa7b-200">Список объектов, полученный в результате выполнения запроса и выполнения функции сопоставления для каждой записи в `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|  
  
## <a name="dbquerydataset"></a><span data-ttu-id="dfa7b-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="dfa7b-201">DbQueryDataSet</span></span>  
 <span data-ttu-id="dfa7b-202">Выполняет запрос, который возвращает <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="dfa7b-203">Этот класс выполняет работу асинхронно.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="dfa7b-204">Он является производным от <xref:System.Activities.AsyncCodeActivity> < `TResult`> и использует его асинхронные возможности.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>  
  
 <span data-ttu-id="dfa7b-205">Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="dfa7b-206">Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="dfa7b-207">После `DbQueryDataSet` выполняется `DataSet` возвращается в `Result``out` аргумент (типа `TResult`, который определен в базовом классе <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>  
  
```  
public class DbQueryDataSet : AsyncCodeActivity<DataSet>  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
}  
```  
  
|<span data-ttu-id="dfa7b-208">Аргумент</span><span class="sxs-lookup"><span data-stu-id="dfa7b-208">Argument</span></span>|<span data-ttu-id="dfa7b-209">Описание</span><span class="sxs-lookup"><span data-stu-id="dfa7b-209">Description</span></span>|  
|-|-|  
|<span data-ttu-id="dfa7b-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-210">ProviderName</span></span>|<span data-ttu-id="dfa7b-211">Неизменяемое имя поставщика ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="dfa7b-212">Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-213">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="dfa7b-213">ConnectionString</span></span>|<span data-ttu-id="dfa7b-214">Строка соединения для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-214">Connection string to connect to the database.</span></span> <span data-ttu-id="dfa7b-215">Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-215">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="dfa7b-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="dfa7b-216">ConfigName</span></span>|<span data-ttu-id="dfa7b-217">Имя раздела файла конфигурации, в котором хранятся сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="dfa7b-218">Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="dfa7b-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="dfa7b-219">CommandType</span></span>|<span data-ttu-id="dfa7b-220">Тип выполняемой команды <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-221">Sql</span><span class="sxs-lookup"><span data-stu-id="dfa7b-221">Sql</span></span>|<span data-ttu-id="dfa7b-222">Выполняемая команда SQL.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-222">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="dfa7b-223">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfa7b-223">Parameters</span></span>|<span data-ttu-id="dfa7b-224">Коллекция параметров SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-224">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="dfa7b-225">Результат</span><span class="sxs-lookup"><span data-stu-id="dfa7b-225">Result</span></span>|<span data-ttu-id="dfa7b-226"><xref:System.Data.DataSet>, полученный после выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|  
  
## <a name="configuring-connection-information"></a><span data-ttu-id="dfa7b-227">Настройка сведений о соединении</span><span class="sxs-lookup"><span data-stu-id="dfa7b-227">Configuring Connection Information</span></span>  
 <span data-ttu-id="dfa7b-228">Все DbActivities используют одни и те же параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="dfa7b-229">Их можно настроить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-229">They can be configured in two ways:</span></span>  
  
-   <span data-ttu-id="dfa7b-230">`ConnectionString + InvariantName`: Укажите неизменяемое имя поставщика ADO.NET и строку соединения.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<DateTime>()  
    {  
        ProviderName = "System.Data.SqlClient",  
        ConnectionString = @"Data Source=.\SQLExpress;  
                             Initial Catalog=DbActivitiesSample;  
                             Integrated Security=True",  
        Sql = "SELECT GetDate()"  
    };  
    ```  
  
-   <span data-ttu-id="dfa7b-231">`ConfigName`: Укажите имя раздела конфигурации, в котором содержатся сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>  
  
    ```xml  
    <connectionStrings>      
        <add name="DbActivitiesSample"  
             providerName="System.Data.SqlClient"  
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>  
      </connectionStrings>  
    ```  
  
-   <span data-ttu-id="dfa7b-232">В действии:</span><span class="sxs-lookup"><span data-stu-id="dfa7b-232">In the activity:</span></span>  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<int>()  
    {                  
        ConfigName = "DbActivitiesSample",  
        Sql = "SELECT COUNT(*) FROM Roles"  
    };  
    ```  
  
## <a name="running-this-sample"></a><span data-ttu-id="dfa7b-233">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="dfa7b-233">Running this sample</span></span>  
  
### <a name="setup-instructions"></a><span data-ttu-id="dfa7b-234">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="dfa7b-234">Setup instructions</span></span>  
 <span data-ttu-id="dfa7b-235">Этот образец использует базу данных.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-235">This sample uses a database.</span></span> <span data-ttu-id="dfa7b-236">Вместе с образцом предоставляется скрипт установки и загрузки (Setup.cmd).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="dfa7b-237">Этот файл необходимо выполнить из командной строки.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-237">You must execute that file using the command prompt.</span></span>  
  
 <span data-ttu-id="dfa7b-238">Скрипт Setup.cmd вызывает файл скрипта CreateDb.sql, который содержит команды SQL и выполняет следующие операции.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>  
  
-   <span data-ttu-id="dfa7b-239">Создает базу данных под именем DbActivitiesSample.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-239">Creates a database called DbActivitiesSample.</span></span>  
  
-   <span data-ttu-id="dfa7b-240">Создает таблицу Roles.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-240">Creates the Roles table.</span></span>  
  
-   <span data-ttu-id="dfa7b-241">Создает таблицу Employees.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-241">Creates Employees table.</span></span>  
  
-   <span data-ttu-id="dfa7b-242">Вставляет 3 записи в таблицу Roles.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-242">Inserts three records into the Roles table.</span></span>  
  
-   <span data-ttu-id="dfa7b-243">Вставляет двенадцать записей в таблицу Employees.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-243">Inserts twelve records into the Employees table.</span></span>  
  
##### <a name="to-run-setupcmd"></a><span data-ttu-id="dfa7b-244">Запуск команды Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="dfa7b-244">To run Setup.cmd</span></span>  
  
1.  <span data-ttu-id="dfa7b-245">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-245">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="dfa7b-246">Перейдите в папку образца DbActivities.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-246">Go to the DbActivities sample folder.</span></span>  
  
3.  <span data-ttu-id="dfa7b-247">Введите «setup.cmd» и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-247">Type "setup.cmd" and press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfa7b-248">Скрипт Setup.cmd пытается установить образец базы данных на экземпляр SQLExpress на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="dfa7b-249">Если образец необходимо установить на другом экземпляре сервера SQL, измените Setup.cmd, указав другое имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>  
  
##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="dfa7b-250">Удаление образца базы данных</span><span class="sxs-lookup"><span data-stu-id="dfa7b-250">To uninstall the sample database</span></span>  
  
1.  <span data-ttu-id="dfa7b-251">Выполните в командной строке файл Cleanup.cmd из папки образца.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>  
  
##### <a name="to-run-the-sample"></a><span data-ttu-id="dfa7b-252">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="dfa7b-252">To run the sample</span></span>  
  
1.  <span data-ttu-id="dfa7b-253">Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfa7b-253">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]</span></span>  
  
2.  <span data-ttu-id="dfa7b-254">Для компиляции решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-254">To compile the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="dfa7b-255">Чтобы запустить образец без отладки, нажмите сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-255">To run the sample without debugging, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfa7b-256">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dfa7b-257">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dfa7b-257">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dfa7b-258">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dfa7b-259">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dfa7b-259">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
