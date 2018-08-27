---
title: Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: 252601b12e21e122c316952f8e10ce04cbe3f78e
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924486"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="84418-102">Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84418-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="84418-103">Language-Integrated Query (LINQ) позволяет легко получить доступ к информации базы данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="84418-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="84418-104">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="84418-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="84418-105">В примере определяются минимальное и максимальное значения для результатов с помощью `Aggregate` и `Group By` предложения.</span><span class="sxs-lookup"><span data-stu-id="84418-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="84418-106">Дополнительные сведения см. в разделе [предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="84418-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="84418-107">В примерах в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="84418-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="84418-108">Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="84418-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="84418-109">Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="84418-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="84418-110">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="84418-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="84418-111">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="84418-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="84418-112">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="84418-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="84418-113">Укажите допустимое соединение с образцом базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="84418-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="84418-114">Чтобы добавить в проект, содержащий файл классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="84418-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="84418-115">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="84418-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="84418-116">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="84418-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="84418-117">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="84418-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="84418-118">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="84418-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="84418-119">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="84418-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="84418-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="84418-120">Click **Add**.</span></span> <span data-ttu-id="84418-121">Для файла northwind.dbml открывается реляционный конструктор объектов (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="84418-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="84418-122">Добавление таблицы к запросу в конструкторе O/R</span><span class="sxs-lookup"><span data-stu-id="84418-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="84418-123">В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="84418-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="84418-124">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="84418-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="84418-125">Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="84418-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="84418-126">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="84418-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="84418-127">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="84418-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="84418-128">Конструктор создает новый `Customer` и `Order` объектов для проекта.</span><span class="sxs-lookup"><span data-stu-id="84418-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="84418-129">Обратите внимание на то, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="84418-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="84418-130">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойство для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="84418-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="84418-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="84418-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="84418-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="84418-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="84418-133">Добавление кода для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="84418-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="84418-134">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="84418-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="84418-135">Дважды щелкните файл Form1, чтобы добавить код для `Load` событий формы.</span><span class="sxs-lookup"><span data-stu-id="84418-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="84418-136">При добавлении таблиц в конструктор O/R designer добавлены <xref:System.Data.Linq.DataContext> объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="84418-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="84418-137">Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="84418-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="84418-138"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="84418-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="84418-139">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="84418-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="84418-140">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запрос таблицы, указанные в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="84418-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="84418-141">Добавьте следующий код, чтобы `Load` событий.</span><span class="sxs-lookup"><span data-stu-id="84418-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="84418-142">Этот код запрашивает таблицы, которые представляются как свойства контекста данных и определяет минимальное и максимальное значения для результатов.</span><span class="sxs-lookup"><span data-stu-id="84418-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="84418-143">Пример использует `Aggregate` предложение, чтобы получить один результат и `Group By` предложение для отображения среднего значения для сгруппированных результатов.</span><span class="sxs-lookup"><span data-stu-id="84418-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]  
  
4.  <span data-ttu-id="84418-144">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="84418-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84418-145">См. также</span><span class="sxs-lookup"><span data-stu-id="84418-145">See Also</span></span>  
 [<span data-ttu-id="84418-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="84418-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="84418-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="84418-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="84418-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="84418-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="84418-149">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="84418-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
