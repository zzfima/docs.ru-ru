---
title: Инструкции. Фильтрация результатов запроса с помощью LINQ
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
ms.openlocfilehash: 2ea8a852a2f012ddb25ec1198c66e09df880ff47
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344991"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="51a85-102">Практическое руководство. Фильтрование результатов запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51a85-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="51a85-103">LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.</span><span class="sxs-lookup"><span data-stu-id="51a85-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="51a85-104">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и фильтрует результаты по определенному значению с помощью предложения `Where`.</span><span class="sxs-lookup"><span data-stu-id="51a85-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="51a85-105">Дополнительные сведения см. в разделе [предложение WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="51a85-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="51a85-106">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="51a85-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="51a85-107">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51a85-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="51a85-108">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="51a85-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="51a85-109">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="51a85-109">To create a connection to a database</span></span>

1. <span data-ttu-id="51a85-110">В Visual Studio откройте **обозреватель сервера**/**обозреватель базы данных** , выбрав **Обозреватель сервера**/**Обозреватель базы данных** в меню **вид** .</span><span class="sxs-lookup"><span data-stu-id="51a85-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="51a85-111">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем нажмите кнопку **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="51a85-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="51a85-112">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="51a85-112">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="51a85-113">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="51a85-113">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="51a85-114">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="51a85-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="51a85-115">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="51a85-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="51a85-116">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="51a85-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="51a85-117">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="51a85-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="51a85-118">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="51a85-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="51a85-119">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="51a85-119">Click **Add**.</span></span> <span data-ttu-id="51a85-120">Для файла Northwind. dbml откроется реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="51a85-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="51a85-121">Добавление таблиц в запрос в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="51a85-121">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="51a85-122">В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="51a85-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="51a85-123">Разверните папку **таблицы** .</span><span class="sxs-lookup"><span data-stu-id="51a85-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="51a85-124">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="51a85-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="51a85-125">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="51a85-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="51a85-126">Щелкните таблицу Orders и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="51a85-126">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="51a85-127">Конструктор создает в проекте новые `Customer` и `Order` объекты.</span><span class="sxs-lookup"><span data-stu-id="51a85-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="51a85-128">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="51a85-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="51a85-129">Например, IntelliSense покажет, что объект `Customer` имеет свойство `Orders` для всех заказов, связанных с этим клиентом.</span><span class="sxs-lookup"><span data-stu-id="51a85-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="51a85-130">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="51a85-130">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="51a85-131">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="51a85-131">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="51a85-132">Добавление кода для запроса к базе данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="51a85-132">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="51a85-133">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="51a85-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="51a85-134">Дважды щелкните Form1, чтобы добавить код в событие `Load` формы.</span><span class="sxs-lookup"><span data-stu-id="51a85-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="51a85-135">При добавлении таблиц в реляционный конструктор объектов конструктор добавил объект <xref:System.Data.Linq.DataContext> для проекта.</span><span class="sxs-lookup"><span data-stu-id="51a85-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="51a85-136">Этот объект содержит код, который необходим для доступа к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="51a85-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="51a85-137">Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="51a85-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="51a85-138">Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="51a85-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="51a85-139">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, заданные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="51a85-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="51a85-140">Добавьте следующий код в событие `Load`, чтобы запросить таблицы, предоставляемые как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="51a85-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="51a85-141">Запрос фильтрует результаты и возвращает только клиентов, расположенных в `London`.</span><span class="sxs-lookup"><span data-stu-id="51a85-141">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="51a85-142">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="51a85-142">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="51a85-143">Ниже приведены некоторые другие фильтры, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="51a85-143">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="51a85-144">См. также</span><span class="sxs-lookup"><span data-stu-id="51a85-144">See also</span></span>

- [<span data-ttu-id="51a85-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="51a85-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="51a85-146">Запросы</span><span class="sxs-lookup"><span data-stu-id="51a85-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="51a85-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="51a85-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="51a85-148">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="51a85-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
