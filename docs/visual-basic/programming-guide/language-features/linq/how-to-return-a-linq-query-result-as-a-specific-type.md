---
title: "Практическое руководство: возвращение результата запроса LINQ в виде определенного типа (Visual Basic) | Документы Microsoft"
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
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
caps.latest.revision: 8
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
ms.openlocfilehash: ecbc691a0afeb7ba631949684a0457d9bcdb2728
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="e7c67-102">Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7c67-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="e7c67-103">Language Integrated Query (LINQ) упрощает для доступа к базе данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="e7c67-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="e7c67-104">По умолчанию запросы LINQ возвращают список объектов как анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="e7c67-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="e7c67-105">Можно также указать, чтобы запрос возвращал список определенного типа с помощью `Select` предложения.</span><span class="sxs-lookup"><span data-stu-id="e7c67-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="e7c67-106">Следующий пример демонстрирует создание нового приложения, которое выполняет запросы к базе данных SQL Server и формирует результаты, как конкретный именованный тип.</span><span class="sxs-lookup"><span data-stu-id="e7c67-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="e7c67-107">Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) и [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e7c67-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="e7c67-108">Примеры в этом разделе используется образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="e7c67-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e7c67-109">Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="e7c67-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="e7c67-110">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="e7c67-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e7c67-111">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="e7c67-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="e7c67-112">В Visual Studio откройте **обозреватель серверов**/**обозревателя базы данных** , щелкнув **обозревателя**/**обозреватель баз данных** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="e7c67-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="e7c67-113">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных** и нажмите кнопку **Добавление подключения**.</span><span class="sxs-lookup"><span data-stu-id="e7c67-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="e7c67-114">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="e7c67-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e7c67-115">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e7c67-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="e7c67-116">В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="e7c67-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e7c67-117">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="e7c67-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="e7c67-118">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e7c67-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e7c67-119">Выберите **классы LINQ to SQL** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="e7c67-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="e7c67-120">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="e7c67-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e7c67-121">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e7c67-121">Click **Add**.</span></span> <span data-ttu-id="e7c67-122">Реляционный конструктор объектов (конструктор O/R) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="e7c67-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="e7c67-123">Добавление таблицы к запросу реляционный конструктор объектов</span><span class="sxs-lookup"><span data-stu-id="e7c67-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="e7c67-124">В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="e7c67-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e7c67-125">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="e7c67-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e7c67-126">Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="e7c67-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="e7c67-127">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="e7c67-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e7c67-128">Конструктор создает новый `Customer` объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="e7c67-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="e7c67-129">Можно проецировать результат запроса как `Customer` тип или тип, который можно создать.</span><span class="sxs-lookup"><span data-stu-id="e7c67-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="e7c67-130">В этом примере будет создать новый тип в процедуре более поздней версии и сформирован результат запроса как тип.</span><span class="sxs-lookup"><span data-stu-id="e7c67-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="e7c67-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="e7c67-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="e7c67-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="e7c67-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="e7c67-133">Чтобы добавить код для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="e7c67-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="e7c67-134">От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="e7c67-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="e7c67-135">Дважды щелкните форму Form1, чтобы изменить класс Form1.</span><span class="sxs-lookup"><span data-stu-id="e7c67-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="e7c67-136">После `End Class` инструкции класса Form1 добавьте следующий код для создания `CustomerInfo` типа для хранения результатов запроса для данного образца.</span><span class="sxs-lookup"><span data-stu-id="e7c67-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     <span data-ttu-id="e7c67-137">[!code-vb[VbLINQToSQLHowTos №&16;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7c67-137">[!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]</span></span>  
  
4.  <span data-ttu-id="e7c67-138">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект в проект.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e7c67-138">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="e7c67-139">Этот объект содержит код, необходимый для доступа к этим таблицам и доступа к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e7c67-139">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="e7c67-140"><xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e7c67-140">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e7c67-141">Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e7c67-141">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e7c67-142">Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и запросить таблицы, указанные в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e7c67-142">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="e7c67-143">В `Load` класса Form1 добавьте следующий код для запроса к таблицам, которые отображаются как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="e7c67-143">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="e7c67-144">`Select` Выражение запроса будет создан новый `CustomerInfo` типа вместо анонимного типа для каждого элемента результата запроса.</span><span class="sxs-lookup"><span data-stu-id="e7c67-144">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     <span data-ttu-id="e7c67-145">[!code-vb[VbLINQToSQLHowTos&#15;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7c67-145">[!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]</span></span>  
  
5.  <span data-ttu-id="e7c67-146">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="e7c67-146">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c67-147">См. также</span><span class="sxs-lookup"><span data-stu-id="e7c67-147">See Also</span></span>  
 <span data-ttu-id="e7c67-148">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="e7c67-148">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="e7c67-149"> [Запросы](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="e7c67-149"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="e7c67-150"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="e7c67-150"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="e7c67-151"> [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="e7c67-151"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

