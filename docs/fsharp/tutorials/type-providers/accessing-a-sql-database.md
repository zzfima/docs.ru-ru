---
title: "Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов (F#)"
description: "Сведения об использовании поставщика типов SqlDataConnection (LINQ to SQL) в F # 3.0 для создания типов для базы данных SQL, при наличии подключения реального времени."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: c99afc1121b4f0d6d05ef82681a32437ede06e42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a><span data-ttu-id="2a804-104">Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="2a804-104">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="2a804-105">В этом руководстве, была написана для F # 3.0 и будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="2a804-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="2a804-106">Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](http://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="2a804-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="2a804-107">Справочные ссылки API, вы перейдете MSDN.</span><span class="sxs-lookup"><span data-stu-id="2a804-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="2a804-108">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="2a804-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2a804-109">В этом пошаговом руководстве описывается использование поставщика типов SqlDataConnection (LINQ to SQL), который доступен в F # 3.0 для создания типов данных в базе данных SQL, при наличии динамического подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-109">This walkthrough explains how to use the SqlDataConnection (LINQ to SQL) type provider that is available in F# 3.0 to generate types for data in a SQL database when you have a live connection to a database.</span></span> <span data-ttu-id="2a804-110">Если у вас активное соединение к базе данных, но нужно LINQ файл схемы SQL (DBML-файл), см. раздел [Пошаговое руководство: Создание типов F # из файла dBm](generating-fsharp-types-from-dbml.md).</span><span class="sxs-lookup"><span data-stu-id="2a804-110">If you do not have a live connection to a database, but you do have a LINQ to SQL schema file (DBML file), see [Walkthrough: Generating F# Types from a DBML File](generating-fsharp-types-from-dbml.md).</span></span>

<span data-ttu-id="2a804-111">В данном пошаговом руководстве рассмотрены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="2a804-111">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="2a804-112">Эти задачи необходимо выполнять в указанном порядке для данного пошагового руководства для успешного выполнения:</span><span class="sxs-lookup"><span data-stu-id="2a804-112">These tasks must be performed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="2a804-113">Подготовка тестовой базой данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-113">Preparing a test database</span></span>

- <span data-ttu-id="2a804-114">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="2a804-114">Creating the project</span></span>

- <span data-ttu-id="2a804-115">Настройка поставщика типов</span><span class="sxs-lookup"><span data-stu-id="2a804-115">Setting up a type provider</span></span>

- <span data-ttu-id="2a804-116">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="2a804-116">Querying the data</span></span>

- <span data-ttu-id="2a804-117">Работа с полями, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="2a804-117">Working with nullable fields</span></span>

- <span data-ttu-id="2a804-118">Вызов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="2a804-118">Calling a stored procedure</span></span>

- <span data-ttu-id="2a804-119">Обновление базы данных</span><span class="sxs-lookup"><span data-stu-id="2a804-119">Updating the database</span></span>

- <span data-ttu-id="2a804-120">Выполнение кода Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a804-120">Executing Transact-SQL code</span></span>

- <span data-ttu-id="2a804-121">Полный контекст данных с помощью</span><span class="sxs-lookup"><span data-stu-id="2a804-121">Using the full data context</span></span>

- <span data-ttu-id="2a804-122">Удаление данных</span><span class="sxs-lookup"><span data-stu-id="2a804-122">Deleting data</span></span>

