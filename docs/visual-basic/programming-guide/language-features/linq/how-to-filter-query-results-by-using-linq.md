---
title: "Практическое руководство: фильтрацию результатов запроса с помощью LINQ (Visual Basic) | Документы Microsoft"
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
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: 6
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
ms.openlocfilehash: d6197e39ffef5b09b87b1b47cab04d4339bcaf3f
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="dca2d-102">Практическое руководство. Фильтрование результатов запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dca2d-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="dca2d-103">Language Integrated Query (LINQ) упрощает для доступа к базе данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="dca2d-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="dca2d-104">Следующий пример демонстрирует создание нового приложения, которое выполняет запросы к базе данных SQL Server и фильтрует результаты по определенному значению с помощью `Where` предложения.</span><span class="sxs-lookup"><span data-stu-id="dca2d-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="dca2d-105">Дополнительные сведения см. в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="dca2d-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="dca2d-106">Примеры в этом разделе используется образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="dca2d-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="dca2d-107">Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="dca2d-107">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="dca2d-108">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="dca2d-108">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="dca2d-109">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="dca2d-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="dca2d-110">В Visual Studio откройте **обозреватель серверов**/**обозревателя базы данных** , щелкнув **обозревателя**/**обозреватель баз данных** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="dca2d-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="dca2d-111">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных** и нажмите кнопку **Добавление подключения**.</span><span class="sxs-lookup"><span data-stu-id="dca2d-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="dca2d-112">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="dca2d-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="dca2d-113">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dca2d-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="dca2d-114">В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="dca2d-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="dca2d-115">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="dca2d-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="dca2d-116">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="dca2d-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="dca2d-117">Выберите **классы LINQ to SQL** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="dca2d-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="dca2d-118">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="dca2d-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="dca2d-119">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dca2d-119">Click **Add**.</span></span> <span data-ttu-id="dca2d-120">Откроется реляционный конструктор объектов (конструктор O/R) для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="dca2d-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="dca2d-121">Добавление таблицы к запросу реляционный конструктор объектов</span><span class="sxs-lookup"><span data-stu-id="dca2d-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="dca2d-122">В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="dca2d-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="dca2d-123">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="dca2d-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="dca2d-124">Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="dca2d-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="dca2d-125">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="dca2d-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="dca2d-126">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="dca2d-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="dca2d-127">Конструктор создает новый `Customer` и `Order` объекты для проекта.</span><span class="sxs-lookup"><span data-stu-id="dca2d-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="dca2d-128">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="dca2d-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="dca2d-129">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="dca2d-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="dca2d-130">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="dca2d-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="dca2d-131">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="dca2d-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="dca2d-132">Чтобы добавить код для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="dca2d-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="dca2d-133">От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="dca2d-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="dca2d-134">Дважды щелкните Form1, чтобы добавить код для `Load` события формы.</span><span class="sxs-lookup"><span data-stu-id="dca2d-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="dca2d-135">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект для проекта.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dca2d-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="dca2d-136">Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="dca2d-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="dca2d-137"><xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dca2d-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="dca2d-138">Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dca2d-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="dca2d-139">Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и запросить таблицы, указанные в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dca2d-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="dca2d-140">Добавьте следующий код в `Load` событий для запроса к таблицам, которые отображаются как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="dca2d-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="dca2d-141">Запрос фильтрует результаты и возвращает только клиентов, которые находятся в `London`.</span><span class="sxs-lookup"><span data-stu-id="dca2d-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     <span data-ttu-id="dca2d-142">[!code-vb[VbLINQToSQLHowTos&11;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dca2d-142">[!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="dca2d-143">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="dca2d-143">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="dca2d-144">Ниже приведены другие фильтры, которые можно попробовать.</span><span class="sxs-lookup"><span data-stu-id="dca2d-144">Following are some other filters that you can try.</span></span>  
  
     <span data-ttu-id="dca2d-145">[!code-vb[VbLINQToSQLHowTos&#12;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dca2d-145">[!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca2d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="dca2d-146">See Also</span></span>  
 <span data-ttu-id="dca2d-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="dca2d-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="dca2d-148"> [Запросы](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="dca2d-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="dca2d-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="dca2d-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="dca2d-150"> [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="dca2d-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

