---
title: "Практическое руководство. Выполнение запросов к базе данных с помощью LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9949b5f6f670c66463c42a71434c0cdd941c995b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="5936d-102">Практическое руководство. Выполнение запросов к базе данных с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5936d-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="5936d-103">Встроенные в язык запросы (LINQ) упрощает доступ к данным базы данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="5936d-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="5936d-104">В следующем примере демонстрируется создание нового приложения, которое выполняет запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5936d-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="5936d-105">Примеры в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="5936d-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="5936d-106">Если у вас образца базы данных "Борей" на компьютере разработчика, его можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="5936d-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="5936d-107">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="5936d-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="5936d-108">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="5936d-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="5936d-109">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="5936d-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="5936d-110">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="5936d-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="5936d-111">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="5936d-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="5936d-112">Чтобы добавить в проект, содержащий файл классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5936d-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="5936d-113">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="5936d-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="5936d-114">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="5936d-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="5936d-115">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="5936d-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="5936d-116">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="5936d-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="5936d-117">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="5936d-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="5936d-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5936d-118">Click **Add**.</span></span> <span data-ttu-id="5936d-119">Реляционный конструктор объектов (O/R-конструктор) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="5936d-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="5936d-120">Добавление таблицы к запросу в конструкторе O/R</span><span class="sxs-lookup"><span data-stu-id="5936d-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="5936d-121">В **обозревателя серверов**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="5936d-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="5936d-122">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="5936d-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="5936d-123">Если O/R-конструктор закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="5936d-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="5936d-124">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="5936d-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="5936d-125">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="5936d-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="5936d-126">Конструктор создает новый `Customer` и `Order` объектов для проекта.</span><span class="sxs-lookup"><span data-stu-id="5936d-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="5936d-127">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="5936d-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="5936d-128">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="5936d-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="5936d-129">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="5936d-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="5936d-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="5936d-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="5936d-131">Добавление кода для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="5936d-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="5936d-132">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> на форме Windows Forms по умолчанию для проекта, Form1 элемент управления.</span><span class="sxs-lookup"><span data-stu-id="5936d-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="5936d-133">Дважды щелкните файл Form1, чтобы добавить код для `Load` событие в формате.</span><span class="sxs-lookup"><span data-stu-id="5936d-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="5936d-134">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объектов для проекта.</span><span class="sxs-lookup"><span data-stu-id="5936d-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="5936d-135">Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5936d-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="5936d-136"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="5936d-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="5936d-137">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="5936d-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="5936d-138">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, указанные в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="5936d-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="5936d-139">Добавьте следующий код в `Load` событий для запроса к таблицам, которые представляются как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="5936d-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="5936d-140">Нажмите клавишу F5 для запуска проекта и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="5936d-140">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="5936d-141">Ниже приведены некоторые дополнительные запросы, которые вы можете попробовать.</span><span class="sxs-lookup"><span data-stu-id="5936d-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5936d-142">См. также</span><span class="sxs-lookup"><span data-stu-id="5936d-142">See Also</span></span>  
 [<span data-ttu-id="5936d-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="5936d-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="5936d-144">Запросы</span><span class="sxs-lookup"><span data-stu-id="5936d-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="5936d-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5936d-145">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="5936d-146">Методы DataContext (O/R-конструктор)</span><span class="sxs-lookup"><span data-stu-id="5936d-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
