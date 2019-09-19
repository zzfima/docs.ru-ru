---
title: Практическое руководство. Фильтрация результатов запроса с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: 1250f2fe0ccd7661b9bc1986000143ec4a15a9f0
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053287"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="6fc0e-102">Практическое руководство. Фильтрация результатов запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fc0e-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="6fc0e-103">LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="6fc0e-104">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и фильтрует результаты по определенному значению с помощью `Where` предложения.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="6fc0e-105">Дополнительные сведения см. в разделе [предложение WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6fc0e-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="6fc0e-106">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="6fc0e-107">Если эта база данных отсутствует на компьютере разработчика, ее можно скачать в центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="6fc0e-108">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="6fc0e-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="6fc0e-109">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="6fc0e-109">To create a connection to a database</span></span>

1. <span data-ttu-id="6fc0e-110">В Visual Studio откройте **Обозреватель сервера**/**Обозреватель базы данных** , выбрав в меню **вид** пункт **Обозреватель сервера**/**Обозреватель базы данных** .</span><span class="sxs-lookup"><span data-stu-id="6fc0e-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="6fc0e-111">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем выберите команду **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="6fc0e-112">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-112">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="6fc0e-113">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6fc0e-113">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="6fc0e-114">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="6fc0e-115">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="6fc0e-116">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6fc0e-117">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="6fc0e-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="6fc0e-118">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="6fc0e-119">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-119">Click **Add**.</span></span> <span data-ttu-id="6fc0e-120">Для файла Northwind. dbml откроется реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="6fc0e-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="6fc0e-121">Добавление таблиц в запрос в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="6fc0e-121">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="6fc0e-122">В **Обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="6fc0e-123">Разверните папку **таблицы** .</span><span class="sxs-lookup"><span data-stu-id="6fc0e-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="6fc0e-124">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="6fc0e-125">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="6fc0e-126">Щелкните таблицу Orders и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-126">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="6fc0e-127">Конструктор создает для проекта `Customer` новые `Order` объекты и.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="6fc0e-128">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="6fc0e-129">Например, IntelliSense покажет, что `Customer` объект `Orders` имеет свойство для всех заказов, связанных с этим клиентом.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="6fc0e-130">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-130">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="6fc0e-131">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-131">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="6fc0e-132">Добавление кода для запроса к базе данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="6fc0e-132">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="6fc0e-133">Перетащите<xref:System.Windows.Forms.DataGridView> элемент управления из **области элементов**в форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="6fc0e-134">Дважды щелкните Form1, чтобы добавить код в `Load` событие в форме.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="6fc0e-135">При добавлении таблиц в реляционный конструктор <xref:System.Data.Linq.DataContext> объектов конструктор добавил объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="6fc0e-136">Этот объект содержит код, который необходим для доступа к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="6fc0e-137">Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="6fc0e-138">Для этого проекта <xref:System.Data.Linq.DataContext> объект `northwindDataContext`называется.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="6fc0e-139"><xref:System.Data.Linq.DataContext> В коде можно создать экземпляр класса и запросить таблицы, заданные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="6fc0e-140">Добавьте следующий код в `Load` событие для запроса таблиц, предоставляемых в качестве свойств контекста данных.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="6fc0e-141">Запрос фильтрует результаты и возвращает только клиентов, расположенных в `London`.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-141">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="6fc0e-142">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-142">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="6fc0e-143">Ниже приведены некоторые другие фильтры, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="6fc0e-143">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="6fc0e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="6fc0e-144">See also</span></span>

- [<span data-ttu-id="6fc0e-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="6fc0e-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="6fc0e-146">Запросы</span><span class="sxs-lookup"><span data-stu-id="6fc0e-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="6fc0e-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6fc0e-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="6fc0e-148">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="6fc0e-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
