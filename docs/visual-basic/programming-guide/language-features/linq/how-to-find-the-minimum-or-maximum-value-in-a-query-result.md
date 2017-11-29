---
title: "Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1af5b590310e966f7d27c02e2835a9e959f40c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="00feb-102">Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00feb-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="00feb-103">Встроенные в язык запросы (LINQ) упрощает доступ к данным базы данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="00feb-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="00feb-104">В следующем примере демонстрируется создание нового приложения, которое выполняет запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00feb-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="00feb-105">В примере определяются минимальное и максимальное значения для результатов с помощью `Aggregate` и `Group By` предложения.</span><span class="sxs-lookup"><span data-stu-id="00feb-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="00feb-106">Дополнительные сведения см. в разделе [предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="00feb-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="00feb-107">Примеры в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="00feb-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="00feb-108">Если у вас образца базы данных "Борей" на компьютере разработчика, его можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="00feb-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="00feb-109">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="00feb-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="00feb-110">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="00feb-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="00feb-111">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="00feb-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="00feb-112">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="00feb-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="00feb-113">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="00feb-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="00feb-114">Чтобы добавить в проект, содержащий файл классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="00feb-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="00feb-115">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="00feb-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="00feb-116">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="00feb-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="00feb-117">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="00feb-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="00feb-118">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="00feb-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="00feb-119">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="00feb-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="00feb-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="00feb-120">Click **Add**.</span></span> <span data-ttu-id="00feb-121">Реляционный конструктор объектов (O/R-конструктор) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="00feb-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="00feb-122">Добавление таблицы к запросу в конструкторе O/R</span><span class="sxs-lookup"><span data-stu-id="00feb-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="00feb-123">В **обозревателя серверов**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="00feb-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="00feb-124">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="00feb-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="00feb-125">Если O/R-конструктор закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="00feb-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="00feb-126">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="00feb-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="00feb-127">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="00feb-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="00feb-128">Конструктор создает новый `Customer` и `Order` объектов для проекта.</span><span class="sxs-lookup"><span data-stu-id="00feb-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="00feb-129">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="00feb-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="00feb-130">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="00feb-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="00feb-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="00feb-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="00feb-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="00feb-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="00feb-133">Добавление кода для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="00feb-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="00feb-134">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> на форме Windows Forms по умолчанию для проекта, Form1 элемент управления.</span><span class="sxs-lookup"><span data-stu-id="00feb-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="00feb-135">Дважды щелкните файл Form1, чтобы добавить код для `Load` событие в формате.</span><span class="sxs-lookup"><span data-stu-id="00feb-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="00feb-136">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объектов для проекта.</span><span class="sxs-lookup"><span data-stu-id="00feb-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="00feb-137">Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="00feb-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="00feb-138"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="00feb-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="00feb-139">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="00feb-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="00feb-140">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, указанные в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="00feb-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="00feb-141">Добавьте следующий код в `Load` событий.</span><span class="sxs-lookup"><span data-stu-id="00feb-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="00feb-142">Этот код запрашивает таблицы, которые представляются как свойства контекста данных и определяет минимальное и максимальное значения для результатов.</span><span class="sxs-lookup"><span data-stu-id="00feb-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="00feb-143">Пример использует `Aggregate` предложения запроса одного результата и `Group By` предложения для отображения среднего значения для сгруппированных результатов.</span><span class="sxs-lookup"><span data-stu-id="00feb-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]  
  
4.  <span data-ttu-id="00feb-144">Нажмите клавишу F5 для запуска проекта и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="00feb-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00feb-145">См. также</span><span class="sxs-lookup"><span data-stu-id="00feb-145">See Also</span></span>  
 [<span data-ttu-id="00feb-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="00feb-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="00feb-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="00feb-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="00feb-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="00feb-148">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="00feb-149">Методы DataContext (O/R-конструктор)</span><span class="sxs-lookup"><span data-stu-id="00feb-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
