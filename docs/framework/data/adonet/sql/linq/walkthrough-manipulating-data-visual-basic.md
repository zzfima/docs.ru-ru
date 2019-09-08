---
title: Пошаговое руководство. Обработка данных (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: a74216c53c45790b974938c7155e0b5e1043ac13
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792285"
---
# <a name="walkthrough-manipulating-data-visual-basic"></a><span data-ttu-id="7817a-102">Пошаговое руководство. Обработка данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7817a-102">Walkthrough: Manipulating Data (Visual Basic)</span></span>
<span data-ttu-id="7817a-103">В данном руководстве представлен основной и полный сценарий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] по добавлению, изменению и удалению данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7817a-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="7817a-104">Для добавления клиента, изменения его имени и удаления заказа следует использовать копию учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="7817a-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="7817a-105">Это пошаговое руководство было написано с помощью параметров разработки Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7817a-105">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7817a-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7817a-106">Prerequisites</span></span>  
 <span data-ttu-id="7817a-107">Необходимо выполнить следующие требования.</span><span class="sxs-lookup"><span data-stu-id="7817a-107">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="7817a-108">Для хранения файлов используется выделенная папка ("c:\linqtest2").</span><span class="sxs-lookup"><span data-stu-id="7817a-108">This walkthrough uses a dedicated folder ("c:\linqtest2") to hold files.</span></span> <span data-ttu-id="7817a-109">Прежде чем приступить к выполнению задач, создайте такую папку.</span><span class="sxs-lookup"><span data-stu-id="7817a-109">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="7817a-110">Наличие учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="7817a-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="7817a-111">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7817a-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="7817a-112">Инструкции см. в разделе [Загрузка образцов баз данных](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7817a-112">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="7817a-113">После загрузки базы данных скопируйте файл northwnd.mdf в папку c:\linqtest2.</span><span class="sxs-lookup"><span data-stu-id="7817a-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest2 folder.</span></span>  
  
- <span data-ttu-id="7817a-114">Наличие файла кода Visual Basic, созданного из базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="7817a-114">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="7817a-115">Этот файл можно создать с помощью реляционный конструктор объектов или средства SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="7817a-115">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="7817a-116">Данное пошаговое руководство было написано с использованием средства SQLMetal со следующей командной строкой:</span><span class="sxs-lookup"><span data-stu-id="7817a-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="7817a-117">**SQLMetal/Code: "c:\linqtest2\northwind.vb"/Language: VB "C:\linqtest2\northwnd.mdf"/плурализе**</span><span class="sxs-lookup"><span data-stu-id="7817a-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="7817a-118">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="7817a-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="7817a-119">Обзор</span><span class="sxs-lookup"><span data-stu-id="7817a-119">Overview</span></span>  
 <span data-ttu-id="7817a-120">Данное пошаговое руководство состоит из шести основных задач.</span><span class="sxs-lookup"><span data-stu-id="7817a-120">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="7817a-121">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Создание решения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7817a-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="7817a-122">Добавление файла кода базы данных в проект.</span><span class="sxs-lookup"><span data-stu-id="7817a-122">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="7817a-123">Создание нового объекта клиента.</span><span class="sxs-lookup"><span data-stu-id="7817a-123">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="7817a-124">Изменение контактного имени клиента.</span><span class="sxs-lookup"><span data-stu-id="7817a-124">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="7817a-125">Удаление заказа.</span><span class="sxs-lookup"><span data-stu-id="7817a-125">Deleting an order.</span></span>  
  
