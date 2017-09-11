---
title: "Практическое руководство: запросов к базе данных с помощью LINQ (Visual Basic) | Документы Microsoft"
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
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: 12
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
ms.openlocfilehash: a645a71dd0489d6bf2cc0cd4fe5898eb7293f13c
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="dfe96-102">Практическое руководство. Выполнение запросов к базе данных с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfe96-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="dfe96-103">Language Integrated Query (LINQ) упрощает для доступа к базе данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="dfe96-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="dfe96-104">Следующий пример демонстрирует создание нового приложения, выполняющего запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dfe96-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="dfe96-105">Примеры в этом разделе используется образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="dfe96-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="dfe96-106">Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="dfe96-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="dfe96-107">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="dfe96-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="dfe96-108">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="dfe96-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="dfe96-109">В Visual Studio откройте **обозреватель серверов**/**обозревателя базы данных** , щелкнув **обозревателя**/**обозреватель баз данных** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="dfe96-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="dfe96-110">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных** и нажмите кнопку **Добавление подключения**.</span><span class="sxs-lookup"><span data-stu-id="dfe96-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="dfe96-111">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="dfe96-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="dfe96-112">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dfe96-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="dfe96-113">В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="dfe96-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="dfe96-114">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="dfe96-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="dfe96-115">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="dfe96-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="dfe96-116">Выберите **классы LINQ to SQL** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="dfe96-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="dfe96-117">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="dfe96-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="dfe96-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dfe96-118">Click **Add**.</span></span> <span data-ttu-id="dfe96-119">Реляционный конструктор объектов (конструктор O/R) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="dfe96-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="dfe96-120">Добавление таблицы к запросу реляционный конструктор объектов</span><span class="sxs-lookup"><span data-stu-id="dfe96-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="dfe96-121">В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="dfe96-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="dfe96-122">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="dfe96-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="dfe96-123">Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="dfe96-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="dfe96-124">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="dfe96-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="dfe96-125">Щелкните в таблице Orders и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="dfe96-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="dfe96-126">Конструктор создает новый `Customer` и `Order` объекты для проекта.</span><span class="sxs-lookup"><span data-stu-id="dfe96-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="dfe96-127">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="dfe96-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="dfe96-128">Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="dfe96-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="dfe96-129">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="dfe96-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="dfe96-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="dfe96-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="dfe96-131">Чтобы добавить код для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="dfe96-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="dfe96-132">От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="dfe96-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="dfe96-133">Дважды щелкните Form1, чтобы добавить код для `Load` события формы.</span><span class="sxs-lookup"><span data-stu-id="dfe96-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="dfe96-134">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект для проекта.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dfe96-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="dfe96-135">Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="dfe96-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="dfe96-136"><xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dfe96-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="dfe96-137">Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dfe96-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="dfe96-138">Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и запросить таблицы, указанные в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="dfe96-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="dfe96-139">Добавьте следующий код в `Load` событий для запроса к таблицам, которые отображаются как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="dfe96-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     <span data-ttu-id="dfe96-140">[!code-vb[VbLINQToSQLHowTos&#3;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dfe96-140">[!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="dfe96-141">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="dfe96-141">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="dfe96-142">Ниже приведены некоторые дополнительные запросы, которые могут помочь.</span><span class="sxs-lookup"><span data-stu-id="dfe96-142">Following are some additional queries that you can try:</span></span>  
  
     <span data-ttu-id="dfe96-143">[!code-vb[VbLINQToSQLHowTos&#4;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dfe96-143">[!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span></span>  
    <span data-ttu-id="dfe96-144">[!code-vb[VbLINQToSQLHowTos&#5;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="dfe96-144">[!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe96-145">См. также</span><span class="sxs-lookup"><span data-stu-id="dfe96-145">See Also</span></span>  
 <span data-ttu-id="dfe96-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="dfe96-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="dfe96-147"> [Запросы](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="dfe96-147"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="dfe96-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="dfe96-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="dfe96-149"> [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="dfe96-149"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

