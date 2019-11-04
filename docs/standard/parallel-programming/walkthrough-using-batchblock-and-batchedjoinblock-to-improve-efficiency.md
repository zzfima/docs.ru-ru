---
title: Пошаговое руководство. Повышение эффективности с помощью BatchBlock и BatchedJoinBlock
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
ms.openlocfilehash: 4b2b6a6124bf8cc0fb3b379607135283678e3268
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091362"
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a><span data-ttu-id="c5830-102">Пошаговое руководство. Повышение эффективности с помощью BatchBlock и BatchedJoinBlock</span><span class="sxs-lookup"><span data-stu-id="c5830-102">Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency</span></span>

<span data-ttu-id="c5830-103">Библиотека потоков данных TPL предоставляет классы <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType>, чтобы пользователь мог получать и помещать в буфер данные из одного или нескольких источников и затем передавать эти помещенные в буфер данные в виде одной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c5830-103">The TPL Dataflow Library provides the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classes so that you can receive and buffer data from one or more sources and then propagate out that buffered data as one collection.</span></span> <span data-ttu-id="c5830-104">Этот механизм пакетной обработки полезен при сборе данных из одного или нескольких источников и дальнейшей обработке различных элементов данных в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="c5830-104">This batching mechanism is useful when you collect data from one or more sources and then process multiple data elements as a batch.</span></span> <span data-ttu-id="c5830-105">Например, рассмотрим приложение, использующее поток данных для вставки записей в базу данных.</span><span class="sxs-lookup"><span data-stu-id="c5830-105">For example, consider an application that uses dataflow to insert records into a database.</span></span> <span data-ttu-id="c5830-106">Эта операция может быть эффективнее, если несколько элементов добавляются одновременно, а не последовательно по одному.</span><span class="sxs-lookup"><span data-stu-id="c5830-106">This operation can be more efficient if multiple items are inserted at the same time instead of one at a time sequentially.</span></span> <span data-ttu-id="c5830-107">В этом документе описано, как использовать класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> для увеличения эффективности подобных операций вставки в базу данных.</span><span class="sxs-lookup"><span data-stu-id="c5830-107">This document describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to improve the efficiency of such database insert operations.</span></span> <span data-ttu-id="c5830-108">Также здесь приводится способ использования класса <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> для перехвата и результатов, и всех исключений, возникающих при выполнении программой считывания из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c5830-108">It also describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to capture both the results and any exceptions that occur when the program reads from a database.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a><span data-ttu-id="c5830-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c5830-109">Prerequisites</span></span>

1. <span data-ttu-id="c5830-110">Прочитайте описание блоков объединения в документации по [потокам данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md), прежде чем приступать к этому руководству.</span><span class="sxs-lookup"><span data-stu-id="c5830-110">Read the Join Blocks section in the [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) document before you start this walkthrough.</span></span>

2. <span data-ttu-id="c5830-111">Убедитесь, что на вашем компьютере есть копия базы данных Northwind, Northwind.sdf.</span><span class="sxs-lookup"><span data-stu-id="c5830-111">Ensure that you have a copy of the Northwind database, Northwind.sdf, available on your computer.</span></span> <span data-ttu-id="c5830-112">Этот файл обычно находится в папке %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span><span class="sxs-lookup"><span data-stu-id="c5830-112">This file is typically located in the folder %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c5830-113">В некоторых версиях Windows вы не сможете подключиться к Northwind.sdf, если Visual Studio работает не в режиме администратора.</span><span class="sxs-lookup"><span data-stu-id="c5830-113">In some versions of Windows, you cannot connect to Northwind.sdf if Visual Studio is running in a non-administrator mode.</span></span> <span data-ttu-id="c5830-114">Для подключения к Northwind.sdf запустите Visual Studio или командную строку разработчика для Visual Studio в режиме **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="c5830-114">To connect to Northwind.sdf, start Visual Studio or a Developer Command Prompt for Visual Studio in the **Run as administrator** mode.</span></span>

<span data-ttu-id="c5830-115">Это пошаговое руководство содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="c5830-115">This walkthrough contains the following sections:</span></span>

