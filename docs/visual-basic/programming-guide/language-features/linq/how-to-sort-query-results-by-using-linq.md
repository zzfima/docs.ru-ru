---
title: "Практическое руководство: сортировка результатов запроса с помощью LINQ (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 0c728d9e52add00c9d3241a9f598c15eb2db17a5
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="32357-102">Практическое руководство. Сортировка результатов запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32357-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="32357-103">Language Integrated Query (LINQ) упрощает для доступа к базе данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="32357-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="32357-104">В следующем примере показано создание нового приложения, которое выполняет запросы к базе данных SQL Server и упорядочивает результаты по нескольким полям с помощью `Order By` предложения.</span><span class="sxs-lookup"><span data-stu-id="32357-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="32357-105">Порядок сортировки для каждого поля можно по возрастанию или убыванию.</span><span class="sxs-lookup"><span data-stu-id="32357-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="32357-106">Дополнительные сведения см. в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="32357-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="32357-107">Примеры в этом разделе используется образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="32357-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="32357-108">Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="32357-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="32357-109">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="32357-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="32357-110">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="32357-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="32357-111">В Visual Studio откройте **обозреватель серверов**/**обозревателя базы данных** , щелкнув **обозревателя**/**обозреватель баз данных** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="32357-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="32357-112">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных** и нажмите кнопку **Добавление подключения**.</span><span class="sxs-lookup"><span data-stu-id="32357-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="32357-113">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="32357-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="32357-114">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="32357-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="32357-115">В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="32357-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="32357-116">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="32357-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="32357-117">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="32357-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="32357-118">Выберите **классы LINQ to SQL** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="32357-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="32357-119">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="32357-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="32357-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="32357-120">Click **Add**.</span></span> <span data-ttu-id="32357-121">Реляционный конструктор объектов (конструктор O/R) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="32357-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="32357-122">Добавление таблицы к запросу реляционный конструктор объектов</span><span class="sxs-lookup"><span data-stu-id="32357-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="32357-123">В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="32357-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="32357-124">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="32357-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="32357-125">Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="32357-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="32357-126">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="32357-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="32357-127">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="32357-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="32357-128">Конструктор создает новый `Customer` и `Order` объекты для проекта.</span><span class="sxs-lookup"><span data-stu-id="32357-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="32357-129">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="32357-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="32357-130">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="32357-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="32357-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="32357-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="32357-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="32357-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="32357-133">Чтобы добавить код для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="32357-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="32357-134">От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="32357-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="32357-135">Дважды щелкните Form1, чтобы добавить код для `Load` события формы.</span><span class="sxs-lookup"><span data-stu-id="32357-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="32357-136">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект в проект.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="32357-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="32357-137">Этот объект содержит код, необходимый для доступа к этим таблицам и доступа к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="32357-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="32357-138"><xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="32357-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="32357-139">Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="32357-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="32357-140">Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и запросить таблицы, указанные в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="32357-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="32357-141">Добавьте следующий код в `Load` событий для запроса к таблицам, которые отображаются как свойства контекста данных и отсортировать результаты.</span><span class="sxs-lookup"><span data-stu-id="32357-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="32357-142">Запрос сортирует результаты по числу заказов клиентов в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="32357-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="32357-143">Клиенты, имеющие одинаковое количество заказов, упорядочены по названию компании в возрастающем порядке (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="32357-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     <span data-ttu-id="32357-144">[!code-vb[VbLINQToSQLHowTos&#10;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="32357-144">[!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="32357-145">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="32357-145">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32357-146">См. также</span><span class="sxs-lookup"><span data-stu-id="32357-146">See Also</span></span>  
 <span data-ttu-id="32357-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="32357-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="32357-148"> [Запросы](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="32357-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="32357-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="32357-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="32357-150"> [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="32357-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

