---
title: Пошаговое руководство. Обработка данных (C#)
ms.date: 03/30/2017
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
ms.openlocfilehash: 2d45861569bc4a8b57427b01e107f87809203e11
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742730"
---
# <a name="walkthrough-manipulating-data-c"></a><span data-ttu-id="14641-102">Пошаговое руководство. Обработка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="14641-102">Walkthrough: Manipulating Data (C#)</span></span>
<span data-ttu-id="14641-103">В данном руководстве представлен основной и полный сценарий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] по добавлению, изменению и удалению данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="14641-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="14641-104">Для добавления клиента, изменения его имени и удаления заказа следует использовать копию учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="14641-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="14641-105">Это пошаговое руководство было написано с использованием параметров разработки Visual C#.</span><span class="sxs-lookup"><span data-stu-id="14641-105">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="14641-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="14641-106">Prerequisites</span></span>  
 <span data-ttu-id="14641-107">Необходимо выполнить следующие требования.</span><span class="sxs-lookup"><span data-stu-id="14641-107">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="14641-108">Для хранения файлов используется выделенная папка ("c:\linqtest6").</span><span class="sxs-lookup"><span data-stu-id="14641-108">This walkthrough uses a dedicated folder ("c:\linqtest6") to hold files.</span></span> <span data-ttu-id="14641-109">Прежде чем приступить к выполнению задач, создайте такую папку.</span><span class="sxs-lookup"><span data-stu-id="14641-109">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="14641-110">Наличие учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="14641-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="14641-111">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="14641-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="14641-112">Инструкции см. в разделе [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="14641-112">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="14641-113">После загрузки базы данных скопируйте файл northwnd.mdf в папку c:\linqtest6.</span><span class="sxs-lookup"><span data-stu-id="14641-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest6 folder.</span></span>  
  
- <span data-ttu-id="14641-114">Наличие файла кода C#, созданного из базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="14641-114">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="14641-115">Этот файл можно создать с помощью средства SQLMetal или реляционного конструктора объектов.</span><span class="sxs-lookup"><span data-stu-id="14641-115">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="14641-116">Данное пошаговое руководство было написано с использованием средства SQLMetal со следующей командной строкой:</span><span class="sxs-lookup"><span data-stu-id="14641-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="14641-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="14641-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="14641-118">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="14641-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="14641-119">Обзор</span><span class="sxs-lookup"><span data-stu-id="14641-119">Overview</span></span>  
 <span data-ttu-id="14641-120">Данное пошаговое руководство состоит из шести основных задач.</span><span class="sxs-lookup"><span data-stu-id="14641-120">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="14641-121">Создание [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] решения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="14641-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="14641-122">Добавление файла кода базы данных в проект.</span><span class="sxs-lookup"><span data-stu-id="14641-122">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="14641-123">Создание нового объекта клиента.</span><span class="sxs-lookup"><span data-stu-id="14641-123">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="14641-124">Изменение контактного имени клиента.</span><span class="sxs-lookup"><span data-stu-id="14641-124">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="14641-125">Удаление заказа.</span><span class="sxs-lookup"><span data-stu-id="14641-125">Deleting an order.</span></span>  
  
- <span data-ttu-id="14641-126">Отправка внесенных изменений в базу данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="14641-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="14641-127">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="14641-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="14641-128">В первой задаче создается решение Visual Studio, содержащее ссылки, необходимые для построения и запуска [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="14641-128">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="14641-129">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="14641-129">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="14641-130">В Visual Studio **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="14641-130">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="14641-131">В **типы проектов** области в **новый проект** диалоговом окне щелкните **Visual C#** .</span><span class="sxs-lookup"><span data-stu-id="14641-131">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3. <span data-ttu-id="14641-132">В области **Шаблоны** щелкните **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="14641-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="14641-133">В **имя** введите **LinqDataManipulationApp**.</span><span class="sxs-lookup"><span data-stu-id="14641-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="14641-134">В **расположение** убедитесь в том, где будут храниться файлы проекта.</span><span class="sxs-lookup"><span data-stu-id="14641-134">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6. <span data-ttu-id="14641-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="14641-135">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="14641-136">Добавление ссылок и директив LINQ</span><span class="sxs-lookup"><span data-stu-id="14641-136">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="14641-137">В этом пошаговом руководстве используются сборки, которые могут быть не установлены по умолчанию в проект.</span><span class="sxs-lookup"><span data-stu-id="14641-137">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="14641-138">Если System.Data.Linq не входит в список ссылок проекта, добавьте ее, как описано в следующих действиях.</span><span class="sxs-lookup"><span data-stu-id="14641-138">If System.Data.Linq is not listed as a reference in your project, add it, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="14641-139">Добавление сборки System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="14641-139">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="14641-140">В **обозревателе решений**, щелкните правой кнопкой мыши **ссылки**, а затем нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="14641-140">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="14641-141">В **добавить ссылку** диалоговом окне щелкните **.NET**, выберите сборку System.Data.Linq, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="14641-141">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="14641-142">Сборка будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="14641-142">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="14641-143">Добавьте следующие директивы в начало Program.cs.</span><span class="sxs-lookup"><span data-stu-id="14641-143">Add the following directives at the top of Program.cs:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="14641-144">Добавление файла кода Northwind в проект</span><span class="sxs-lookup"><span data-stu-id="14641-144">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="14641-145">При выполнении этих действий подразумевается, что для создания файла кода из учебной базы данных Northwind использовалось средство SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="14641-145">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="14641-146">Дополнительные сведения см. в разделе "Предварительные требования" ранее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="14641-146">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="14641-147">Добавление файла кода northwind в проект</span><span class="sxs-lookup"><span data-stu-id="14641-147">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="14641-148">На **проекта** меню, щелкните **добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="14641-148">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="14641-149">В **добавить существующий элемент** диалоговом окне перейдите к c:\linqtest6\northwind.cs и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="14641-149">In the **Add Existing Item** dialog box, navigate to c:\linqtest6\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="14641-150">Файл northwind.cs будет добавлен в проект.</span><span class="sxs-lookup"><span data-stu-id="14641-150">The northwind.cs file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="14641-151">Настройка подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="14641-151">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="14641-152">Сначала проверьте подключение к базе данных.</span><span class="sxs-lookup"><span data-stu-id="14641-152">First, test your connection to the database.</span></span> <span data-ttu-id="14641-153">Обратите особое внимание, что в имени базы данных - Northwnd - отсутствует буква "i".</span><span class="sxs-lookup"><span data-stu-id="14641-153">Note especially that the database, Northwnd, has no i character.</span></span> <span data-ttu-id="14641-154">Если при выполнении следующих действий возникают ошибки, просмотрите файл northwind.cs, чтобы определить написание разделяемого класса Northwind.</span><span class="sxs-lookup"><span data-stu-id="14641-154">If you generate errors in the next steps, review the northwind.cs file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="14641-155">Настройка и проверка подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="14641-155">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="14641-156">Введите или вставьте следующий код в метод `Main` в классе Program.</span><span class="sxs-lookup"><span data-stu-id="14641-156">Type or paste the following code into the `Main` method in the Program class:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2. <span data-ttu-id="14641-157">Чтобы проверить приложение на этом этапе, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="14641-157">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="14641-158">Объект **консоли** откроется окно.</span><span class="sxs-lookup"><span data-stu-id="14641-158">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="14641-159">Можно закрыть приложение, нажав клавишу ВВОД в **консоли** окна, или щелкнув **остановить отладку** на Visual Studio **Отладка** меню.</span><span class="sxs-lookup"><span data-stu-id="14641-159">You can close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="14641-160">Создание новой сущности</span><span class="sxs-lookup"><span data-stu-id="14641-160">Creating a New Entity</span></span>  
 <span data-ttu-id="14641-161">Создание новой сущности не представляет особых проблем.</span><span class="sxs-lookup"><span data-stu-id="14641-161">Creating a new entity is straightforward.</span></span> <span data-ttu-id="14641-162">Для создания объектов (например, `Customer`) можно использовать ключевое слово `new`.</span><span class="sxs-lookup"><span data-stu-id="14641-162">You can create objects (such as `Customer`) by using the `new` keyword.</span></span>  
  
 <span data-ttu-id="14641-163">В этом и следующих разделах выполняются изменения только локального кэша.</span><span class="sxs-lookup"><span data-stu-id="14641-163">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="14641-164">Изменения не будут отправлены в базу данных до тех пор, пока ближе к концу данного руководства не будет вызван <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="14641-164">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="14641-165">Добавление нового объекта сущностей Customer</span><span class="sxs-lookup"><span data-stu-id="14641-165">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="14641-166">Создайте новый `Customer`, добавив перед `Console.ReadLine();`в методе `Main` следующий код.</span><span class="sxs-lookup"><span data-stu-id="14641-166">Create a new `Customer` by adding the following code before `Console.ReadLine();` in the `Main` method:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2. <span data-ttu-id="14641-167">Нажмите клавишу F5 для отладки решения.</span><span class="sxs-lookup"><span data-stu-id="14641-167">Press F5 to debug the solution.</span></span>  
  
3. <span data-ttu-id="14641-168">Нажмите клавишу ВВОД в **консоли** окно, чтобы остановить отладку и продолжить выполнение других действий.</span><span class="sxs-lookup"><span data-stu-id="14641-168">Press Enter in the **Console** window to stop debugging and continue the walkthrough.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="14641-169">Обновление сущности</span><span class="sxs-lookup"><span data-stu-id="14641-169">Updating an Entity</span></span>  
 <span data-ttu-id="14641-170">При выполнении следующих действий будет извлечен объект `Customer` и изменено одно из его свойств.</span><span class="sxs-lookup"><span data-stu-id="14641-170">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="14641-171">Изменение имени клиента</span><span class="sxs-lookup"><span data-stu-id="14641-171">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="14641-172">Добавьте следующий код перед `Console.ReadLine();`:</span><span class="sxs-lookup"><span data-stu-id="14641-172">Add the following code above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="14641-173">Удаление сущности</span><span class="sxs-lookup"><span data-stu-id="14641-173">Deleting an Entity</span></span>  
 <span data-ttu-id="14641-174">Используя тот же самый объект клиента, можно удалить первый заказ.</span><span class="sxs-lookup"><span data-stu-id="14641-174">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="14641-175">В следующем коде показано, как разорвать связь между строками и удалить строку из базы данных.</span><span class="sxs-lookup"><span data-stu-id="14641-175">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span> <span data-ttu-id="14641-176">Чтобы удаление объектов, добавьте следующий код перед `Console.ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="14641-176">Add the following code before `Console.ReadLine` to see how objects can be deleted:</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="14641-177">Удаление строки</span><span class="sxs-lookup"><span data-stu-id="14641-177">To delete a row</span></span>  
  
- <span data-ttu-id="14641-178">Добавьте следующий код перед `Console.ReadLine();`.</span><span class="sxs-lookup"><span data-stu-id="14641-178">Add the following code just above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="14641-179">Отправка изменений в базу данных</span><span class="sxs-lookup"><span data-stu-id="14641-179">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="14641-180">Последнее действие, необходимое для создания, обновления и удаления объектов, заключается в фактической отправке изменений в базу данных.</span><span class="sxs-lookup"><span data-stu-id="14641-180">The final step required for creating, updating, and deleting objects, is to actually submit the changes to the database.</span></span> <span data-ttu-id="14641-181">Без него изменения останутся на локальном уровне и не появятся в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="14641-181">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="14641-182">Отправка изменений в базу данных</span><span class="sxs-lookup"><span data-stu-id="14641-182">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="14641-183">Вставьте следующий код перед `Console.ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="14641-183">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2. <span data-ttu-id="14641-184">Вставьте следующий код (после `SubmitChanges`), чтобы показать результаты до и после отправки изменений.</span><span class="sxs-lookup"><span data-stu-id="14641-184">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3. <span data-ttu-id="14641-185">Нажмите клавишу F5 для отладки решения.</span><span class="sxs-lookup"><span data-stu-id="14641-185">Press F5 to debug the solution.</span></span>  
  
4. <span data-ttu-id="14641-186">Нажмите клавишу ВВОД в **консоли** окна, чтобы закрыть приложение.</span><span class="sxs-lookup"><span data-stu-id="14641-186">Press Enter in the **Console** window to close the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14641-187">После добавления нового клиента путем отправки изменений это решение нельзя повторно выполнить в исходном виде.</span><span class="sxs-lookup"><span data-stu-id="14641-187">After you have added the new customer by submitting the changes, you cannot execute this solution again as is.</span></span> <span data-ttu-id="14641-188">Для повторного выполнения решения измените имя клиента и значение идентификатора добавляемого клиента.</span><span class="sxs-lookup"><span data-stu-id="14641-188">To execute the solution again, change the name of the customer and customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14641-189">См. также</span><span class="sxs-lookup"><span data-stu-id="14641-189">See also</span></span>

- [<span data-ttu-id="14641-190">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="14641-190">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
