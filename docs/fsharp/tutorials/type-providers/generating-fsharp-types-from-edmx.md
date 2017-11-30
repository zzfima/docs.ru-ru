---
title: "Пошаговое руководство. Создание типов F# из файла схемы EDMX (F#)"
description: "Узнайте, как создание типов F # для данных, представленных в модели данных сущности (EDM) в F # 3.0, где схема задана в EDMX-файл."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 5c59911f5f880493080ef1838bc015045ce4336a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a><span data-ttu-id="cc76b-104">Пошаговое руководство. Создание типов F# из файла схемы EDMX</span><span class="sxs-lookup"><span data-stu-id="cc76b-104">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>

> [!NOTE]
<span data-ttu-id="cc76b-105">В этом руководстве, была написана для F # 3.0 и будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="cc76b-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="cc76b-106">Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](http://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="cc76b-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="cc76b-107">Справочные ссылки API, вы перейдете MSDN.</span><span class="sxs-lookup"><span data-stu-id="cc76b-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="cc76b-108">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="cc76b-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="cc76b-109">В этом пошаговом руководстве для F# 3.0 показано создание типов для данных, представляемых моделью EDM, схема для которой определена в EDMX-файле.</span><span class="sxs-lookup"><span data-stu-id="cc76b-109">This walkthrough for F# 3.0 shows you how to create types for data that is represented by the Entity Data Model (EDM), the schema for which is specified in an .edmx file.</span></span> <span data-ttu-id="cc76b-110">В этом пошаговом руководстве также описано использование поставщика типов EdmxFile.</span><span class="sxs-lookup"><span data-stu-id="cc76b-110">This walkthrough also shows how to use the EdmxFile type provider.</span></span> <span data-ttu-id="cc76b-111">Сначала рассмотрим, не является ли поставщик типов SqlEntityConnection более подходящим поставщиком.</span><span class="sxs-lookup"><span data-stu-id="cc76b-111">Before you begin, consider whether a SqlEntityConnection type provider is a more appropriate type provider option.</span></span> <span data-ttu-id="cc76b-112">Поставщик типов SqlEntityConnection оптимально подходит для сценариев, где имеется база данных реального времени, к которой можно подключаться на этапе разработки проекта, и у вас нет возражений против указания строки подключения во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="cc76b-112">The SqlEntityConnection type provider works best for scenarios where you have a live database that you can connect to during the development phase of your project, and you do not mind specifying the connection string at compile time.</span></span> <span data-ttu-id="cc76b-113">Однако этот поставщик типов предоставляет меньше функциональных возможностей базы данных по сравнению с поставщиком типов EdmxFile.</span><span class="sxs-lookup"><span data-stu-id="cc76b-113">However, this type provider is also limited in that it doesn't expose as much database functionality as the EdmxFile type provider.</span></span> <span data-ttu-id="cc76b-114">Кроме того, при отсутствии подключения к базе данных реального времени для проекта базы данных, использующего модель EDM, можно использовать EDMX-файл, чтобы реализовать код для базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-114">Also, if you don't have a live database connection for a database project that uses the Entity Data Model, you can use the .edmx file to code against the database.</span></span> <span data-ttu-id="cc76b-115">При использовании поставщика типов EdmxFile компилятор F# выполняет программу EdmGen.exe для создания типов, которые он предоставляет.</span><span class="sxs-lookup"><span data-stu-id="cc76b-115">When you use the EdmxFile type provider, the F# compiler runs EdmGen.exe to generate the types that it provides.</span></span>

<span data-ttu-id="cc76b-116">В этом пошаговом руководстве рассмотрены перечисленные ниже задачи, которые необходимо выполнить в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="cc76b-116">This walkthrough illustrates the following tasks, which you must perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="cc76b-117">Создание EDMX-файла</span><span class="sxs-lookup"><span data-stu-id="cc76b-117">Creating an EDMX file</span></span>
<br />

- <span data-ttu-id="cc76b-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="cc76b-118">Creating the project</span></span>
<br />

- <span data-ttu-id="cc76b-119">Поиск или создание строки подключения модели EDM</span><span class="sxs-lookup"><span data-stu-id="cc76b-119">Finding or creating the entity data model connection string</span></span>
<br />