- <span data-ttu-id="2a804-123">Создайте тестовую базу данных (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="2a804-123">Create a test database (as needed)</span></span>

## <a name="preparing-a-test-database"></a><span data-ttu-id="2a804-124">Подготовка тестовой базой данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-124">Preparing a Test Database</span></span>
<span data-ttu-id="2a804-125">На сервере, на котором выполняется SQL Server создайте базу данных в целях тестирования.</span><span class="sxs-lookup"><span data-stu-id="2a804-125">On a server that's running SQL Server, create a database for testing purposes.</span></span> <span data-ttu-id="2a804-126">Можно использовать базу данных создать скрипт в нижней части этой страницы в разделе [Создание тестовой базы данных](#creating-a-test-database) это сделать.</span><span class="sxs-lookup"><span data-stu-id="2a804-126">You can use the database create script at the bottom of this page in the section [Creating a test database](#creating-a-test-database) to do this.</span></span>


#### <a name="to-prepare-a-test-database"></a><span data-ttu-id="2a804-127">Для подготовки тестовой базы данных</span><span class="sxs-lookup"><span data-stu-id="2a804-127">To prepare a test database</span></span>

<span data-ttu-id="2a804-128">Чтобы выполнить скрипт создания MyDatabase, откройте **представление** меню и выберите **обозреватель объектов SQL Server** или нажмите сочетание клавиш Ctrl +\, клавиши Ctrl + S.</span><span class="sxs-lookup"><span data-stu-id="2a804-128">To run the MyDatabase Create Script, open the **View** menu, and then choose **SQL Server Object Explorer** or choose the Ctrl+\, Ctrl+S keys.</span></span> <span data-ttu-id="2a804-129">В **обозреватель объектов SQL Server** окна, откройте контекстное меню для соответствующего экземпляра, **новый запрос**, скопируйте сценарий в нижней части этой страницы и затем вставить скрипт в редакторе.</span><span class="sxs-lookup"><span data-stu-id="2a804-129">In **SQL Server Object Explorer** window, open the shortcut menu for the appropriate instance, choose **New Query**, copy the script at the bottom of this page, and then paste the script into the editor.</span></span> <span data-ttu-id="2a804-130">Чтобы запустить скрипт SQL, выберите значок панели инструментов треугольное символом или нажмите сочетание клавиш Ctrl + Q.</span><span class="sxs-lookup"><span data-stu-id="2a804-130">To run the SQL script, choose the toolbar icon with the triangular symbol, or choose the Ctrl+Q keys.</span></span> <span data-ttu-id="2a804-131">Дополнительные сведения о **обозреватель объектов SQL Server**, в разделе [разработка подключенной базы данных](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span><span class="sxs-lookup"><span data-stu-id="2a804-131">For more information about **SQL Server Object Explorer**, see [Connected Database Development](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span></span>


## <a name="creating-the-project"></a><span data-ttu-id="2a804-132">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="2a804-132">Creating the project</span></span>
<span data-ttu-id="2a804-133">Создайте проект приложения F #.</span><span class="sxs-lookup"><span data-stu-id="2a804-133">Next, you create an F# application project.</span></span>


#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="2a804-134">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="2a804-134">To create and set up the project</span></span>

1. <span data-ttu-id="2a804-135">Создайте новый проект приложения F #.</span><span class="sxs-lookup"><span data-stu-id="2a804-135">Create a new F# Application project.</span></span>

2. <span data-ttu-id="2a804-136">Добавьте ссылки на [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), а также `System.Data`, и `System.Data.Linq`.</span><span class="sxs-lookup"><span data-stu-id="2a804-136">Add references to [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), as well as `System.Data`, and `System.Data.Linq`.</span></span>

3. <span data-ttu-id="2a804-137">Откройте соответствующие пространства имен, добавив следующий код в верхнюю часть вашего файла кода F # Program.fs.</span><span class="sxs-lookup"><span data-stu-id="2a804-137">Open the appropriate namespaces by adding the following lines of code to the top of your F# code file Program.fs.</span></span>

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. <span data-ttu-id="2a804-138">Как и в большинстве программ F #, может выполнять код в этом пошаговом руководстве как компилированной программы или интерактивном режиме запустить ее как сценарий.</span><span class="sxs-lookup"><span data-stu-id="2a804-138">As with most F# programs, you can execute the code in this walkthrough as a compiled program, or you can run it interactively as a script.</span></span> <span data-ttu-id="2a804-139">Если вы предпочитаете использовать сценарии, откройте контекстное меню узла проекта, выберите **добавить новый элемент**, добавьте файл скрипта F # и добавьте код в каждом шаге в скрипт.</span><span class="sxs-lookup"><span data-stu-id="2a804-139">If you prefer to use scripts, open the shortcut menu for the project node, select **Add New Item**, add an F# script file, and add the code in each step to the script.</span></span> <span data-ttu-id="2a804-140">Необходимо добавить следующие строки в верхней части файла для загрузки ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="2a804-140">You will need to add the following lines at the top of the file to load the assembly references.</span></span>

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  <span data-ttu-id="2a804-141">Затем можно выбрать каждый блок кода, как добавить его и нажмите клавиши Alt + ВВОД для запуска в F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="2a804-141">You can then select each block of code as you add it and press Alt+Enter to run it in F# Interactive.</span></span>

## <a name="setting-up-a-type-provider"></a><span data-ttu-id="2a804-142">Настройка поставщика типов</span><span class="sxs-lookup"><span data-stu-id="2a804-142">Setting up a type provider</span></span>
<span data-ttu-id="2a804-143">На этом шаге создается тип поставщика схемы базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-143">In this step, you create a type provider for your database schema.</span></span>


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a><span data-ttu-id="2a804-144">Чтобы настроить поставщик типов подключения прямых базы данных</span><span class="sxs-lookup"><span data-stu-id="2a804-144">To set up the type provider from a direct database connection</span></span>

<span data-ttu-id="2a804-145">Существуют две важные строки кода, необходимое для создания типов, которые можно использовать для запросов к базе данных SQL с помощью поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="2a804-145">There are two critical lines of code that you need in order to create the types that you can use to query a SQL database using the type provider.</span></span> <span data-ttu-id="2a804-146">Во-первых можно создать экземпляр поставщика типа.</span><span class="sxs-lookup"><span data-stu-id="2a804-146">First, you instantiate the type provider.</span></span> <span data-ttu-id="2a804-147">Чтобы сделать это, создайте как сокращенную форму для типа выглядит `SqlDataConnection` с статический универсальный параметр.</span><span class="sxs-lookup"><span data-stu-id="2a804-147">To do this, create what looks like a type abbreviation for a `SqlDataConnection` with a static generic parameter.</span></span> <span data-ttu-id="2a804-148">`SqlDataConnection`— Это поставщик типа SQL и их не следует путать с `SqlConnection` типа, используемые при программировании ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2a804-148">`SqlDataConnection` is a SQL type provider, and should not be confused with `SqlConnection` type that is used in ADO.NET programming.</span></span> <span data-ttu-id="2a804-149">Если имеется база данных, необходимо подключиться к, а строка подключения, используйте следующий код для вызова поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="2a804-149">If you have a database that you want to connect to, and have a connection string, use the following code to invoke the type provider.</span></span> <span data-ttu-id="2a804-150">Замените строки подключения для примера строка заданному.</span><span class="sxs-lookup"><span data-stu-id="2a804-150">Substitute your own connection string for the example string given.</span></span> <span data-ttu-id="2a804-151">Например если сервер MYSERVER и экземпляр базы данных — ЭКЗЕМПЛЯР, имя базы данных — MyDatabase и вы хотите использовать проверку подлинности Windows для доступа к базе данных, то строка подключения будет как имеется в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="2a804-151">For example, if your server is MYSERVER and the database instance is INSTANCE, the database name is MyDatabase, and you want to use Windows Authentication to access the database, then the connection string would be as given in the following example code.</span></span>

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

<span data-ttu-id="2a804-152">Теперь у вас есть тип, `dbSchema`, который является родительским типом, содержащий созданные типы, представляющие таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-152">Now you have a type, `dbSchema`, which is a parent type that contains all the generated types that represent database tables.</span></span> <span data-ttu-id="2a804-153">Также имеется объект, `db`, который имеет членами всех таблиц в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-153">You also have an object, `db`, which has as its members all the tables in the database.</span></span> <span data-ttu-id="2a804-154">Имена таблиц представляются свойства и тип этих свойств создается компилятором F #.</span><span class="sxs-lookup"><span data-stu-id="2a804-154">The table names are properties, and the type of these properties is generated by the F# compiler.</span></span> <span data-ttu-id="2a804-155">Самих типов отображаются как вложенные типы под `dbSchema.ServiceTypes`.</span><span class="sxs-lookup"><span data-stu-id="2a804-155">The types themselves appear as nested types under `dbSchema.ServiceTypes`.</span></span> <span data-ttu-id="2a804-156">Таким образом любые данные, полученные для строк из этих таблиц — это экземпляр соответствующего типа, который был создан для этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a804-156">Therefore, any data retrieved for rows of these tables is an instance of the appropriate type that was generated for that table.</span></span> <span data-ttu-id="2a804-157">Имя типа `ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="2a804-157">The name of the type is `ServiceTypes.Table1`.</span></span>

<span data-ttu-id="2a804-158">Чтобы ознакомиться с интерпретацией запросов в запросы SQL языка F #, просмотрите строки, которая задает `Log` свойства в контексте данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-158">To familiarize yourself with how the F# language interprets queries into SQL queries, review the line that sets the `Log` property on the data context.</span></span>

<span data-ttu-id="2a804-159">Для дальнейшего изучения типов, созданных поставщиком типов, добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="2a804-159">To further explore the types created by the type provider, add the following code.</span></span>

```fsharp
let table1 = db.Table1
```

<span data-ttu-id="2a804-160">Наведите указатель мыши на `table1` для просмотра его тип.</span><span class="sxs-lookup"><span data-stu-id="2a804-160">Hover over `table1` to see its type.</span></span> <span data-ttu-id="2a804-161">Его тип — `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` и универсального аргумента подразумевается, что тип каждой строки является созданного типа `dbSchema.ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="2a804-161">Its type is `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` and the generic argument implies that the type of each row is the generated type, `dbSchema.ServiceTypes.Table1`.</span></span> <span data-ttu-id="2a804-162">Компилятор создает аналогичного для каждой таблицы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-162">The compiler creates a similar type for each table in the database.</span></span>

## <a name="querying-the-data"></a><span data-ttu-id="2a804-163">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="2a804-163">Querying the data</span></span>
<span data-ttu-id="2a804-164">На этом этапе запись запроса с помощью выражения запросов F #.</span><span class="sxs-lookup"><span data-stu-id="2a804-164">In this step, you write a query using F# query expressions.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="2a804-165">Действия для запроса данных</span><span class="sxs-lookup"><span data-stu-id="2a804-165">To query the data</span></span>

1. <span data-ttu-id="2a804-166">Теперь можно создайте запрос для этой таблицы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-166">Now create a query for that table in the database.</span></span> <span data-ttu-id="2a804-167">Добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="2a804-167">Add the following code.</span></span>

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  <span data-ttu-id="2a804-168">Внешний вид слово `query` указывает, что это выражение запроса, тип вычисления выражения, которое создает коллекцию результаты, аналогичные запроса обычной базой данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-168">The appearance of the word `query` indicates that this is a query expression, a type of computation expression that generates a collection of results similar of a typical database query.</span></span> <span data-ttu-id="2a804-169">При наведении на запрос, вы увидите, что он является экземпляром [класс Linq.QueryBuilder](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), тип, который определяет query-вычислительное выражение.</span><span class="sxs-lookup"><span data-stu-id="2a804-169">If you hover over query, you will see that it is an instance of [Linq.QueryBuilder Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), a type that defines the query computation expression.</span></span> <span data-ttu-id="2a804-170">При наведении `query1`, вы увидите, что он является экземпляром `System.Linq.IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="2a804-170">If you hover over `query1`, you will see that it is an instance of `System.Linq.IQueryable`.</span></span> <span data-ttu-id="2a804-171">Как видно из имени, `System.Linq.IQueryable` представляет данные, которые могут запрашиваться не является результатом запроса.</span><span class="sxs-lookup"><span data-stu-id="2a804-171">As the name suggests, `System.Linq.IQueryable` represents data that may be queried, not the result of a query.</span></span> <span data-ttu-id="2a804-172">Запрос регулируется отложенные вычисления, что означает, что база данных доступна только запросы при вычислении запроса.</span><span class="sxs-lookup"><span data-stu-id="2a804-172">A query is subject to lazy evaluation, which means that the database is only queried when the query is evaluated.</span></span> <span data-ttu-id="2a804-173">Последняя строка передает запрос с помощью `Seq.iter`.</span><span class="sxs-lookup"><span data-stu-id="2a804-173">The final line passes the query through `Seq.iter`.</span></span> <span data-ttu-id="2a804-174">Запросы перечисляемую и может выполнить итерацию как последовательности.</span><span class="sxs-lookup"><span data-stu-id="2a804-174">Queries are enumerable and may be iterated like sequences.</span></span> <span data-ttu-id="2a804-175">Дополнительные сведения см. в разделе [выражения запросов](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2a804-175">For more information, see [Query Expressions](../../language-reference/query-expressions.md).</span></span>

2. <span data-ttu-id="2a804-176">Теперь добавьте оператор запроса в запрос.</span><span class="sxs-lookup"><span data-stu-id="2a804-176">Now add a query operator to the query.</span></span> <span data-ttu-id="2a804-177">Существует несколько операторов запроса, что можно использовать для создания более сложных запросов.</span><span class="sxs-lookup"><span data-stu-id="2a804-177">There are a number of query operators available that you can use to construct more complex queries.</span></span> <span data-ttu-id="2a804-178">В этом примере также показано, можно исключить переменной запроса и вместо этого используйте оператор конвейера.</span><span class="sxs-lookup"><span data-stu-id="2a804-178">This example also shows that you can eliminate the query variable and use a pipeline operator instead.</span></span>

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. <span data-ttu-id="2a804-179">Добавьте более сложный запрос с соединение двух таблиц.</span><span class="sxs-lookup"><span data-stu-id="2a804-179">Add a more complex query with a join of two tables.</span></span>

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. <span data-ttu-id="2a804-180">Обычно в реальном коде параметров в запросе являются значения или переменные, константы не во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="2a804-180">In real-world code, the parameters in your query are usually values or variables, not compile-time constants.</span></span> <span data-ttu-id="2a804-181">Добавьте следующий код, который создает оболочку для запроса в функции, которая принимает параметр, а затем вызывает эту функцию со значением 10.</span><span class="sxs-lookup"><span data-stu-id="2a804-181">Add the following code that wraps a query in a function that takes a parameter, and then calls that function with the value 10.</span></span>

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a><span data-ttu-id="2a804-182">Работа с полями, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="2a804-182">Working with nullable fields</span></span>
<span data-ttu-id="2a804-183">В базах данных поля часто разрешены значения null.</span><span class="sxs-lookup"><span data-stu-id="2a804-183">In databases, fields often allow null values.</span></span> <span data-ttu-id="2a804-184">В системе типов .NET нельзя использовать обычные числовыми типами данных для данных, допускающий значения NULL, так как эти типы не имеют возможности значение null.</span><span class="sxs-lookup"><span data-stu-id="2a804-184">In the .NET type system, you cannot use the ordinary numerical data types for data that allows nulls because those types do not have null as a possible value.</span></span> <span data-ttu-id="2a804-185">Таким образом, эти значения представлены экземплярами `System.Nullable` типа.</span><span class="sxs-lookup"><span data-stu-id="2a804-185">Therefore, these values are represented by instances of `System.Nullable` type.</span></span> <span data-ttu-id="2a804-186">Вместо обращения к значения таких полей непосредственно с именем поля, необходимо выполнить некоторые дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="2a804-186">Instead of accessing the value of such fields directly with the name of the field, you need to add some extra steps.</span></span> <span data-ttu-id="2a804-187">Можно использовать `System.Nullable.Value` свойство для доступа к значению базового типа nullable.</span><span class="sxs-lookup"><span data-stu-id="2a804-187">You can use the `System.Nullable.Value` property to access the underlying value of a nullable type.</span></span> <span data-ttu-id="2a804-188">`System.Nullable.Value` Свойство вызывает исключение, если объект имеет значение null, вместо того чтобы использовать значение.</span><span class="sxs-lookup"><span data-stu-id="2a804-188">The `System.Nullable.Value` property throws an exception if the object is null rather than having a value.</span></span> <span data-ttu-id="2a804-189">Можно использовать `System.Nullable.HasValue` логический метод, чтобы определить, если значение существует, или используйте `System.Nullable.GetValueOrDefault()` для убедитесь, что фактическое значение во всех случаях.</span><span class="sxs-lookup"><span data-stu-id="2a804-189">You can use the `System.Nullable.HasValue` Boolean method to determine if a value exists, or use `System.Nullable.GetValueOrDefault()` to ensure that you have an actual value in all cases.</span></span> <span data-ttu-id="2a804-190">Если вы используете `System.Nullable.GetValueOrDefault()` и в базе данных имеется значение null, то он заменяется со значением, такие как пустую строку для строковых типов, 0 для целочисленных типов или 0,0 чисел с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="2a804-190">If you use `System.Nullable.GetValueOrDefault()` and there is a null in the database, then it is replaced with a value such as an empty string for string types, 0 for integral types or 0.0 for floating point types.</span></span>

<span data-ttu-id="2a804-191">Если необходим для выполнения проверок на равенство или сравнения на значения NULL в `where` предложения в запросе можно использовать операторы допускает значения NULL, в [модуль Linq.NullableOperators](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="2a804-191">When you need to perform equality tests or comparisons on nullable values in a `where` clause in a query, you can use the nullable operators found in the [Linq.NullableOperators Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span></span> <span data-ttu-id="2a804-192">Они похожи на операторы сравнения, регулярные `=`, `>`, `<=`, и т. д., за исключением того, знак вопроса появляется слева или справа от оператора в которых значения NULL.</span><span class="sxs-lookup"><span data-stu-id="2a804-192">These are like the regular comparison operators `=`, `>`, `<=`, and so on, except that a question mark appears on the left or right of the operator where the nullable values are.</span></span> <span data-ttu-id="2a804-193">Например, оператор `>?` больше-оператор со значением, допускающие значения NULL в правой части.</span><span class="sxs-lookup"><span data-stu-id="2a804-193">For example, the operator `>?` is a greater-than operator with a nullable value on the right.</span></span> <span data-ttu-id="2a804-194">Эти операторы работают в том случае, если один из операндов выражения принимает значение null, то выражение принимает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2a804-194">The way these operators work is that if either side of the expression is null, the expression evaluates to `false`.</span></span> <span data-ttu-id="2a804-195">В `where` предложение, обычно это означает что строки, содержащие поля со значением null не выбран и не возвращается в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="2a804-195">In a `where` clause, this generally means that the rows that contain null fields are not selected and not returned in the query results.</span></span>


#### <a name="to-work-with-nullable-fields"></a><span data-ttu-id="2a804-196">Для работы с полями, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="2a804-196">To work with nullable fields</span></span>

<span data-ttu-id="2a804-197">Ниже показана работа со значениями NULL; предполагается, что **TestData1** является целочисленным полем, допускающий значения NULL.</span><span class="sxs-lookup"><span data-stu-id="2a804-197">The following code shows working with nullable values; assume that **TestData1** is an integer field that allows nulls.</span></span>

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="2a804-198">Вызов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="2a804-198">Calling a stored procedure</span></span>
<span data-ttu-id="2a804-199">Все хранимые процедуры в базе данных может вызываться из F #.</span><span class="sxs-lookup"><span data-stu-id="2a804-199">Any stored procedures on the database can be called from F#.</span></span> <span data-ttu-id="2a804-200">Необходимо задать параметр static `StoredProcedures` для `true` в реализации поставщика типа.</span><span class="sxs-lookup"><span data-stu-id="2a804-200">You must set the static parameter `StoredProcedures` to `true` in the type provider instantiation.</span></span> <span data-ttu-id="2a804-201">Поставщик типов `SqlDataConnection` содержит несколько статических методов, которые можно использовать для настройки созданные типы.</span><span class="sxs-lookup"><span data-stu-id="2a804-201">The type provider `SqlDataConnection` contains several static methods that you can use to configure the types that are generated.</span></span> <span data-ttu-id="2a804-202">Полное описание из них см. в разделе [поставщика типов SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="2a804-202">For a complete description of these, see [SqlDataConnection Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span></span> <span data-ttu-id="2a804-203">Метод в типе контекста данных создается для каждой хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="2a804-203">A method on the data context type is generated for each stored procedure.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="2a804-204">Действия для вызова хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="2a804-204">To call a stored procedure</span></span>

<span data-ttu-id="2a804-205">Если хранимые процедуры принимает параметры, допускающие значения NULL, необходимо передать соответствующей `System.Nullable` значение.</span><span class="sxs-lookup"><span data-stu-id="2a804-205">If the stored procedures takes parameters that are nullable, you need to pass an appropriate `System.Nullable` value.</span></span> <span data-ttu-id="2a804-206">Возвращаемое значение метода хранимой процедуры, возвращающей скалярное или таблицы является `System.Data.Linq.ISingleResult`, который содержит свойства, которые позволяют получить доступ к возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-206">The return value of a stored procedure method that returns a scalar or a table is `System.Data.Linq.ISingleResult`, which contains properties that enable you to access the returned data.</span></span> <span data-ttu-id="2a804-207">Тип аргумента для `System.Data.Linq.ISingleResult` также является одним из типов, создаваемых поставщиком типа и зависит от определенной процедуры.</span><span class="sxs-lookup"><span data-stu-id="2a804-207">The type argument for `System.Data.Linq.ISingleResult` depends on the specific procedure and is also one of the types that the type provider generates.</span></span> <span data-ttu-id="2a804-208">Для хранимой процедуры с именем `Procedure1`, тип — `Procedure1Result`.</span><span class="sxs-lookup"><span data-stu-id="2a804-208">For a stored procedure named `Procedure1`, the type is `Procedure1Result`.</span></span> <span data-ttu-id="2a804-209">Тип `Procedure1Result` содержит имена столбцов в таблице результатов или для хранимой процедуры, возвращающей скалярное значение, он представляет возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="2a804-209">The type `Procedure1Result` contains the names of the columns in a returned table, or, for a stored procedure that returns a scalar value, it represents the return value.</span></span>

<span data-ttu-id="2a804-210">В следующем коде предполагается, что является процедурой `Procedure1` в базе данных, которая принимает два целых числа допускает значения NULL, как параметры, выполняют запрос, который возвращает столбец с именем `TestData1`и возвращает целое число.</span><span class="sxs-lookup"><span data-stu-id="2a804-210">The following code assumes that there is a procedure `Procedure1` on the database that takes two nullable integers as parameters, runs a query that returns a column named `TestData1`, and returns an integer.</span></span>

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a><span data-ttu-id="2a804-211">Обновление базы данных</span><span class="sxs-lookup"><span data-stu-id="2a804-211">Updating the database</span></span>
<span data-ttu-id="2a804-212">Тип LINQ DataContext содержит методы, которые упрощают процесс для выполнения обновления с поддержкой транзакций базы данных полностью введенного образом с помощью создаваемых типов.</span><span class="sxs-lookup"><span data-stu-id="2a804-212">The LINQ DataContext type contains methods that make it easier to perform transacted database updates in a fully typed fashion with the generated types.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="2a804-213">Обновление базы данных</span><span class="sxs-lookup"><span data-stu-id="2a804-213">To update the database</span></span>

1. <span data-ttu-id="2a804-214">В следующем коде несколько строки добавляются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-214">In the following code, several rows are added to the database.</span></span> <span data-ttu-id="2a804-215">При добавлении строки можно использовать `System.Data.Linq.Table.InsertOnSubmit()` для указания новой строки для добавления.</span><span class="sxs-lookup"><span data-stu-id="2a804-215">If you are only adding a row, you can use `System.Data.Linq.Table.InsertOnSubmit()` to specify the new row to add.</span></span> <span data-ttu-id="2a804-216">При вставке нескольких строк, следует помещать их в коллекцию и вызова `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span><span class="sxs-lookup"><span data-stu-id="2a804-216">If you are inserting multiple rows, you should put them into a collection and call `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span></span> <span data-ttu-id="2a804-217">При вызове любого из этих методов, базы данных не изменяется немедленно.</span><span class="sxs-lookup"><span data-stu-id="2a804-217">When you call either of these methods, the database is not immediately changed.</span></span> <span data-ttu-id="2a804-218">Необходимо вызвать метод `System.Data.Linq.DataContext.SubmitChanges` для фактического применения изменений.</span><span class="sxs-lookup"><span data-stu-id="2a804-218">You must call `System.Data.Linq.DataContext.SubmitChanges` to actually commit the changes.</span></span> <span data-ttu-id="2a804-219">По умолчанию все действия выполняются прежде чем вызывать `System.Data.Linq.DataContext.SubmitChanges` неявным образом является частью той же транзакции.</span><span class="sxs-lookup"><span data-stu-id="2a804-219">By default, everything that you do before you call `System.Data.Linq.DataContext.SubmitChanges` is implicitly part of the same transaction.</span></span>

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. <span data-ttu-id="2a804-220">Теперь очистите строки, вызвав операцию удаления.</span><span class="sxs-lookup"><span data-stu-id="2a804-220">Now clean up the rows by calling a delete operation.</span></span>

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a><span data-ttu-id="2a804-221">Выполнение кода Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a804-221">Executing Transact-SQL code</span></span>
<span data-ttu-id="2a804-222">Можно также указать Transact-SQL непосредственно с помощью `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` метод `DataContext` класса.</span><span class="sxs-lookup"><span data-stu-id="2a804-222">You can also specify Transact-SQL directly by using the `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` method on the `DataContext` class.</span></span>


#### <a name="to-execute-custom-sql-commands"></a><span data-ttu-id="2a804-223">Для выполнения пользовательских команд SQL</span><span class="sxs-lookup"><span data-stu-id="2a804-223">To execute custom SQL commands</span></span>

<span data-ttu-id="2a804-224">Ниже показано, как для отправки команд SQL для вставки записи в таблицу и удалить запись из таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a804-224">The following code shows how to send SQL commands to insert a record into a table and also to delete a record from a table.</span></span>

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a><span data-ttu-id="2a804-225">Полный контекст данных с помощью</span><span class="sxs-lookup"><span data-stu-id="2a804-225">Using the full data context</span></span>
<span data-ttu-id="2a804-226">В предыдущих примерах `GetDataContext` метод, использованный для получения, называемый *упрощенным контекстом данных* для схемы базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-226">In the previous examples, the `GetDataContext` method was used to get what is called the *simplified data context* for the database schema.</span></span> <span data-ttu-id="2a804-227">Для использования при построении запросов, так как нет всех членов, доступных проще упрощенным контекстом данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-227">The simplified data context is easier to use when you are constructing queries because there are not as many members available.</span></span> <span data-ttu-id="2a804-228">Таким образом при просмотре свойств в IntelliSense, можно сосредоточиться на структуру базы данных, таких как таблицы и хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="2a804-228">Therefore, when you browse the properties in IntelliSense, you can focus on the database structure, such as the tables and stored procedures.</span></span> <span data-ttu-id="2a804-229">Однако имеется ограничение для действий, выполняемых с упрощенным контекстом данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-229">However, there is a limit to what you can do with the simplified data context.</span></span> <span data-ttu-id="2a804-230">Полный контекст данных, обеспечивает возможность выполнения других действий.</span><span class="sxs-lookup"><span data-stu-id="2a804-230">A full data context that provides the ability to perform other actions.</span></span> <span data-ttu-id="2a804-231">также доступен этот файл находится в `ServiceTypes` и имеет имя *DataContext* статического параметра, если он указан.</span><span class="sxs-lookup"><span data-stu-id="2a804-231">is also available This is located in the `ServiceTypes` and has the name of the *DataContext* static parameter if you provided it.</span></span> <span data-ttu-id="2a804-232">Если оно не было указано, имя типа контекста данных формируется автоматически на основе других данных SqlMetal.exe.</span><span class="sxs-lookup"><span data-stu-id="2a804-232">If you did not provide it, the name of the data context type is generated for you by SqlMetal.exe based on the other input.</span></span> <span data-ttu-id="2a804-233">Полный контекст данных наследует от `System.Data.Linq.DataContext` и предоставляет доступ к членам базового класса, включая ссылки на типы данных ADO.NET, такие как `Connection` объектов, методов, таких как `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` и `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` , можно использовать для написания запросов в SQL а также средства для работы с транзакциями, явным образом.</span><span class="sxs-lookup"><span data-stu-id="2a804-233">The full data context inherits from `System.Data.Linq.DataContext` and exposes the members of its base class, including references to ADO.NET data types such as the `Connection` object, methods such as `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` and `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` that you can use to write queries in SQL, and also a means to work with transactions explicitly.</span></span>


#### <a name="to-use-the-full-data-context"></a><span data-ttu-id="2a804-234">Чтобы использовать полный контекст данных</span><span class="sxs-lookup"><span data-stu-id="2a804-234">To use the full data context</span></span>

<span data-ttu-id="2a804-235">В следующем коде показано получение объекта контекста полного набора данных и использовать его для выполнения команд непосредственно к базе данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-235">The following code demonstrates getting a full data context object and using it to execute commands directly against the database.</span></span> <span data-ttu-id="2a804-236">В этом случае две команды выполняются в рамках одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="2a804-236">In this case, two commands are executed as part of the same transaction.</span></span>

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a><span data-ttu-id="2a804-237">Удаление данных</span><span class="sxs-lookup"><span data-stu-id="2a804-237">Deleting data</span></span>
<span data-ttu-id="2a804-238">Этот шаг показывает, как удалить строки из таблицы данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-238">This step shows you how to delete rows from a data table.</span></span>


#### <a name="to-delete-rows-from-the-database"></a><span data-ttu-id="2a804-239">Для удаления строк из базы данных</span><span class="sxs-lookup"><span data-stu-id="2a804-239">To delete rows from the database</span></span>

<span data-ttu-id="2a804-240">Теперь очистки любого добавлено строк путем написания функции, которая удаляет строки из указанной таблицы, экземпляр `System.Data.Linq.Table` класса.</span><span class="sxs-lookup"><span data-stu-id="2a804-240">Now, clean up any added rows by writing a function that deletes rows from a specified table, an instance of the `System.Data.Linq.Table` class.</span></span> <span data-ttu-id="2a804-241">Затем написать запрос для нахождения всех строк, которые требуется удалить и передать результаты запроса в `deleteRows` функции.</span><span class="sxs-lookup"><span data-stu-id="2a804-241">Then write a query to find all the rows that you want to delete, and pipe the results of the query into the `deleteRows` function.</span></span> <span data-ttu-id="2a804-242">Этот код использует возможности предоставления частичного применения аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="2a804-242">This code takes advantage of the ability to provide partial application of function arguments.</span></span>

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a><span data-ttu-id="2a804-243">Создание тестовой базой данных.</span><span class="sxs-lookup"><span data-stu-id="2a804-243">Creating a test database</span></span>
<span data-ttu-id="2a804-244">В этом разделе показано, как настроить тестовую базу данных для использования в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="2a804-244">This section shows you how to set up the test database to use in this walkthrough.</span></span>

<span data-ttu-id="2a804-245">Обратите внимание, что если база данных каким-либо образом изменены, необходимо будет сбросить тип поставщика.</span><span class="sxs-lookup"><span data-stu-id="2a804-245">Note that if you alter the database in some way, you will have to reset the type provider.</span></span> <span data-ttu-id="2a804-246">Чтобы сбросить тип поставщика, перестроения или очистки проект, который содержит тип поставщика.</span><span class="sxs-lookup"><span data-stu-id="2a804-246">To reset the type provider, rebuild or clean the project that contains the type provider.</span></span>


#### <a name="to-create-the-test-database"></a><span data-ttu-id="2a804-247">Создание тестовой базы данных</span><span class="sxs-lookup"><span data-stu-id="2a804-247">To create the test database</span></span>

1. <span data-ttu-id="2a804-248">В **обозревателя серверов**, откройте контекстное меню для **подключения к данным** узел и выберите **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="2a804-248">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and choose **Add Connection**.</span></span> <span data-ttu-id="2a804-249">**Добавить подключение** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="2a804-249">The **Add Connection** dialog box appears.</span></span>

2. <span data-ttu-id="2a804-250">В **имя сервера** поле, укажите имя экземпляра SQL Server, имеют административный доступ к или если нет доступа к серверу, укажите (localdb\v11. 0).</span><span class="sxs-lookup"><span data-stu-id="2a804-250">In the **Server name** box, specify the name of an instance of SQL Server that you have administrative access to, or if you do not have access to a server, specify (localdb\v11.0).</span></span> <span data-ttu-id="2a804-251">SQL Express LocalDB предоставляет упрощенный сервер базы данных для разработки и тестирования на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2a804-251">SQL Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="2a804-252">Создается новый узел в **обозревателя серверов** под **подключения к данным**.</span><span class="sxs-lookup"><span data-stu-id="2a804-252">A new node is created in **Server Explorer** under **Data Connections**.</span></span> <span data-ttu-id="2a804-253">Дополнительные сведения о LocalDB см. в разделе [Пошаговое руководство: Создание локального файла базы данных в Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="2a804-253">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>

3. <span data-ttu-id="2a804-254">Откройте контекстное меню для нового узла подключения и выберите **новый запрос**.</span><span class="sxs-lookup"><span data-stu-id="2a804-254">Open the shortcut menu for the new connection node, and select **New Query**.</span></span>

4. <span data-ttu-id="2a804-255">Скопируйте следующий скрипт SQL и вставьте его в редакторе запросов выберите **Execute** на панели инструментов или нажмите сочетание клавиш Ctrl + Shift + E.</span><span class="sxs-lookup"><span data-stu-id="2a804-255">Copy the following SQL script, paste it into the query editor, and then choose the **Execute** button on the toolbar or choose the Ctrl+Shift+E keys.</span></span>

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a><span data-ttu-id="2a804-256">См. также</span><span class="sxs-lookup"><span data-stu-id="2a804-256">See Also</span></span>
[<span data-ttu-id="2a804-257">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="2a804-257">Type Providers</span></span>](index.md)

[<span data-ttu-id="2a804-258">Поставщик типов SqlDataConnection</span><span class="sxs-lookup"><span data-stu-id="2a804-258">SqlDataConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[<span data-ttu-id="2a804-259">Пошаговое руководство: Создание типов F # из DBML-файла</span><span class="sxs-lookup"><span data-stu-id="2a804-259">Walkthrough: Generating F# Types from a DBML File</span></span>](generating-fsharp-types-from-dbml.md)

[<span data-ttu-id="2a804-260">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="2a804-260">Query Expressions</span></span>](../../language-reference/query-expressions.md)

[<span data-ttu-id="2a804-261">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2a804-261">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)

[<span data-ttu-id="2a804-262">SqlMetal.exe &#40; Средство создания кода &#41;</span><span class="sxs-lookup"><span data-stu-id="2a804-262">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)
