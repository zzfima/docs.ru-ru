---
title: Практическое руководство. Сортировка результатов запроса с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: 40baa1d7ae463b4193e4af5a9b79d29116b179b4
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "34826910"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="4d738-102">Практическое руководство. Сортировка результатов запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d738-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="4d738-103">Встроенные в язык запросы (LINQ) упрощает доступ к данным базы данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="4d738-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="4d738-104">В следующем примере показано создание нового приложения, которое выполняет запросы к базе данных SQL Server и сортирует результаты по нескольким полям с помощью `Order By` предложения.</span><span class="sxs-lookup"><span data-stu-id="4d738-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="4d738-105">Порядок сортировки для каждого поля можно по возрастанию или убыванию.</span><span class="sxs-lookup"><span data-stu-id="4d738-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="4d738-106">Дополнительные сведения см. в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4d738-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="4d738-107">Примеры в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="4d738-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="4d738-108">Если база данных не установлена на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4d738-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="4d738-109">Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4d738-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="4d738-110">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="4d738-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="4d738-111">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="4d738-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="4d738-112">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="4d738-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="4d738-113">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="4d738-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="4d738-114">Чтобы добавить в проект, содержащий файл классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4d738-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="4d738-115">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="4d738-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="4d738-116">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="4d738-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="4d738-117">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="4d738-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="4d738-118">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="4d738-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="4d738-119">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="4d738-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="4d738-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4d738-120">Click **Add**.</span></span> <span data-ttu-id="4d738-121">Реляционный конструктор объектов (O/R-конструктор) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="4d738-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="4d738-122">Добавление таблицы к запросу в конструкторе O/R</span><span class="sxs-lookup"><span data-stu-id="4d738-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="4d738-123">В **обозревателя серверов**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="4d738-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="4d738-124">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="4d738-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="4d738-125">Если O/R-конструктор закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="4d738-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="4d738-126">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="4d738-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="4d738-127">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="4d738-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="4d738-128">Конструктор создает новый `Customer` и `Order` объектов для проекта.</span><span class="sxs-lookup"><span data-stu-id="4d738-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="4d738-129">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="4d738-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="4d738-130">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="4d738-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="4d738-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="4d738-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="4d738-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="4d738-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="4d738-133">Добавление кода для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="4d738-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="4d738-134">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> на форме Windows Forms по умолчанию для проекта, Form1 элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4d738-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="4d738-135">Дважды щелкните файл Form1, чтобы добавить код для `Load` событие в формате.</span><span class="sxs-lookup"><span data-stu-id="4d738-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="4d738-136">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объекта к проекту.</span><span class="sxs-lookup"><span data-stu-id="4d738-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="4d738-137">Этот объект содержит код, который должен иметь доступа к этим таблицам и получить доступ к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4d738-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="4d738-138"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="4d738-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="4d738-139">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="4d738-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="4d738-140">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, указанные в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="4d738-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="4d738-141">Добавьте следующий код в `Load` событий для запроса к таблицам, которые представляются как свойства контекста данных и отсортировать результаты.</span><span class="sxs-lookup"><span data-stu-id="4d738-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="4d738-142">Запрос сортирует результаты по числу заказов клиентов в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="4d738-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="4d738-143">Клиенты, имеющие одинаковое количество заказов упорядочиваются по названию компании в возрастающем порядке (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4d738-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="4d738-144">Нажмите клавишу F5 для запуска проекта и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="4d738-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d738-145">См. также</span><span class="sxs-lookup"><span data-stu-id="4d738-145">See Also</span></span>  
 [<span data-ttu-id="4d738-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="4d738-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="4d738-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="4d738-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="4d738-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4d738-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="4d738-149">Методы DataContext (O/R-конструктор)</span><span class="sxs-lookup"><span data-stu-id="4d738-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