- <span data-ttu-id="7817a-126">Отправка внесенных изменений в базу данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="7817a-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="7817a-127">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7817a-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="7817a-128">В этой первой задаче вы создадите решение Visual Studio, содержащее необходимые ссылки для сборки и запуска [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="7817a-128">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="7817a-129">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7817a-129">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="7817a-130">В меню **Файл** Visual Studio выберите команду **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="7817a-130">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="7817a-131">В области **типы проектов** диалогового окна **Новый проект** нажмите кнопку **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="7817a-131">In the **Project types** pane in the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3. <span data-ttu-id="7817a-132">В области **Шаблоны** щелкните **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="7817a-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="7817a-133">В поле **имя** введите **линкдатаманипулатионапп**.</span><span class="sxs-lookup"><span data-stu-id="7817a-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="7817a-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7817a-134">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="7817a-135">Добавление ссылок и директив LINQ</span><span class="sxs-lookup"><span data-stu-id="7817a-135">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="7817a-136">В этом пошаговом руководстве используются сборки, которые могут быть не установлены по умолчанию в проект.</span><span class="sxs-lookup"><span data-stu-id="7817a-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="7817a-137">Если `System.Data.Linq` в проекте нет списка (щелкните **Показывать все файлы** в **Обозреватель решений** и разверните узел **ссылки** ), добавьте его, как описано в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="7817a-137">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="7817a-138">Добавление сборки System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="7817a-138">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="7817a-139">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **ссылки**и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="7817a-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="7817a-140">В диалоговом окне **Добавление ссылки** щелкните **.NET**, выберите сборку System. Data. LINQ и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7817a-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7817a-141">Сборка будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="7817a-141">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="7817a-142">В редакторе кода добавьте следующие директивы над **Module1**:</span><span class="sxs-lookup"><span data-stu-id="7817a-142">In the code editor, add the following directives above **Module1**:</span></span>  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="7817a-143">Добавление файла кода Northwind в проект</span><span class="sxs-lookup"><span data-stu-id="7817a-143">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="7817a-144">При выполнении этих действий подразумевается, что для создания файла кода из учебной базы данных Northwind использовалось средство SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="7817a-144">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="7817a-145">Дополнительные сведения см. в разделе "Предварительные требования" ранее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="7817a-145">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="7817a-146">Добавление файла кода northwind в проект</span><span class="sxs-lookup"><span data-stu-id="7817a-146">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="7817a-147">В меню **проект** выберите команду **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="7817a-147">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="7817a-148">В диалоговом окне **Добавление существующего элемента** перейдите к c:\linqtest2\northwind.vb и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7817a-148">In the **Add Existing Item** dialog box, navigate to c:\linqtest2\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="7817a-149">Файл northwind.vb будет добавлен в проект.</span><span class="sxs-lookup"><span data-stu-id="7817a-149">The northwind.vb file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="7817a-150">Настройка подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="7817a-150">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="7817a-151">Сначала проверьте подключение к базе данных.</span><span class="sxs-lookup"><span data-stu-id="7817a-151">First, test your connection to the database.</span></span> <span data-ttu-id="7817a-152">Обратите особое внимание, что в имени базы данных - Northwnd - отсутствует буква "i".</span><span class="sxs-lookup"><span data-stu-id="7817a-152">Note especially that the name of the database, Northwnd, has no i character.</span></span> <span data-ttu-id="7817a-153">Если при выполнении следующих действий возникают ошибки, просмотрите файл northwind.vb, чтобы определить написание разделяемого класса Northwind.</span><span class="sxs-lookup"><span data-stu-id="7817a-153">If you generate errors in the next steps, review the northwind.vb file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="7817a-154">Настройка и проверка подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="7817a-154">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="7817a-155">Введите или вставьте следующий код в `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="7817a-155">Type or paste the following code into `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2. <span data-ttu-id="7817a-156">Чтобы проверить приложение на этом этапе, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="7817a-156">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="7817a-157">Откроется окно **консоли** .</span><span class="sxs-lookup"><span data-stu-id="7817a-157">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="7817a-158">Закройте приложение, нажав клавишу ВВОД в окне **консоли** или выбрав пункт **прерывать отладку** в меню **Отладка** Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7817a-158">Close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="7817a-159">Создание новой сущности</span><span class="sxs-lookup"><span data-stu-id="7817a-159">Creating a New Entity</span></span>  
 <span data-ttu-id="7817a-160">Создание новой сущности не представляет особых проблем.</span><span class="sxs-lookup"><span data-stu-id="7817a-160">Creating a new entity is straightforward.</span></span> <span data-ttu-id="7817a-161">Для создания объектов (например, `Customer`) можно использовать ключевое слово `New`.</span><span class="sxs-lookup"><span data-stu-id="7817a-161">You can create objects (such as `Customer`) by using the `New` keyword.</span></span>  
  
 <span data-ttu-id="7817a-162">В этом и следующих разделах выполняются изменения только локального кэша.</span><span class="sxs-lookup"><span data-stu-id="7817a-162">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="7817a-163">Изменения не будут отправлены в базу данных до тех пор, пока ближе к концу данного руководства не будет вызван <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="7817a-163">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="7817a-164">Добавление нового объекта сущностей Customer</span><span class="sxs-lookup"><span data-stu-id="7817a-164">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="7817a-165">Создайте новый `Customer`, добавив перед `Console.ReadLine` в `Sub Main` следующий код.</span><span class="sxs-lookup"><span data-stu-id="7817a-165">Create a new `Customer` by adding the following code before `Console.ReadLine` in `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2. <span data-ttu-id="7817a-166">Нажмите клавишу F5 для отладки решения.</span><span class="sxs-lookup"><span data-stu-id="7817a-166">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="7817a-167">В окне консоли отображаются следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="7817a-167">The results that are shown in the console window are as follows:</span></span>  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     <span data-ttu-id="7817a-168">Обратите внимание, что в выходных данных новая строка не отображается.</span><span class="sxs-lookup"><span data-stu-id="7817a-168">Note that the new row does not appear in the results.</span></span> <span data-ttu-id="7817a-169">Новые данные еще не были переданы в базу данных.</span><span class="sxs-lookup"><span data-stu-id="7817a-169">The new data has not yet been submitted to the database.</span></span>  
  
3. <span data-ttu-id="7817a-170">Нажмите клавишу ВВОД в окне **консоли** , чтобы отключить отладку.</span><span class="sxs-lookup"><span data-stu-id="7817a-170">Press Enter in the **Console** window to stop debugging.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="7817a-171">Обновление сущности</span><span class="sxs-lookup"><span data-stu-id="7817a-171">Updating an Entity</span></span>  
 <span data-ttu-id="7817a-172">При выполнении следующих действий будет извлечен объект `Customer` и изменено одно из его свойств.</span><span class="sxs-lookup"><span data-stu-id="7817a-172">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="7817a-173">Изменение имени клиента</span><span class="sxs-lookup"><span data-stu-id="7817a-173">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="7817a-174">Добавьте следующий код перед `Console.ReadLine()`:</span><span class="sxs-lookup"><span data-stu-id="7817a-174">Add the following code above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="7817a-175">Удаление сущности</span><span class="sxs-lookup"><span data-stu-id="7817a-175">Deleting an Entity</span></span>  
 <span data-ttu-id="7817a-176">Используя тот же самый объект клиента, можно удалить первый заказ.</span><span class="sxs-lookup"><span data-stu-id="7817a-176">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="7817a-177">В следующем коде показано, как разорвать связь между строками и удалить строку из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7817a-177">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="7817a-178">Удаление строки</span><span class="sxs-lookup"><span data-stu-id="7817a-178">To delete a row</span></span>  
  
- <span data-ttu-id="7817a-179">Добавьте следующий код перед `Console.ReadLine()`.</span><span class="sxs-lookup"><span data-stu-id="7817a-179">Add the following code just above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="7817a-180">Отправка изменений в базу данных</span><span class="sxs-lookup"><span data-stu-id="7817a-180">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="7817a-181">Последнее действие, необходимое для создания, обновления и удаления объектов, заключается в фактической отправке изменений в базу данных.</span><span class="sxs-lookup"><span data-stu-id="7817a-181">The final step required for creating, updating, and deleting objects is to actually submit the changes to the database.</span></span> <span data-ttu-id="7817a-182">Без него изменения останутся на локальном уровне и не появятся в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="7817a-182">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="7817a-183">Отправка изменений в базу данных</span><span class="sxs-lookup"><span data-stu-id="7817a-183">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="7817a-184">Вставьте следующий код перед `Console.ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="7817a-184">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2. <span data-ttu-id="7817a-185">Вставьте следующий код (после `SubmitChanges`), чтобы показать результаты до и после отправки изменений.</span><span class="sxs-lookup"><span data-stu-id="7817a-185">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3. <span data-ttu-id="7817a-186">Нажмите клавишу F5 для отладки решения.</span><span class="sxs-lookup"><span data-stu-id="7817a-186">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="7817a-187">Появится окно консоли со следующими данными.</span><span class="sxs-lookup"><span data-stu-id="7817a-187">The console window appears as follows:</span></span>  
  
    ```  
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4. <span data-ttu-id="7817a-188">Нажмите клавишу ВВОД в окне **консоли** , чтобы отключить отладку.</span><span class="sxs-lookup"><span data-stu-id="7817a-188">Press Enter in the **Console** window to stop debugging.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7817a-189">После добавления нового клиента путем отправки изменений это решение нельзя повторно выполнить в исходном виде, поскольку этот же клиент не может быть добавлен без изменений.</span><span class="sxs-lookup"><span data-stu-id="7817a-189">After you have added the new customer by submitting the changes, you cannot execute this solution again as is, because you cannot add the same customer again as is.</span></span> <span data-ttu-id="7817a-190">Для повторного выполнения решения измените значение идентификатора добавляемого клиента.</span><span class="sxs-lookup"><span data-stu-id="7817a-190">To execute the solution again, change the value of the customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7817a-191">См. также</span><span class="sxs-lookup"><span data-stu-id="7817a-191">See also</span></span>

- [<span data-ttu-id="7817a-192">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="7817a-192">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
