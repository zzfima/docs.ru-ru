---
title: "Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов и сущностей (F#)"
description: "Узнайте, как получить доступ к типизированным данным для базы данных SQL в зависимости от модели EDM ADO.NET в F # 3.0."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: e0e78e06fa1129ba5eeb73bc36c14343c93d6927
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a><span data-ttu-id="44674-104">Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов и сущностей</span><span class="sxs-lookup"><span data-stu-id="44674-104">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>

> [!NOTE]
<span data-ttu-id="44674-105">В этом руководстве, была написана для F # 3.0 и будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="44674-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="44674-106">Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](http://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="44674-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="44674-107">Справочные ссылки API, вы перейдете MSDN.</span><span class="sxs-lookup"><span data-stu-id="44674-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="44674-108">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="44674-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="44674-109">В этом пошаговом руководстве для F# 3.0 показывается, как получить доступ к типизированным данным для базы данных SQL на основе модели EDM ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="44674-109">This walkthrough for F# 3.0 shows you how to access typed data for a SQL database based on the ADO.NET Entity Data Model.</span></span> <span data-ttu-id="44674-110">В нем также рассматриваются настройка поставщика типов `SqlEntityConnection` языка F# для использования с базой данных SQL, правила написания запросов к данным, вызов хранимых процедур в базе данных, а также использование некоторых типов и методов ADO.NET Entity Framework для обновления базы данных.</span><span class="sxs-lookup"><span data-stu-id="44674-110">This walkthrough shows you how to set up the F# `SqlEntityConnection` type provider for use with a SQL database, how to write queries against the data, how to call stored procedures on the database, as well as how to use some of the ADO.NET Entity Framework types and methods to update the database.</span></span>

<span data-ttu-id="44674-111">В этом пошаговом руководстве описываются перечисленные ниже задачи, которые необходимо выполнить в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="44674-111">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="44674-112">Создание базы данных School</span><span class="sxs-lookup"><span data-stu-id="44674-112">Create the School database</span></span>
<br />

- <span data-ttu-id="44674-113">Создание и настройка проекта F#</span><span class="sxs-lookup"><span data-stu-id="44674-113">Create and configure an F# project</span></span>
<br />

- <span data-ttu-id="44674-114">Настройка поставщика типов и подключение к модели EDM</span><span class="sxs-lookup"><span data-stu-id="44674-114">Configure the type provider and connect to the Entity Data Model</span></span>
<br />

- <span data-ttu-id="44674-115">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="44674-115">Query the database</span></span>
<br />

- <span data-ttu-id="44674-116">Обновление базы данных</span><span class="sxs-lookup"><span data-stu-id="44674-116">Updating the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="44674-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="44674-117">Prerequisites</span></span>
<span data-ttu-id="44674-118">Необходимо иметь доступ к серверу с работающим программным обеспечением SQL Server, где можно создать базу данных для выполнения указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="44674-118">You must have access to a server that's running SQL Server where you can create a database to complete these steps.</span></span>

## <a name="create-the-school-database"></a><span data-ttu-id="44674-119">Создание базы данных School</span><span class="sxs-lookup"><span data-stu-id="44674-119">Create the School database</span></span>
<span data-ttu-id="44674-120">Базу данных School можно создать на любом сервере с работающим программным обеспечением SQL Server, к которому имеется административный доступ. Можно также использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="44674-120">You can create the School database on any server that's running SQL Server to which you have administrative access, or you can use LocalDB.</span></span>


#### <a name="to-create-the-school-database"></a><span data-ttu-id="44674-121">Действия для создания базы данных School</span><span class="sxs-lookup"><span data-stu-id="44674-121">To create the School database</span></span>

1. <span data-ttu-id="44674-122">В **обозревателя серверов**, откройте контекстное меню для **подключения к данным** узел и выберите **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="44674-122">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and then choose **Add Connection**.</span></span>
<br />  <span data-ttu-id="44674-123">**Добавить подключение** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="44674-123">The **Add Connection** dialog box appears.</span></span>
<br />