- <span data-ttu-id="cc76b-120">Настройка поставщика типов</span><span class="sxs-lookup"><span data-stu-id="cc76b-120">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="cc76b-121">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="cc76b-121">Querying the data</span></span>
<br />

- <span data-ttu-id="cc76b-122">Вызов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="cc76b-122">Calling a stored procedure</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="cc76b-123">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cc76b-123">Prerequisites</span></span>

## <a name="creating-an-edmx-file"></a><span data-ttu-id="cc76b-124">Создание EDMX-файла</span><span class="sxs-lookup"><span data-stu-id="cc76b-124">Creating an EDMX file</span></span>
<span data-ttu-id="cc76b-125">Если EDMX-файл уже есть, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="cc76b-125">If you already have an EDMX file, you can skip this step.</span></span>


#### <a name="to-create-an-edmx-file"></a><span data-ttu-id="cc76b-126">Создание EDMX-файла</span><span class="sxs-lookup"><span data-stu-id="cc76b-126">To create an EDMX file</span></span>

- <span data-ttu-id="cc76b-127">Если у вас еще нет EDMX-файла, можно выполнить действия, в конце этого пошагового руководства в разделе [Настройка модели EDM](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span><span class="sxs-lookup"><span data-stu-id="cc76b-127">If you don't already have an EDMX file, you can follow the instructions at the end of this walkthrough in the step [Configuring the Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span></span>
<br />

## <a name="creating-the-project"></a><span data-ttu-id="cc76b-128">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="cc76b-128">Creating the project</span></span>
<span data-ttu-id="cc76b-129">На этом шаге создается проект и добавляются необходимые ссылки на него для использования поставщика типов EDMX.</span><span class="sxs-lookup"><span data-stu-id="cc76b-129">In this step, you create a project and add appropriate references to it to use the EDMX type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="cc76b-130">Действия для создания и настройки проекта F#</span><span class="sxs-lookup"><span data-stu-id="cc76b-130">To create and set up an F# project</span></span>

1. <span data-ttu-id="cc76b-131">Закройте предыдущий проект, создайте другой проект и назовите его SchoolEDM.</span><span class="sxs-lookup"><span data-stu-id="cc76b-131">Close the previous project, create another project, and name it SchoolEDM.</span></span>
<br />

2. <span data-ttu-id="cc76b-132">В **обозревателе решений**, откройте контекстное меню для **ссылки**и нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="cc76b-132">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="cc76b-133">В **сборки** области, выберите **Framework** узла.</span><span class="sxs-lookup"><span data-stu-id="cc76b-133">In the **Assemblies** area, choose the **Framework** node.</span></span>
<br />

4. <span data-ttu-id="cc76b-134">В списке доступных сборок выберите **System.Data.Entity** и **System.Data.Linq** сборки, а затем выберите **добавить** кнопку, чтобы добавить ссылки на эти сборки в проект.</span><span class="sxs-lookup"><span data-stu-id="cc76b-134">In the list of available assemblies, choose the **System.Data.Entity** and **System.Data.Linq** assemblies, and then choose the **Add** button to add references to these assemblies to your project.</span></span>
<br />

5. <span data-ttu-id="cc76b-135">В **сборки** выберите **расширения** узла.</span><span class="sxs-lookup"><span data-stu-id="cc76b-135">In the **Assemblies** area, select the **Extensions** node.</span></span>
<br />

6. <span data-ttu-id="cc76b-136">В списке доступных расширений добавьте ссылку на сборку FSharp.Data.TypeProviders.</span><span class="sxs-lookup"><span data-stu-id="cc76b-136">In the  list of available extensions, add a reference to the FSharp.Data.TypeProviders assembly.</span></span>
<br />

7. <span data-ttu-id="cc76b-137">Добавьте представленный ниже код, чтобы открыть соответствующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cc76b-137">Add the following code to open the appropriate namespaces.</span></span>
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="cc76b-138">Поиск или создание строки подключения для модели EDM</span><span class="sxs-lookup"><span data-stu-id="cc76b-138">Finding or creating the connection string for the Entity Data Model</span></span>
<span data-ttu-id="cc76b-139">Строка подключения для модели EDM (строка подключения EDMX) содержит не только строку подключения для поставщика базы данных, но и дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="cc76b-139">The connection string for the Entity Data Model (EDMX connection string) includes not only the connection string for the database provider but also additional information.</span></span> <span data-ttu-id="cc76b-140">Например, строка подключения EDMX для простой базы данных SQL Server подобна следующему коду.</span><span class="sxs-lookup"><span data-stu-id="cc76b-140">For example, EDMX connection string for a simple SQL Server database resembles the following code.</span></span>

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

<span data-ttu-id="cc76b-141">Дополнительные сведения о строках подключения EDMX см. в разделе [строки подключения](https://msdn.microsoft.com/library/ms254494.aspx).</span><span class="sxs-lookup"><span data-stu-id="cc76b-141">For more information about EDMX connection strings, see [Connection Strings](https://msdn.microsoft.com/library/ms254494.aspx).</span></span>


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="cc76b-142">Действия для поиска или создания строки подключения для модели EDM</span><span class="sxs-lookup"><span data-stu-id="cc76b-142">To find or create the connection string for the Entity Data Model</span></span>

1. <span data-ttu-id="cc76b-143">Строки подключения EDMX трудно создавать вручную, поэтому можно сэкономить время, создавая их программно.</span><span class="sxs-lookup"><span data-stu-id="cc76b-143">EDMX connection strings can be difficult to generate by hand, so you can save time by generating it programmatically.</span></span> <span data-ttu-id="cc76b-144">Если строка подключения EDMX известна, можно пропустить этот шаг и просто использовать эту строку на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="cc76b-144">If you know your EDMX connection string, you can bypass this step and simply use that string in the next step.</span></span> <span data-ttu-id="cc76b-145">Если строка неизвестна, используйте показанный ниже код для создания строки подключения EDMX из строки подключения к базе данных, которую необходимо предоставить.</span><span class="sxs-lookup"><span data-stu-id="cc76b-145">If not, use the following code to generate the EDMX connection string from a database connection string that you provide.</span></span>
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a><span data-ttu-id="cc76b-146">Настройка поставщика типов</span><span class="sxs-lookup"><span data-stu-id="cc76b-146">Configuring the type provider</span></span>
<span data-ttu-id="cc76b-147">На этом шаге создается и настраивается поставщик типов со строкой подключения EDMX, а также создаются типы для схемы, определенной в EMDX-файле.</span><span class="sxs-lookup"><span data-stu-id="cc76b-147">In this step, you create and configure the type provider with the EDMX connection string, and you generate types for the schema that's defined in the .edmx file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="cc76b-148">Настройка поставщика типов и создание типов</span><span class="sxs-lookup"><span data-stu-id="cc76b-148">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="cc76b-149">Скопируйте EDMX-файл, созданный на первом шаге данного пошагового руководства, в папку проекта.</span><span class="sxs-lookup"><span data-stu-id="cc76b-149">Copy the .edmx file that you generated in the first step of this walkthrough to your project folder.</span></span>
<br />

2. <span data-ttu-id="cc76b-150">Откройте контекстное меню узла проекта в проекте F #, выберите команду **Добавление существующего элемента**, а затем выберите EDMX-файл, чтобы добавить его в проект.</span><span class="sxs-lookup"><span data-stu-id="cc76b-150">Open the shortcut menu for the project node in your F# project, choose **Add Existing Item**, and then choose the .edmx file to add it to your project.</span></span>
<br />

3. <span data-ttu-id="cc76b-151">Введите представленный ниже код, чтобы активировать поставщик типов для EDMX-файла.</span><span class="sxs-lookup"><span data-stu-id="cc76b-151">Enter the following code to activate the type provider for your .edmx file.</span></span> <span data-ttu-id="cc76b-152">Замените *сервера*\*экземпляр * с именем сервера, на котором работает SQL Server и имя экземпляра и используйте имя EDMX-файла с первым шагом в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="cc76b-152">Replace *Server*\*Instance* with the name of your server that's running SQL Server and the name of your instance, and use the name of your .edmx file from the first step in this walkthrough.</span></span>
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a><span data-ttu-id="cc76b-153">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="cc76b-153">Querying the data</span></span>
<span data-ttu-id="cc76b-154">На этом шаге используются выражения запросов F# для запроса к базе данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-154">In this step, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="cc76b-155">Действия для запроса данных</span><span class="sxs-lookup"><span data-stu-id="cc76b-155">To query the data</span></span>

- <span data-ttu-id="cc76b-156">Введите представленный ниже код, чтобы запросить данные в модели EDM.</span><span class="sxs-lookup"><span data-stu-id="cc76b-156">Enter the following code to query the data in the entity data model.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="cc76b-157">Вызов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="cc76b-157">Calling a stored procedure</span></span>
<span data-ttu-id="cc76b-158">Хранимые процедуры можно вызывать с помощью поставщика типов EDMX.</span><span class="sxs-lookup"><span data-stu-id="cc76b-158">You can call stored procedures by using the EDMX type provider.</span></span> <span data-ttu-id="cc76b-159">В следующей процедуре базы данных School содержит хранимую процедуру, **UpdatePerson**, которая обновляет запись, используя новые значения для столбцов.</span><span class="sxs-lookup"><span data-stu-id="cc76b-159">In the following procedure, the School database contains a stored procedure, **UpdatePerson**, which updates a record, given new values for the columns.</span></span> <span data-ttu-id="cc76b-160">Эту хранимую процедуру можно использовать, поскольку она предоставляется в качестве метода типа DataContext.</span><span class="sxs-lookup"><span data-stu-id="cc76b-160">You can use this stored procedure because it's exposed as a method on the DataContext type.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="cc76b-161">Действия для вызова хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="cc76b-161">To call a stored procedure</span></span>

- <span data-ttu-id="cc76b-162">Добавьте к записям обновления следующий код.</span><span class="sxs-lookup"><span data-stu-id="cc76b-162">Add the following code to update records.</span></span>
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

<span data-ttu-id="cc76b-163">В случае успеха результатом будет значение 1.</span><span class="sxs-lookup"><span data-stu-id="cc76b-163">The result is 1 if you succeed.</span></span> <span data-ttu-id="cc76b-164">Обратите внимание, что **exactlyOne** используется в выражении запроса, чтобы убедиться, что только один результат возвращен; в противном случае, создается исключение.</span><span class="sxs-lookup"><span data-stu-id="cc76b-164">Notice that **exactlyOne** is used in the query expression to ensure that only one result is returned; otherwise, an exception is thrown.</span></span> <span data-ttu-id="cc76b-165">Кроме того, для упрощения работы со значениями NULL можно использовать простой **nullable** функции, который определен в этом коде для создания значения, допускающие значения NULL из обычного значения.</span><span class="sxs-lookup"><span data-stu-id="cc76b-165">Also, to work with nullable values more easily, you can use the simple **nullable** function that's defined in this code to create a nullable value out of an ordinary value.</span></span>

<br />

## <a name="configuring-the-entity-data-model"></a><span data-ttu-id="cc76b-166">Настройка модели EDM</span><span class="sxs-lookup"><span data-stu-id="cc76b-166">Configuring the Entity Data Model</span></span>
<span data-ttu-id="cc76b-167">Эту процедуру следует выполнить, только если необходимо знать, как создать полную модель EDM из базы данных при отсутствии базы данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="cc76b-167">You should complete this procedure only if you want to know how to generate a full Entity Data Model from a database and you don't have a database with which to test.</span></span>


#### <a name="to-configure-the-entity-data-model"></a><span data-ttu-id="cc76b-168">Действия для настройки модели EDM</span><span class="sxs-lookup"><span data-stu-id="cc76b-168">To configure the Entity Data Model</span></span>

1. <span data-ttu-id="cc76b-169">В строке меню выберите **SQL**, **редактора Transact-SQL**, **новый запрос** для создания базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-169">On the menu bar, choose **SQL**, **Transact-SQL Editor**, **New Query** to create a database.</span></span> <span data-ttu-id="cc76b-170">В случае получения запроса укажите сервер и экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-170">If prompted, specify your database server and instance.</span></span>
<br />

2. <span data-ttu-id="cc76b-171">Скопируйте и вставьте содержимое скрипта базы данных, который создает базу данных студентов, как описано в [документации по Entity Framework](http://msdn.microsoft.com/data/JJ614587.aspx) в центр разработчиков данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-171">Copy and paste the contents of the database script that creates the Student database, as described in the [Entity Framework documentation](http://msdn.microsoft.com/data/JJ614587.aspx) in the Data Developer Center.</span></span>
<br />

3. <span data-ttu-id="cc76b-172">Запустите скрипт SQL, выбрав кнопку панели инструментов с треугольником, или нажмите клавиши Ctrl + Q.</span><span class="sxs-lookup"><span data-stu-id="cc76b-172">Run the SQL script by choosing the toolbar button with the triangle symbol or choosing the Ctrl+Q keys.</span></span>
<br />

4. <span data-ttu-id="cc76b-173">В **обозревателя серверов**, откройте контекстное меню для **подключения к данным**, выберите **добавить подключение**, а затем введите имя сервера базы данных, имя экземпляра и базы данных School.</span><span class="sxs-lookup"><span data-stu-id="cc76b-173">In **Server Explorer**, open the shortcut menu for **Data Connections**, choose **Add Connection**, and then enter the name of the database server, the name of the instance name, and the School database.</span></span>
<br />

5. <span data-ttu-id="cc76b-174">Создайте проект C# или консольное приложение Visual Basic, откройте ее контекстное меню, выберите **Добавление нового элемента**, а затем выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="cc76b-174">Create a C# or Visual Basic Console Application project, open its shortcut menu, choose **Add New Item**, and then choose **ADO.NET Entity Data Model**.</span></span>
<br />  <span data-ttu-id="cc76b-175">Откроется мастер моделей EDM.</span><span class="sxs-lookup"><span data-stu-id="cc76b-175">The Entity Data Model Wizard opens.</span></span> <span data-ttu-id="cc76b-176">С помощью этого мастера можно выбрать способ создания модели EDM.</span><span class="sxs-lookup"><span data-stu-id="cc76b-176">By using this wizard, you can choose how you want to create the Entity Data Model.</span></span>
<br />

6. <span data-ttu-id="cc76b-177">В разделе **Выбор содержимого модели**выберите **создать из базы данных** флажок.</span><span class="sxs-lookup"><span data-stu-id="cc76b-177">Under **Choose Model Contents**, select the **Generate from database** check box.</span></span>
<br />

7. <span data-ttu-id="cc76b-178">На следующей странице выберите только что созданную базу данных School в качестве подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="cc76b-178">On the next page, choose your newly created School database as the data connection.</span></span>
<br />  <span data-ttu-id="cc76b-179">Это подключение должно быть подобно  **&lt;servername&gt;.&lt; instancename&gt;. School.dbo**.</span><span class="sxs-lookup"><span data-stu-id="cc76b-179">This connection should resemble **&lt;servername&gt;.&lt;instancename&gt;.School.dbo**.</span></span>
<br />

8. <span data-ttu-id="cc76b-180">Скопируйте строку подключения сущности в буфер обмена, поскольку эта строка может пригодиться в будущем.</span><span class="sxs-lookup"><span data-stu-id="cc76b-180">Copy your entity connection string to the Clipboard because that string might be important later.</span></span>
<br />

9. <span data-ttu-id="cc76b-181">Убедитесь, что флажок, чтобы сохранить строку подключения сущности в **App.Config** файл выбран и запишите значение строки в текстовом поле, которое поможет найти строку подключения позже, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="cc76b-181">Make sure the check box to save the entity connection string to the **App.Config** file is selected, and make note of the string value in the text box, which should help you locate the connection string later, if needed.</span></span>
<br />

10. <span data-ttu-id="cc76b-182">На следующей странице выберите **таблиц** и **хранимые процедуры и функции**.</span><span class="sxs-lookup"><span data-stu-id="cc76b-182">On the next page, choose **Tables** and **Stored Procedures and Functions**.</span></span>
<br />  <span data-ttu-id="cc76b-183">При выборе этих узлов верхнего уровня выбираются все таблицы, хранимые процедуры и функции.</span><span class="sxs-lookup"><span data-stu-id="cc76b-183">By choosing these top-level nodes, you choose all tables, stored procedures, and functions.</span></span> <span data-ttu-id="cc76b-184">При необходимости можно также выбрать их отдельно.</span><span class="sxs-lookup"><span data-stu-id="cc76b-184">You can also choose these individually, if you want.</span></span>
<br />

11. <span data-ttu-id="cc76b-185">Убедитесь, что установлены флажки для других параметров.</span><span class="sxs-lookup"><span data-stu-id="cc76b-185">Make sure that the check boxes for the other settings are selected.</span></span>
<br />  <span data-ttu-id="cc76b-186">Первый **единственном или множественном числе формировать имена объектов** флажок указывает, следует ли изменить форм единственного числа для во множественном числе, чтобы соответствовать соглашениям по именованию объектов, представляющих таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-186">The first **Pluralize or singularize generated object names** check box indicates whether to change singular forms to plural to match conventions in naming objects that represent database tables.</span></span> <span data-ttu-id="cc76b-187">**Включить столбцы внешних ключей в модель** флажок определяет, следует ли включать поля, для которых предназначен для соединения с другими полями в типах объектов, созданных для схемы базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-187">The **Include foreign key columns in the model** check box determines whether to include fields for which the purpose is to join to other fields in the object types that are generated for the database schema.</span></span> <span data-ttu-id="cc76b-188">Третий флажок указывает, следует ли включать в модель хранимые процедуры и функции.</span><span class="sxs-lookup"><span data-stu-id="cc76b-188">The third check box indicates whether to include stored procedures and functions in the model.</span></span>
<br />

12. <span data-ttu-id="cc76b-189">Выберите **Готово** кнопку, чтобы создать EDMX-файл, содержащий модель EDM, основанный на базу данных School.</span><span class="sxs-lookup"><span data-stu-id="cc76b-189">Select the **Finish** button to generate an .edmx file that contains an Entity Data Model that's based on the School database.</span></span>
<br />  <span data-ttu-id="cc76b-190">Файл, **Model1.edmx**, добавляется в проект, и появляется диаграмма базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc76b-190">A file, **Model1.edmx**, is added to your project, and a database diagram appears.</span></span>
<br />

13. <span data-ttu-id="cc76b-191">В строке меню выберите **представление**, **другие окна**, **браузер моделей EDM** для просмотра всех сведений о модели или **сведения о сопоставлении данных модели EDM**  чтобы открыть окно, в котором показано, как созданная модель объектов сопоставляется таблицам базы данных и столбцов.</span><span class="sxs-lookup"><span data-stu-id="cc76b-191">On the menu bar, choose **View**, **Other Windows**, **Entity Data Model Browser** to view all the details of the model or **Entity Data Model Mapping Details** to open a window that shows how the generated object model maps onto database tables and columns.</span></span>
<br />


## <a name="next-steps"></a><span data-ttu-id="cc76b-192">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="cc76b-192">Next Steps</span></span>
<span data-ttu-id="cc76b-193">Изучение других запросов, просмотрев доступны операторы, перечисленные в [выражения запросов](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cc76b-193">Explore other queries by looking at the available query operators as listed in [Query Expressions](../../language-reference/query-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="cc76b-194">См. также</span><span class="sxs-lookup"><span data-stu-id="cc76b-194">See Also</span></span>
[<span data-ttu-id="cc76b-195">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="cc76b-195">Type Providers</span></span>](index.md)

[<span data-ttu-id="cc76b-196">Поставщик типов EdmxFile</span><span class="sxs-lookup"><span data-stu-id="cc76b-196">EdmxFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="cc76b-197">Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов и сущностей</span><span class="sxs-lookup"><span data-stu-id="cc76b-197">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>](accessing-a-sql-database-entities.md)

[<span data-ttu-id="cc76b-198">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="cc76b-198">Entity Framework</span></span>](http://msdn.microsoft.com/data/ef)

[<span data-ttu-id="cc76b-199">Общие сведения о файлах .edmx</span><span class="sxs-lookup"><span data-stu-id="cc76b-199">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[<span data-ttu-id="cc76b-200">Генератор модели EDM &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="cc76b-200">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)

