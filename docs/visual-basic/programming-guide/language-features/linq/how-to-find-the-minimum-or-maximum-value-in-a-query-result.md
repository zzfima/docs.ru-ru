---
title: "Практическое руководство: поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic) | Документы Microsoft"
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
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
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
ms.openlocfilehash: 76f5ad02dc79bf8447ae0656c0ea90b5d9bb8edc
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="8d6e5-102">Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d6e5-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="8d6e5-103">Language Integrated Query (LINQ) упрощает для доступа к базе данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="8d6e5-104">Следующий пример демонстрирует создание нового приложения, выполняющего запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="8d6e5-105">В примере определяются минимальное и максимальное значения для результатов с помощью `Aggregate` и `Group By` предложения.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="8d6e5-106">Дополнительные сведения см. в разделе [предложения Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8d6e5-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="8d6e5-107">Примеры в этом разделе используется образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="8d6e5-108">Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="8d6e5-109">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="8d6e5-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="8d6e5-110">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="8d6e5-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="8d6e5-111">В Visual Studio откройте **обозреватель серверов**/**обозревателя базы данных** , щелкнув **обозревателя**/**обозреватель баз данных** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="8d6e5-112">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных** и нажмите кнопку **Добавление подключения**.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="8d6e5-113">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="8d6e5-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="8d6e5-114">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8d6e5-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="8d6e5-115">В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="8d6e5-116">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="8d6e5-117">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="8d6e5-118">Выберите **классы LINQ to SQL** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="8d6e5-119">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="8d6e5-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-120">Click **Add**.</span></span> <span data-ttu-id="8d6e5-121">Реляционный конструктор объектов (конструктор O/R) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="8d6e5-122">Добавление таблицы к запросу реляционный конструктор объектов</span><span class="sxs-lookup"><span data-stu-id="8d6e5-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="8d6e5-123">В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="8d6e5-124">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="8d6e5-125">Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="8d6e5-126">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="8d6e5-127">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="8d6e5-128">Конструктор создает новый `Customer` и `Order` объекты для проекта.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="8d6e5-129">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="8d6e5-130">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="8d6e5-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="8d6e5-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="8d6e5-133">Чтобы добавить код для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="8d6e5-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="8d6e5-134">От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="8d6e5-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="8d6e5-135">Дважды щелкните Form1, чтобы добавить код для `Load` события формы.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="8d6e5-136">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект для проекта.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="8d6e5-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="8d6e5-137">Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="8d6e5-138"><xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="8d6e5-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="8d6e5-139">Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="8d6e5-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="8d6e5-140">Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и запросить таблицы, указанные в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="8d6e5-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="8d6e5-141">Добавьте следующий код в `Load` событий.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="8d6e5-142">Этот код запрашивает таблицы, которые представляются как свойства в контексте данных и определяет минимальное и максимальное значения для результатов.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="8d6e5-143">Пример использует `Aggregate` предложение для запроса одного результата и `Group By` предложения для отображения среднего значения для сгруппированных результатов.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     <span data-ttu-id="8d6e5-144">[!code-vb[VbLINQToSQLHowTos&#14;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d6e5-144">[!code-vb[VbLINQToSQLHowTos#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]</span></span>  
  
4.  <span data-ttu-id="8d6e5-145">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="8d6e5-145">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d6e5-146">См. также</span><span class="sxs-lookup"><span data-stu-id="8d6e5-146">See Also</span></span>  
 <span data-ttu-id="8d6e5-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d6e5-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="8d6e5-148"> [Запросы](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="8d6e5-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="8d6e5-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="8d6e5-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="8d6e5-150"> [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="8d6e5-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