2. <span data-ttu-id="44674-124">В **имя сервера** поле, укажите имя экземпляра SQL Server, к которому имеется административный доступ или укажите (localdb\v11. 0), при отсутствии доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="44674-124">In the **Server name** box, specify the name of an instance of SQL Server to which you have administrative access, or specify (localdb\v11.0) if you don't have access to a server.</span></span>
<br />  <span data-ttu-id="44674-125">SQL Server Express LocalDB предоставляет упрощенный сервер базы данных для разработки и тестирования на компьютере.</span><span class="sxs-lookup"><span data-stu-id="44674-125">SQL Server Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="44674-126">Дополнительные сведения о LocalDB см. в разделе [Пошаговое руководство: Создание локального файла базы данных в Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="44674-126">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>
<br />  <span data-ttu-id="44674-127">Создается новый узел в **обозревателя серверов** под **подключения к данным**.</span><span class="sxs-lookup"><span data-stu-id="44674-127">A new node is created in **Server Explorer** under **Data Connections**.</span></span>
<br />

3. <span data-ttu-id="44674-128">Откройте контекстное меню для нового узла подключения и выберите **новый запрос**.</span><span class="sxs-lookup"><span data-stu-id="44674-128">Open the shortcut menu for the new connection node, and then choose **New Query**.</span></span>
<br />

4. <span data-ttu-id="44674-129">Откройте [Создание образца базы данных School](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) в веб-сайте Майкрософт, а затем скопировать и вставить скрипт базы данных, создает базу данных School в окно редактора.</span><span class="sxs-lookup"><span data-stu-id="44674-129">Open [Creating the School Sample Database](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) on the Microsoft website, and then copy and paste the database script that creates the School database into the editor window.</span></span>
<br />


## <span data-ttu-id="44674-130"><a name="BKMK_CreateConfigFSProj"> </a></span><span class="sxs-lookup"><span data-stu-id="44674-130"><a name="BKMK_CreateConfigFSProj"> </a></span></span>

## <a name="create-and-configure-an-f-project"></a><span data-ttu-id="44674-131">Создание и настройка проекта F#</span><span class="sxs-lookup"><span data-stu-id="44674-131">Create and configure an F# project</span></span>
<span data-ttu-id="44674-132">На данном шаге создается проект и он настраивается на использование поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="44674-132">In this step, you create a project and set it up to use a type provider.</span></span>


#### <a name="to-create-and-configure-an-f-project"></a><span data-ttu-id="44674-133">Действия для создания и настройки проекта F#</span><span class="sxs-lookup"><span data-stu-id="44674-133">To create and configure an F# project</span></span>

1. <span data-ttu-id="44674-134">Закройте предыдущий проект, создайте другой проект и назовите его **SchoolEDM**.</span><span class="sxs-lookup"><span data-stu-id="44674-134">Close the previous project, create another project, and name it **SchoolEDM**.</span></span>
<br />

2. <span data-ttu-id="44674-135">В **обозревателе решений**, откройте контекстное меню для **ссылки**и нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="44674-135">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="44674-136">Выберите **Framework** узел, а затем в **Framework** выберите **System.Data**, **System.Data.Entity**и **System.Data.Linq**.</span><span class="sxs-lookup"><span data-stu-id="44674-136">Choose the **Framework** node, and then, in the **Framework** list, choose **System.Data**, **System.Data.Entity**,  and **System.Data.Linq**.</span></span>
<br />

4. <span data-ttu-id="44674-137">Выберите **расширения** узел, добавьте ссылку на [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) сборки и нажмите кнопку **ОК** кнопку, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="44674-137">Choose the **Extensions** node, add a reference to the [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, and then choose the **OK** button to dismiss the dialog box.</span></span>
<br />

5. <span data-ttu-id="44674-138">Добавьте представленный ниже код для определения внутреннего модуля и откройте соответствующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="44674-138">Add the following code to define an internal module and open appropriate namespaces.</span></span> <span data-ttu-id="44674-139">Поставщик типов может вводить типы только в закрытое или внутреннее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="44674-139">The type provider can inject types only into a private or internal namespace.</span></span>
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. <span data-ttu-id="44674-140">Выполнение кода в этом пошаговом руководстве в интерактивном режиме в виде скрипта, а не как компилированной программы, откройте контекстное меню узла проекта, выберите **добавить новый элемент**, добавьте файл скрипта F # и затем добавьте код в каждом шаге в скрипт.</span><span class="sxs-lookup"><span data-stu-id="44674-140">To run the code in this walkthrough interactively as a script instead of as a compiled program, open the shortcut menu for the project node, choose **Add New Item**, add an F# script file, and then add the code in each step to the script.</span></span> <span data-ttu-id="44674-141">Для загрузки ссылок на сборку добавьте следующие строки.</span><span class="sxs-lookup"><span data-stu-id="44674-141">To load the assembly references, add the following lines.</span></span>
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. <span data-ttu-id="44674-142">Выделите каждый блок кода при его добавлении и нажмите клавиши Alt + ВВОД для запуска в F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="44674-142">Highlight each block of code as you add it, and choose the Alt + Enter keys to run it in F# Interactive.</span></span>
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="44674-143">Настройка поставщика типов и подключение к модели EDM</span><span class="sxs-lookup"><span data-stu-id="44674-143">Configure the type provider, and connect to the Entity Data Model</span></span>
<span data-ttu-id="44674-144">На этом шаге настраивается поставщик типов с подключением к данным и производится получение контекста данных, позволяющего работать с ними.</span><span class="sxs-lookup"><span data-stu-id="44674-144">In this step, you set up a type provider with a data connection and obtain a data context that allows you to work with data.</span></span>


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="44674-145">Действия для настройки поставщика типов и подключения к модели EDM</span><span class="sxs-lookup"><span data-stu-id="44674-145">To configure the type provider, and connect to the Entity Data Model</span></span>

1. <span data-ttu-id="44674-146">Введите представленный ниже код, чтобы настроить поставщик типов `SqlEntityConnection`, формирующий типы F# на основе ранее созданной модели EDM.</span><span class="sxs-lookup"><span data-stu-id="44674-146">Enter the following code to configure the `SqlEntityConnection` type provider that generates F# types based on the Entity Data Model that you created previously.</span></span> <span data-ttu-id="44674-147">Вместо полной строки подключения EDMX используйте только строку подключения SQL.</span><span class="sxs-lookup"><span data-stu-id="44674-147">Instead of the full EDMX connection string, use only the SQL connection string.</span></span>
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  <span data-ttu-id="44674-148">Это действие настраивает поставщик типов с созданным ранее подключением к базе данных.</span><span class="sxs-lookup"><span data-stu-id="44674-148">This action sets up a type provider with the database connection that you created earlier.</span></span> <span data-ttu-id="44674-149">Свойство `MultipleActiveResultSets` необходимо при использовании ADO.NET Entity Framework, поскольку допускает асинхронное выполнение нескольких команд для базы данных в одном подключении. Такое может часто происходить в коде ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="44674-149">The property `MultipleActiveResultSets` is needed when you use the ADO.NET Entity Framework because this property allows multiple commands to execute asynchronously on the database in one connection, which can occur frequently in ADO.NET Entity Framework code.</span></span> <span data-ttu-id="44674-150">Дополнительные сведения см. в разделе [Несколько активных результирующих наборов (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span><span class="sxs-lookup"><span data-stu-id="44674-150">For more information, see [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span></span>
<br />

2. <span data-ttu-id="44674-151">Получите контекст данных, который представляет собой объект, содержащий таблицы базы данных в качестве свойств и хранимые процедуры и функции базы данных в качестве методов.</span><span class="sxs-lookup"><span data-stu-id="44674-151">Get the data context, which is an object that contains the database tables as properties and the database stored procedures and functions as methods.</span></span>
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a><span data-ttu-id="44674-152">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="44674-152">Querying the database</span></span>
<span data-ttu-id="44674-153">На этом шаге используются выражения запросов F# для выполнения различных запросов к базе данных.</span><span class="sxs-lookup"><span data-stu-id="44674-153">In this step, you use F# query expressions to execute various queries on the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="44674-154">Действия для запроса данных</span><span class="sxs-lookup"><span data-stu-id="44674-154">To query the data</span></span>

- <span data-ttu-id="44674-155">Введите представленный ниже код для запроса данных из модели EDM.</span><span class="sxs-lookup"><span data-stu-id="44674-155">Enter the following code to query the data from the entity data model.</span></span> <span data-ttu-id="44674-156">Обратите внимание, что Pluralize = true изменяет таблицы базы данных Course на Courses и Person на People.</span><span class="sxs-lookup"><span data-stu-id="44674-156">Note the effect of Pluralize = true, which changes the database table Course to Courses and Person to People.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a><span data-ttu-id="44674-157">Обновление базы данных</span><span class="sxs-lookup"><span data-stu-id="44674-157">Updating the database</span></span>
<span data-ttu-id="44674-158">Для обновления базы данных можно использовать классы и методы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="44674-158">To update the database, you use the Entity Framework classes and methods.</span></span> <span data-ttu-id="44674-159">С поставщиком типов SQLEntityConnection можно использовать два типа контекста данных.</span><span class="sxs-lookup"><span data-stu-id="44674-159">You can use two types of data context with the SQLEntityConnection type provider.</span></span> <span data-ttu-id="44674-160">Первый тип `ServiceTypes.SimpleDataContextTypes.EntityContainer` является упрощенным контекстом данных, который содержит только предоставленные свойства, представляющие таблицы и столбцы базы данных.</span><span class="sxs-lookup"><span data-stu-id="44674-160">First, `ServiceTypes.SimpleDataContextTypes.EntityContainer` is the simplified data context, which includes only the provided properties that represent database tables and columns.</span></span> <span data-ttu-id="44674-161">Второй тип, полный контекст данных, — это экземпляр класса Entity Framework `System.Data.Objects.ObjectContext`, содержащий метод `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` для добавления строк в базу данных.</span><span class="sxs-lookup"><span data-stu-id="44674-161">Second, the full data context is an instance of the Entity Framework class `System.Data.Objects.ObjectContext`, which contains the method `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` to add rows to the database.</span></span> <span data-ttu-id="44674-162">Entity Framework распознает таблицы и отношения между ними, обеспечивая тем самым согласованность базы данных.</span><span class="sxs-lookup"><span data-stu-id="44674-162">The Entity Framework recognizes the tables and the relationships between them, so it enforces database consistency.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="44674-163">Обновление базы данных</span><span class="sxs-lookup"><span data-stu-id="44674-163">To update the database</span></span>

1. <span data-ttu-id="44674-164">Добавьте в программу представленный ниже код.</span><span class="sxs-lookup"><span data-stu-id="44674-164">Add the following code to your program.</span></span> <span data-ttu-id="44674-165">В этом примере добавляются два объекта с отношением между ними, а также инструктор и распределение аудиторий.</span><span class="sxs-lookup"><span data-stu-id="44674-165">In this example, you add two objects with a relationship between them, and you add an instructor and an office assignment.</span></span> <span data-ttu-id="44674-166">Таблица `OfficeAssignments` содержит столбец `InstructorID`, в котором имеется ссылка на столбец `PersonID` в таблице `Person`.</span><span class="sxs-lookup"><span data-stu-id="44674-166">The table `OfficeAssignments` contains the `InstructorID` column, which references the `PersonID` column in the `Person` table.</span></span>
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

<span data-ttu-id="44674-167">До вызова метода `System.Data.Objects.ObjectContext.SaveChanges` в базе данных ничего не изменяется.</span><span class="sxs-lookup"><span data-stu-id="44674-167">Nothing is changed in the database until you call `System.Data.Objects.ObjectContext.SaveChanges`.</span></span>
<br />

2. <span data-ttu-id="44674-168">Теперь восстановите предшествующее состояние базы данных, удалив добавленные объекты.</span><span class="sxs-lookup"><span data-stu-id="44674-168">Now restore the database to its earlier state by deleting the objects that you added.</span></span>
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
<span data-ttu-id="44674-169">При использовании выражения запроса необходимо помнить, что такой запрос подвержен отложенным вычислениям.</span><span class="sxs-lookup"><span data-stu-id="44674-169">When you use a query expression, you must remember that the query is subject to lazy evaluation.</span></span> <span data-ttu-id="44674-170">Поэтому база данных остается открытой для чтения при выполнении всех цепочек вычислений, например блоков лямбда-выражений после каждого выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="44674-170">Therefore, the database is still open for reading during any chained evaluations, such as in the lambda expression blocks after each query expression.</span></span> <span data-ttu-id="44674-171">Любая операция базы данных, явно или неявно использующая транзакцию, должна произойти после завершения операций чтения.</span><span class="sxs-lookup"><span data-stu-id="44674-171">Any database operation that explicitly or implicitly uses a transaction must occur after the read operations have completed.</span></span>


## <a name="next-steps"></a><span data-ttu-id="44674-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="44674-172">Next Steps</span></span>
<span data-ttu-id="44674-173">Исследовать другие параметры запроса, просмотрев операторы запроса, доступные в [выражения запросов](../../language-reference/query-expressions.md), а также просмотреть [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) чтобы понять, какие функции доступны при можно использовать этот поставщик типов.</span><span class="sxs-lookup"><span data-stu-id="44674-173">Explore other query options by reviewing the query operators available in [Query Expressions](../../language-reference/query-expressions.md), and also review the [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) to understand what functionality is available to you when you use this type provider.</span></span>


## <a name="see-also"></a><span data-ttu-id="44674-174">См. также</span><span class="sxs-lookup"><span data-stu-id="44674-174">See Also</span></span>
[<span data-ttu-id="44674-175">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="44674-175">Type Providers</span></span>](index.md)  
[<span data-ttu-id="44674-176">Поставщик типов SqlEntityConnection</span><span class="sxs-lookup"><span data-stu-id="44674-176">SqlEntityConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[<span data-ttu-id="44674-177">Пошаговое руководство: Создание типов F # из файла схемы EDMX</span><span class="sxs-lookup"><span data-stu-id="44674-177">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)  
[<span data-ttu-id="44674-178">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="44674-178">ADO.NET Entity Framework</span></span>](https://msdn.microsoft.com/library/bb399572)  
[<span data-ttu-id="44674-179">Общие сведения о файлах .edmx</span><span class="sxs-lookup"><span data-stu-id="44674-179">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[<span data-ttu-id="44674-180">Генератор модели EDM &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="44674-180">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)  
