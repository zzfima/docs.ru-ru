---
title: Практическое руководство. Фильтрование результатов запроса с помощью LINQ (Visual Basic)
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
ms.openlocfilehash: f9854650b1f89a2330cfa81910187e3fb01c54b4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424442"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="d52ed-102">Практическое руководство. Фильтрование результатов запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d52ed-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="d52ed-103">Language-Integrated Query (LINQ) позволяет легко получить доступ к информации базы данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="d52ed-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="d52ed-104">Приведенный ниже показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и фильтрует результаты по определенному значению, используя `Where` предложение.</span><span class="sxs-lookup"><span data-stu-id="d52ed-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="d52ed-105">Дополнительные сведения см. в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d52ed-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="d52ed-106">В примерах в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="d52ed-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="d52ed-107">Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d52ed-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="d52ed-108">Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d52ed-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="d52ed-109">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="d52ed-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="d52ed-110">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="d52ed-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="d52ed-111">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="d52ed-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="d52ed-112">Укажите допустимое соединение с образцом базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="d52ed-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="d52ed-113">Чтобы добавить в проект, содержащий файл классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d52ed-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="d52ed-114">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="d52ed-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="d52ed-115">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="d52ed-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="d52ed-116">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="d52ed-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="d52ed-117">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="d52ed-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="d52ed-118">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="d52ed-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="d52ed-119">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d52ed-119">Click **Add**.</span></span> <span data-ttu-id="d52ed-120">Для файла northwind.dbml откроется реляционный конструктор объектов (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="d52ed-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="d52ed-121">Добавление таблицы к запросу в конструкторе O/R</span><span class="sxs-lookup"><span data-stu-id="d52ed-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="d52ed-122">В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="d52ed-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="d52ed-123">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="d52ed-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="d52ed-124">Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="d52ed-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="d52ed-125">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="d52ed-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="d52ed-126">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="d52ed-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="d52ed-127">Конструктор создает новый `Customer` и `Order` объектов для проекта.</span><span class="sxs-lookup"><span data-stu-id="d52ed-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="d52ed-128">Обратите внимание на то, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="d52ed-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="d52ed-129">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойство для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="d52ed-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="d52ed-130">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="d52ed-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="d52ed-131">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="d52ed-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="d52ed-132">Добавление кода для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="d52ed-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="d52ed-133">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="d52ed-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="d52ed-134">Дважды щелкните файл Form1, чтобы добавить код для `Load` событий формы.</span><span class="sxs-lookup"><span data-stu-id="d52ed-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="d52ed-135">При добавлении таблиц в конструктор O/R designer добавлены <xref:System.Data.Linq.DataContext> объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="d52ed-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="d52ed-136">Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="d52ed-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="d52ed-137"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="d52ed-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="d52ed-138">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="d52ed-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="d52ed-139">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запрос таблицы, указанные в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="d52ed-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="d52ed-140">Добавьте следующий код, чтобы `Load` событий для запроса к таблицам, которые представляются как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="d52ed-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="d52ed-141">Запрос фильтрует результаты и возвращает только те клиенты, которые находятся в папке `London`.</span><span class="sxs-lookup"><span data-stu-id="d52ed-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="d52ed-142">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="d52ed-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="d52ed-143">Ниже приведены другие фильтры, которые вы можете попробовать.</span><span class="sxs-lookup"><span data-stu-id="d52ed-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d52ed-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d52ed-144">See Also</span></span>  
 [<span data-ttu-id="d52ed-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="d52ed-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="d52ed-146">Запросы</span><span class="sxs-lookup"><span data-stu-id="d52ed-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="d52ed-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d52ed-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="d52ed-148">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="d52ed-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
