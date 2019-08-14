---
title: Пошаговое руководство. Применение только хранимых процедур (C#)
ms.date: 03/30/2017
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
ms.openlocfilehash: 69419dd5bb49c2e47315d0079df3a7b575ad9afd
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971778"
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="de22e-102">Пошаговое руководство. Применение только хранимых процедур (C#)</span><span class="sxs-lookup"><span data-stu-id="de22e-102">Walkthrough: Using Only Stored Procedures (C#)</span></span>

<span data-ttu-id="de22e-103">В данном пошаговом руководстве представлен основной полный сценарий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для получения доступа к данным, выполняя только хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="de22e-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="de22e-104">Этот метод часто используется администраторами баз данных для ограничения способов получения доступа к хранилищам данных.</span><span class="sxs-lookup"><span data-stu-id="de22e-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>

> [!NOTE]
> <span data-ttu-id="de22e-105">Хранимые процедуры можно также использовать в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для переопределения поведения по умолчанию, особенно для процессов `Create`, `Update` и `Delete`.</span><span class="sxs-lookup"><span data-stu-id="de22e-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="de22e-106">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="de22e-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>

<span data-ttu-id="de22e-107">Для целей данного пошагового руководства будут использованы два метода, которые были сопоставлены с хранимыми процедурами в образце базы данных Northwind: CustOrdersDetail и CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="de22e-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="de22e-108">Сопоставление осуществляется при запуске программы командной строки SQLMetal для создания файла C#.</span><span class="sxs-lookup"><span data-stu-id="de22e-108">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="de22e-109">Дополнительные сведения см. в разделе "Предварительные требования" далее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="de22e-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>

<span data-ttu-id="de22e-110">Это пошаговое руководство не полагается на реляционный конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="de22e-110">This walkthrough does not rely on the Object Relational Designer.</span></span> <span data-ttu-id="de22e-111">Разработчики, использующие Visual Studio, также могут использовать конструктор O/R для реализации функциональных возможностей хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="de22e-111">Developers using Visual Studio can also use the O/R Designer to implement stored procedure functionality.</span></span> <span data-ttu-id="de22e-112">См. раздел [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="de22e-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="de22e-113">Это пошаговое руководство было написано с использованием параметров разработки Visual C#.</span><span class="sxs-lookup"><span data-stu-id="de22e-113">This walkthrough was written by using Visual C# Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de22e-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="de22e-114">Prerequisites</span></span>

<span data-ttu-id="de22e-115">Необходимо выполнить следующие требования.</span><span class="sxs-lookup"><span data-stu-id="de22e-115">This walkthrough requires the following:</span></span>

- <span data-ttu-id="de22e-116">Для хранения файлов используется выделенная папка ("c:\linqtest7").</span><span class="sxs-lookup"><span data-stu-id="de22e-116">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="de22e-117">Прежде чем приступить к выполнению задач, создайте такую папку.</span><span class="sxs-lookup"><span data-stu-id="de22e-117">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="de22e-118">Наличие учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="de22e-118">The Northwind sample database.</span></span>

     <span data-ttu-id="de22e-119">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="de22e-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="de22e-120">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="de22e-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="de22e-121">После загрузки базы данных скопируйте файл northwnd.mdf в папку c:\linqtest7.</span><span class="sxs-lookup"><span data-stu-id="de22e-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>

- <span data-ttu-id="de22e-122">Наличие файла кода C#, созданного из базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="de22e-122">A C# code file generated from the Northwind database.</span></span>

     <span data-ttu-id="de22e-123">Данное пошаговое руководство было написано с использованием средства SqlMetal со следующей командной строкой:</span><span class="sxs-lookup"><span data-stu-id="de22e-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>

     <span data-ttu-id="de22e-124">**SQLMetal/Code: "c:\linqtest7\northwind.cs"/Language: CSharp "c:\linqtest7\northwnd.mdf"/спрокс/функтионс/плурализе**</span><span class="sxs-lookup"><span data-stu-id="de22e-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>

     <span data-ttu-id="de22e-125">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="de22e-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>

## <a name="overview"></a><span data-ttu-id="de22e-126">Обзор</span><span class="sxs-lookup"><span data-stu-id="de22e-126">Overview</span></span>

<span data-ttu-id="de22e-127">Данное пошаговое руководство состоит из шести основных задач.</span><span class="sxs-lookup"><span data-stu-id="de22e-127">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="de22e-128">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Настройка решения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="de22e-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="de22e-129">Добавление сборки System.Data.Linq в проект.</span><span class="sxs-lookup"><span data-stu-id="de22e-129">Adding the System.Data.Linq assembly to the project.</span></span>

- <span data-ttu-id="de22e-130">Добавление файла кода базы данных в проект.</span><span class="sxs-lookup"><span data-stu-id="de22e-130">Adding the database code file to the project.</span></span>

- <span data-ttu-id="de22e-131">Создание подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="de22e-131">Creating a connection with the database.</span></span>

- <span data-ttu-id="de22e-132">Настройка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="de22e-132">Setting up the user interface.</span></span>

- <span data-ttu-id="de22e-133">Запуск и тестирование приложения.</span><span class="sxs-lookup"><span data-stu-id="de22e-133">Running and testing the application.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="de22e-134">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="de22e-134">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="de22e-135">В этой первой задаче вы создадите решение Visual Studio, содержащее необходимые ссылки для сборки и запуска [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="de22e-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="de22e-136">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="de22e-136">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="de22e-137">В меню **файл** Visual Studio наведите указатель на пункт **создать**и выберите пункт **проект**.</span><span class="sxs-lookup"><span data-stu-id="de22e-137">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="de22e-138">В области **типы проектов** диалогового окна **Новый проект** нажмите кнопку визуальный **C#** элемент.</span><span class="sxs-lookup"><span data-stu-id="de22e-138">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>

3. <span data-ttu-id="de22e-139">Выберите **Приложение Windows Forms** в области **Шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="de22e-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>

4. <span data-ttu-id="de22e-140">В поле **имя** введите **спроконляпп**.</span><span class="sxs-lookup"><span data-stu-id="de22e-140">In the **Name** box, type **SprocOnlyApp**.</span></span>

5. <span data-ttu-id="de22e-141">В поле **Расположение** проверьте, где вы хотите сохранить файлы проекта.</span><span class="sxs-lookup"><span data-stu-id="de22e-141">In the **Location** box, verify where you want to store your project files.</span></span>

6. <span data-ttu-id="de22e-142">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de22e-142">Click **OK**.</span></span>

     <span data-ttu-id="de22e-143">Откроется конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="de22e-143">The Windows Forms Designer opens.</span></span>

## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="de22e-144">Добавление ссылки на сборку LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="de22e-144">Adding the LINQ to SQL Assembly Reference</span></span>

<span data-ttu-id="de22e-145">Сборка [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не включается в стандартный шаблон приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="de22e-145">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="de22e-146">Сборку необходимо добавить самостоятельно, выполнив приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="de22e-146">You will have to add the assembly yourself, as explained in the following steps:</span></span>

### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="de22e-147">Добавление сборки System.Data.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="de22e-147">To add System.Data.Linq.dll</span></span>

1. <span data-ttu-id="de22e-148">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **ссылки**и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="de22e-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="de22e-149">В диалоговом окне **Добавление ссылки** щелкните **.NET**, выберите сборку System. Data. LINQ и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de22e-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="de22e-150">Сборка будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="de22e-150">The assembly is added to the project.</span></span>

## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="de22e-151">Добавление файла кода Northwind в проект</span><span class="sxs-lookup"><span data-stu-id="de22e-151">Adding the Northwind Code File to the Project</span></span>

<span data-ttu-id="de22e-152">При выполнении действий этого шага предполагается, что для создания файла кода из учебной базы данных Northwind использовалась программа SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="de22e-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="de22e-153">Дополнительные сведения см. в разделе "Предварительные требования" ранее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="de22e-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="de22e-154">Добавление файла кода northwind в проект</span><span class="sxs-lookup"><span data-stu-id="de22e-154">To add the northwind code file to the project</span></span>

1. <span data-ttu-id="de22e-155">В меню **проект** выберите команду **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="de22e-155">On the **Project** menu, click **Add Existing Item**.</span></span>

2. <span data-ttu-id="de22e-156">В диалоговом окне **Добавление существующего элемента** перейдите в c:\linqtest7\northwind.cs и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="de22e-156">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>

     <span data-ttu-id="de22e-157">Файл northwind.cs будет добавлен в проект.</span><span class="sxs-lookup"><span data-stu-id="de22e-157">The northwind.cs file is added to the project.</span></span>

## <a name="creating-a-database-connection"></a><span data-ttu-id="de22e-158">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="de22e-158">Creating a Database Connection</span></span>

<span data-ttu-id="de22e-159">На этом этапе определяется подключение к учебной базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="de22e-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="de22e-160">В качестве пути используется "c:\linqtest7\northwnd.mdf".</span><span class="sxs-lookup"><span data-stu-id="de22e-160">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>

### <a name="to-create-the-database-connection"></a><span data-ttu-id="de22e-161">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="de22e-161">To create the database connection</span></span>

1. <span data-ttu-id="de22e-162">В **Обозреватель решений**щелкните правой кнопкой мыши **Form1.CS**и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="de22e-162">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>

2. <span data-ttu-id="de22e-163">Введите следующий код в класс `Form1`:</span><span class="sxs-lookup"><span data-stu-id="de22e-163">Type the following code into the `Form1` class:</span></span>

     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]

## <a name="setting-up-the-user-interface"></a><span data-ttu-id="de22e-164">Настройка пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="de22e-164">Setting up the User Interface</span></span>

<span data-ttu-id="de22e-165">В этой задаче настраивается интерфейс, с помощью которого пользователи могут выполнять хранимые процедуры для получения доступа к данным в базе данных.</span><span class="sxs-lookup"><span data-stu-id="de22e-165">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="de22e-166">В приложении, разрабатываемом с помощью настоящего пошагового руководства, пользователи могут получать доступ к данным в базе данных только с помощью хранимых процедур, внедренных в приложение.</span><span class="sxs-lookup"><span data-stu-id="de22e-166">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>

### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="de22e-167">Настройка пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="de22e-167">To set up the user interface</span></span>

1. <span data-ttu-id="de22e-168">Вернитесь к конструктор Windows Forms (**Form1. cs [Design]** ).</span><span class="sxs-lookup"><span data-stu-id="de22e-168">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>

2. <span data-ttu-id="de22e-169">В меню **Вид** выберите пункт **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="de22e-169">On the **View** menu, click **Toolbox**.</span></span>

     <span data-ttu-id="de22e-170">Откроется панель элементов.</span><span class="sxs-lookup"><span data-stu-id="de22e-170">The toolbox opens.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de22e-171">Щелкните кнопку **Автоскрытие** , чтобы открыть панель элементов во время выполнения оставшихся действий в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="de22e-171">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>

3. <span data-ttu-id="de22e-172">Перетащите две кнопки, два текстовых поля и две метки с панели элементов на **форму Form1**.</span><span class="sxs-lookup"><span data-stu-id="de22e-172">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>

     <span data-ttu-id="de22e-173">Расположите элементы управления в соответствии с показанным здесь рисунком.</span><span class="sxs-lookup"><span data-stu-id="de22e-173">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="de22e-174">Разверните **форму Form1** , чтобы элементы управления были легко размещены.</span><span class="sxs-lookup"><span data-stu-id="de22e-174">Expand **Form1** so that the controls fit easily.</span></span>

4. <span data-ttu-id="de22e-175">Щелкните правой кнопкой мыши элемент **Label1**и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="de22e-175">Right-click **label1**, and then click **Properties**.</span></span>

5. <span data-ttu-id="de22e-176">Измените свойство **Text** с помощью **Label1** , чтобы **ввести OrderID:** .</span><span class="sxs-lookup"><span data-stu-id="de22e-176">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>

6. <span data-ttu-id="de22e-177">Таким же образом для **ярлык2**измените свойство **Text** с **ярлык2** на **Ввод CustomerID:** .</span><span class="sxs-lookup"><span data-stu-id="de22e-177">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>

7. <span data-ttu-id="de22e-178">Аналогичным образом измените свойство **Text** для **Button1** на **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="de22e-178">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>

8. <span data-ttu-id="de22e-179">Измените свойство **Text** для свойства **Button2** на " **журнал заказов**".</span><span class="sxs-lookup"><span data-stu-id="de22e-179">Change the **Text** property for **button2** to **Order History**.</span></span>

     <span data-ttu-id="de22e-180">Расширьте элементы управления "Кнопка", чтобы отображался весь текст.</span><span class="sxs-lookup"><span data-stu-id="de22e-180">Widen the button controls so that all the text is visible.</span></span>

### <a name="to-handle-button-clicks"></a><span data-ttu-id="de22e-181">Обработка нажатий кнопки</span><span class="sxs-lookup"><span data-stu-id="de22e-181">To handle button clicks</span></span>

1. <span data-ttu-id="de22e-182">Дважды щелкните элемент **сведения о заказе** в **Form1** , чтобы открыть обработчик событий button1 в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="de22e-182">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>

2. <span data-ttu-id="de22e-183">Введите в обработчик кнопки `button1` следующий код:</span><span class="sxs-lookup"><span data-stu-id="de22e-183">Type the following code into the `button1` handler:</span></span>

     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]

3. <span data-ttu-id="de22e-184">Теперь дважды щелкните элемент " **Button2** " на **Form1** `button2` , чтобы открыть обработчик.</span><span class="sxs-lookup"><span data-stu-id="de22e-184">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>

4. <span data-ttu-id="de22e-185">Введите в обработчик кнопки `button2` следующий код:</span><span class="sxs-lookup"><span data-stu-id="de22e-185">Type the following code into the `button2` handler:</span></span>

     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]

## <a name="testing-the-application"></a><span data-ttu-id="de22e-186">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="de22e-186">Testing the Application</span></span>

<span data-ttu-id="de22e-187">Теперь необходимо протестировать приложение.</span><span class="sxs-lookup"><span data-stu-id="de22e-187">Now it is time to test your application.</span></span> <span data-ttu-id="de22e-188">Обратите внимание, что все обращения к хранилищу данных ограничены теми действиями, которые могут выполняться двумя хранимыми процедурами.</span><span class="sxs-lookup"><span data-stu-id="de22e-188">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="de22e-189">Эти действия заключаются в возвращении продуктов, включенных в заказ с введенным кодом, или истории продуктов, заказанных клиентом с введенным кодом.</span><span class="sxs-lookup"><span data-stu-id="de22e-189">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>

### <a name="to-test-the-application"></a><span data-ttu-id="de22e-190">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="de22e-190">To test the application</span></span>

1. <span data-ttu-id="de22e-191">Нажмите клавишу F5, чтобы начать отладку.</span><span class="sxs-lookup"><span data-stu-id="de22e-191">Press F5 to start debugging.</span></span>

     <span data-ttu-id="de22e-192">Откроется форма "Form1".</span><span class="sxs-lookup"><span data-stu-id="de22e-192">Form1 appears.</span></span>

2. <span data-ttu-id="de22e-193">В поле **Enter OrderID (введите** код `10249`заказа) введите, а затем щелкните **Order Details (подробности заказа**).</span><span class="sxs-lookup"><span data-stu-id="de22e-193">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>

     <span data-ttu-id="de22e-194">В окне сообщения будет отображен список продуктов, включенных в заказ 10249.</span><span class="sxs-lookup"><span data-stu-id="de22e-194">A message box lists the products included in order 10249.</span></span>

     <span data-ttu-id="de22e-195">Нажмите кнопку **ОК** , чтобы закрыть окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="de22e-195">Click **OK** to close the message box.</span></span>

3. <span data-ttu-id="de22e-196">В поле **введите CustomerID** введите `ALFKI`, а затем щелкните **Журнал заказа**.</span><span class="sxs-lookup"><span data-stu-id="de22e-196">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>

     <span data-ttu-id="de22e-197">Откроется окно сообщения, в котором отображается история заказа для клиента ALFKI.</span><span class="sxs-lookup"><span data-stu-id="de22e-197">A message box appears that lists the order history for customer ALFKI.</span></span>

     <span data-ttu-id="de22e-198">Нажмите кнопку **ОК** , чтобы закрыть окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="de22e-198">Click **OK** to close the message box.</span></span>

4. <span data-ttu-id="de22e-199">В поле **Enter OrderID (введите** код `123`заказа) введите, а затем щелкните **Order Details (подробности заказа**).</span><span class="sxs-lookup"><span data-stu-id="de22e-199">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>

     <span data-ttu-id="de22e-200">Откроется окно сообщения, в котором отображается текст "Нет результатов".</span><span class="sxs-lookup"><span data-stu-id="de22e-200">A message box appears that displays "No results."</span></span>

     <span data-ttu-id="de22e-201">Нажмите кнопку **ОК** , чтобы закрыть окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="de22e-201">Click **OK** to close the message box.</span></span>

5. <span data-ttu-id="de22e-202">В меню **Отладка** выберите команду **прерывать отладку**.</span><span class="sxs-lookup"><span data-stu-id="de22e-202">On the **Debug** menu, click **Stop debugging**.</span></span>

     <span data-ttu-id="de22e-203">Сеанс отладки закрывается.</span><span class="sxs-lookup"><span data-stu-id="de22e-203">The debug session closes.</span></span>

6. <span data-ttu-id="de22e-204">Если вы завершили эксперименты, можно нажать кнопку **Закрыть проект** в меню **файл** и сохранить проект при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="de22e-204">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de22e-205">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="de22e-205">Next Steps</span></span>

<span data-ttu-id="de22e-206">Этот проект можно улучшить, выполнив некоторые изменения.</span><span class="sxs-lookup"><span data-stu-id="de22e-206">You can enhance this project by making some changes.</span></span> <span data-ttu-id="de22e-207">Например, можно создать поле со списком доступных хранимых процедур и разрешить пользователю выбирать процедуру для выполнения.</span><span class="sxs-lookup"><span data-stu-id="de22e-207">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="de22e-208">Можно также записывать выходные данных отчетов в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="de22e-208">You could also stream the output of the reports to a text file.</span></span>

## <a name="see-also"></a><span data-ttu-id="de22e-209">См. также</span><span class="sxs-lookup"><span data-stu-id="de22e-209">See also</span></span>

- [<span data-ttu-id="de22e-210">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="de22e-210">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="de22e-211">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="de22e-211">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