- [<span data-ttu-id="c5830-116">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="c5830-116">Creating the Console Application</span></span>](#creating)

- [<span data-ttu-id="c5830-117">Определение класса сотрудников</span><span class="sxs-lookup"><span data-stu-id="c5830-117">Defining the Employee Class</span></span>](#employeeClass)

- [<span data-ttu-id="c5830-118">Определение операций базы данных сотрудников</span><span class="sxs-lookup"><span data-stu-id="c5830-118">Defining Employee Database Operations</span></span>](#operations)

- [<span data-ttu-id="c5830-119">Добавление данных о сотруднике в базу данных без буферизации</span><span class="sxs-lookup"><span data-stu-id="c5830-119">Adding Employee Data to the Database without Using Buffering</span></span>](#nonBuffering)

- [<span data-ttu-id="c5830-120">Использование буферизации для добавления данных о сотруднике в базу данных</span><span class="sxs-lookup"><span data-stu-id="c5830-120">Using Buffering to Add Employee Data to the Database</span></span>](#buffering)

- [<span data-ttu-id="c5830-121">Использование объединения буферизированных данных для считывания данных о сотруднике из базы данных</span><span class="sxs-lookup"><span data-stu-id="c5830-121">Using Buffered Join to Read Employee Data from the Database</span></span>](#bufferedJoin)

- [<span data-ttu-id="c5830-122">Полный пример</span><span class="sxs-lookup"><span data-stu-id="c5830-122">The Complete Example</span></span>](#complete)

<a name="creating"></a>

## <a name="creating-the-console-application"></a><span data-ttu-id="c5830-123">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="c5830-123">Creating the Console Application</span></span>

1. <span data-ttu-id="c5830-124">В Visual Studio создайте проект **Консольное приложение** на Visual C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c5830-124">In Visual Studio, create a Visual C# or Visual Basic **Console Application** project.</span></span> <span data-ttu-id="c5830-125">В этом документе проект называется `DataflowBatchDatabase`.</span><span class="sxs-lookup"><span data-stu-id="c5830-125">In this document, the project is named `DataflowBatchDatabase`.</span></span>

2. <span data-ttu-id="c5830-126">В проект добавьте ссылку на System.Data.SqlServerCe.dll и ссылку на System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="c5830-126">In your project, add a reference to System.Data.SqlServerCe.dll and a reference to System.Threading.Tasks.Dataflow.dll.</span></span>

3. <span data-ttu-id="c5830-127">Убедитесь, что Form1.cs (Form1.vb для Visual Basic) содержит следующие операторы `using` (`Imports` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c5830-127">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` (`Imports` in Visual Basic) statements.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
    [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]

4. <span data-ttu-id="c5830-128">Добавьте в класс `Program` следующие данные-члены.</span><span class="sxs-lookup"><span data-stu-id="c5830-128">Add the following data members to the `Program` class.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
    [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]

<a name="employeeClass"></a>

## <a name="defining-the-employee-class"></a><span data-ttu-id="c5830-129">Определение класса "Сотрудник"</span><span class="sxs-lookup"><span data-stu-id="c5830-129">Defining the Employee Class</span></span>

<span data-ttu-id="c5830-130">Добавьте в класс `Program` класс `Employee`.</span><span class="sxs-lookup"><span data-stu-id="c5830-130">Add to the `Program` class the `Employee` class.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
[!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]

<span data-ttu-id="c5830-131">В классе `Employee` содержатся три свойства: `EmployeeID`, `LastName` и `FirstName`,</span><span class="sxs-lookup"><span data-stu-id="c5830-131">The `Employee` class contains three properties, `EmployeeID`, `LastName`, and `FirstName`.</span></span> <span data-ttu-id="c5830-132">Эти свойства соответствуют столбцам `Employee ID`, `Last Name` и `First Name` в таблице `Employees` в базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="c5830-132">These properties correspond to the `Employee ID`, `Last Name`, and `First Name` columns in the `Employees` table in the Northwind database.</span></span> <span data-ttu-id="c5830-133">Для этого примера в классе `Employee` также определяется метод `Random`, который создает объект `Employee` со случайными значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="c5830-133">For this demonstration, the `Employee` class also defines the `Random` method, which creates an `Employee` object that has random values for its properties.</span></span>

<a name="operations"></a>

## <a name="defining-employee-database-operations"></a><span data-ttu-id="c5830-134">Определение операций базы данных сотрудников</span><span class="sxs-lookup"><span data-stu-id="c5830-134">Defining Employee Database Operations</span></span>

<span data-ttu-id="c5830-135">Добавьте в класс `Program` методы `InsertEmployees`, `GetEmployeeCount` и `GetEmployeeID`.</span><span class="sxs-lookup"><span data-stu-id="c5830-135">Add to the `Program` class the `InsertEmployees`, `GetEmployeeCount`, and `GetEmployeeID` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
[!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]

<span data-ttu-id="c5830-136">Метод `InsertEmployees` добавляет новые записи "Сотрудник" в базу данных.</span><span class="sxs-lookup"><span data-stu-id="c5830-136">The `InsertEmployees` method adds new employee records to the database.</span></span> <span data-ttu-id="c5830-137">Метод `GetEmployeeCount` получает число записей в таблице `Employees`.</span><span class="sxs-lookup"><span data-stu-id="c5830-137">The `GetEmployeeCount` method retrieves the number of entries in the `Employees` table.</span></span> <span data-ttu-id="c5830-138">Метод `GetEmployeeID` получает идентификатор первого сотрудника с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c5830-138">The `GetEmployeeID` method retrieves the identifier of the first employee that has the provided name.</span></span> <span data-ttu-id="c5830-139">Каждый из этих методов принимает строку подключения к базе данных Northwind и использует функциональные возможности пространства имен `System.Data.SqlServerCe` для обмена данными с базой данных.</span><span class="sxs-lookup"><span data-stu-id="c5830-139">Each of these methods takes a connection string to the Northwind database and uses functionality in the `System.Data.SqlServerCe` namespace to communicate with the database.</span></span>

<a name="nonBuffering"></a>

## <a name="adding-employee-data-to-the-database-without-using-buffering"></a><span data-ttu-id="c5830-140">Добавление данных о сотруднике в базу данных без использования буферизации</span><span class="sxs-lookup"><span data-stu-id="c5830-140">Adding Employee Data to the Database Without Using Buffering</span></span>

<span data-ttu-id="c5830-141">Добавьте в класс `Program` методы `AddEmployees` и `PostRandomEmployees`.</span><span class="sxs-lookup"><span data-stu-id="c5830-141">Add to the `Program` class the `AddEmployees` and `PostRandomEmployees` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
[!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]

<span data-ttu-id="c5830-142">Метод `AddEmployees` добавляет случайные данные о сотрудниках в базу данных с помощью потока данных.</span><span class="sxs-lookup"><span data-stu-id="c5830-142">The `AddEmployees` method adds random employee data to the database by using dataflow.</span></span> <span data-ttu-id="c5830-143">Он создает объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, который вызывает метод `InsertEmployees` для добавления записи о сотруднике в базу данных.</span><span class="sxs-lookup"><span data-stu-id="c5830-143">It creates an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that calls the `InsertEmployees` method to add an employee entry to the database.</span></span> <span data-ttu-id="c5830-144">Метод `AddEmployees` затем вызывает метод `PostRandomEmployees` для прикрепления нескольких объектов `Employee` к объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="c5830-144">The `AddEmployees` method then calls the `PostRandomEmployees` method to post multiple `Employee` objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="c5830-145">Метод `AddEmployees` затем ожидает завершения всех операций вставки.</span><span class="sxs-lookup"><span data-stu-id="c5830-145">The `AddEmployees` method then waits for all insert operations to finish.</span></span>

<a name="buffering"></a>

## <a name="using-buffering-to-add-employee-data-to-the-database"></a><span data-ttu-id="c5830-146">Использование буферизации для добавления данных о сотруднике в базу данных</span><span class="sxs-lookup"><span data-stu-id="c5830-146">Using Buffering to Add Employee Data to the Database</span></span>

<span data-ttu-id="c5830-147">Добавьте метод `Program` в класс `AddEmployeesBatched`.</span><span class="sxs-lookup"><span data-stu-id="c5830-147">Add to the `Program` class the `AddEmployeesBatched` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
[!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]

<span data-ttu-id="c5830-148">Этот метод похож на `AddEmployees` за исключением того, что он использует класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> для буферизации нескольких объектов `Employee` перед их отправкой объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="c5830-148">This method resembles `AddEmployees`, except that it also uses the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to buffer multiple `Employee` objects before it sends those objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="c5830-149">Поскольку класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> выдает на выходе несколько элементов в виде коллекции, объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> изменяется для работы с массивом объектов `Employee`.</span><span class="sxs-lookup"><span data-stu-id="c5830-149">Because the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class propagates out multiple elements as a collection, the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object is modified to act on an array of `Employee` objects.</span></span> <span data-ttu-id="c5830-150">Как и в методе `AddEmployees`, `AddEmployeesBatched` вызывает метод `PostRandomEmployees` для отправки нескольких объектов `Employee`; однако `AddEmployeesBatched` отправляет эти объекты объекту <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="c5830-150">As in the `AddEmployees` method, `AddEmployeesBatched` calls the `PostRandomEmployees` method to post multiple `Employee` objects; however, `AddEmployeesBatched` posts these objects to the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> object.</span></span> <span data-ttu-id="c5830-151">Метод `AddEmployeesBatched` также ожидает завершения всех операций вставки.</span><span class="sxs-lookup"><span data-stu-id="c5830-151">The `AddEmployeesBatched`  method also waits for all insert operations to finish.</span></span>

<a name="bufferedJoin"></a>

## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a><span data-ttu-id="c5830-152">Использование объединения буферизированных данных для считывания данных о сотруднике из базы данных</span><span class="sxs-lookup"><span data-stu-id="c5830-152">Using Buffered Join to Read Employee Data from the Database</span></span>

<span data-ttu-id="c5830-153">Добавьте метод `Program` в класс `GetRandomEmployees`.</span><span class="sxs-lookup"><span data-stu-id="c5830-153">Add to the `Program` class the `GetRandomEmployees` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
[!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]

<span data-ttu-id="c5830-154">Этот метод выводит сведения о случайных сотрудниках на консоль.</span><span class="sxs-lookup"><span data-stu-id="c5830-154">This method prints information about random employees to the console.</span></span> <span data-ttu-id="c5830-155">Он создает несколько произвольных объектов `Employee` и вызывает метод `GetEmployeeID` для извлечения уникального идентификатора каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="c5830-155">It creates several random `Employee` objects and calls the `GetEmployeeID` method to retrieve the unique identifier for each object.</span></span> <span data-ttu-id="c5830-156">Поскольку метод `GetEmployeeID` создает исключение, если не найден сотрудник с данным именем и фамилией, метод `GetRandomEmployees` использует класс <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> для хранения объектов `Employee` в случае успешного вызова объектов `GetEmployeeID` и <xref:System.Exception?displayProperty=nameWithType> для вызовов, которые завершились ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c5830-156">Because the `GetEmployeeID` method throws an exception if there is no matching employee with the given first and last names, the `GetRandomEmployees` method uses the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to store `Employee` objects for successful calls to `GetEmployeeID` and <xref:System.Exception?displayProperty=nameWithType> objects for calls that fail.</span></span> <span data-ttu-id="c5830-157">Объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> в этом примере работает с объектом <xref:System.Tuple%602>, содержащим список объектов `Employee` и список объектов <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="c5830-157">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object in this example acts on a <xref:System.Tuple%602> object that holds a list of `Employee` objects and a list of <xref:System.Exception> objects.</span></span> <span data-ttu-id="c5830-158">Объект <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> передает эти данные, когда в сумме количество полученных объектов `Employee` и <xref:System.Exception> равняется размеру пакета.</span><span class="sxs-lookup"><span data-stu-id="c5830-158">The <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> object propagates out this data when the sum of the received `Employee` and <xref:System.Exception> object counts equals the batch size.</span></span>

<a name="complete"></a>

## <a name="the-complete-example"></a><span data-ttu-id="c5830-159">Полный пример</span><span class="sxs-lookup"><span data-stu-id="c5830-159">The Complete Example</span></span>

<span data-ttu-id="c5830-160">В следующем примере показан полный код.</span><span class="sxs-lookup"><span data-stu-id="c5830-160">The following example shows the complete code.</span></span> <span data-ttu-id="c5830-161">Метод `Main` сравнивает время выполнения пакетной вставки в базу данных и время выполнения непакетной вставки.</span><span class="sxs-lookup"><span data-stu-id="c5830-161">The `Main` method compares the time that is required to perform batched database insertions versus the time to perform non-batched database insertions.</span></span> <span data-ttu-id="c5830-162">Здесь также демонстрируется использование объединения буферизированных данных для чтения сведений о сотруднике из базы данных, помимо этого он докладывает об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c5830-162">It also demonstrates the use of buffered join to read employee data from the database and also report errors.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
[!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]

## <a name="see-also"></a><span data-ttu-id="c5830-163">См. также</span><span class="sxs-lookup"><span data-stu-id="c5830-163">See also</span></span>

- [<span data-ttu-id="c5830-164">Поток данных</span><span class="sxs-lookup"><span data-stu-id="c5830-164">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
