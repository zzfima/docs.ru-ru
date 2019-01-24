---
title: Как выполнить Возвращение результата запроса LINQ в виде определенного типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 7d281de2005f1ee9227b3e3496125c8af9acba35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500620"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="83000-102">Как выполнить Возвращение результата запроса LINQ в виде определенного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83000-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="83000-103">Language-Integrated Query (LINQ) позволяет легко получить доступ к информации базы данных и выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="83000-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="83000-104">По умолчанию запросы LINQ возвращают список объектов как анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="83000-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="83000-105">Можно также указать, чтобы запрос возвращал список определенного типа с помощью `Select` предложение.</span><span class="sxs-lookup"><span data-stu-id="83000-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="83000-106">Приведенный ниже показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и результаты запроса проецируются как конкретный именованный тип.</span><span class="sxs-lookup"><span data-stu-id="83000-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="83000-107">Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) и [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="83000-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="83000-108">В примерах в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="83000-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="83000-109">Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="83000-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="83000-110">Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="83000-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="83000-111">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="83000-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="83000-112">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="83000-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="83000-113">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="83000-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="83000-114">Укажите допустимое соединение с образцом базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="83000-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="83000-115">Чтобы добавить в проект, содержащий файл классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="83000-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="83000-116">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="83000-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="83000-117">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="83000-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="83000-118">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="83000-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="83000-119">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="83000-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="83000-120">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="83000-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="83000-121">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="83000-121">Click **Add**.</span></span> <span data-ttu-id="83000-122">Для файла northwind.dbml открывается реляционный конструктор объектов (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="83000-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="83000-123">Добавление таблицы к запросу в конструкторе O/R</span><span class="sxs-lookup"><span data-stu-id="83000-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="83000-124">В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="83000-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="83000-125">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="83000-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="83000-126">Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="83000-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="83000-127">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="83000-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="83000-128">Конструктор создает новый `Customer` объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="83000-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="83000-129">Вы можете проецировать результат запроса как `Customer` тип или тип, который создается.</span><span class="sxs-lookup"><span data-stu-id="83000-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="83000-130">Этот пример будет создать новый тип в последующей процедуре и результат запроса как этот тип проекта.</span><span class="sxs-lookup"><span data-stu-id="83000-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="83000-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="83000-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="83000-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="83000-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="83000-133">Добавление кода для запроса к базе данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="83000-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="83000-134">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="83000-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="83000-135">Дважды щелкните файл Form1, чтобы изменить класс Form1.</span><span class="sxs-lookup"><span data-stu-id="83000-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="83000-136">После `End Class` инструкции класса Form1 добавьте следующий код для создания `CustomerInfo` тип, содержащий результаты запроса для этого примера.</span><span class="sxs-lookup"><span data-stu-id="83000-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  <span data-ttu-id="83000-137">При добавлении таблиц в конструктор O/R designer добавлены <xref:System.Data.Linq.DataContext> объект в проект.</span><span class="sxs-lookup"><span data-stu-id="83000-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="83000-138">Этот объект содержит код, который необходимо иметь для доступа к этим таблицам и для доступа к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="83000-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="83000-139"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="83000-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="83000-140">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="83000-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="83000-141">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запрос таблицы, указанные в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="83000-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="83000-142">В `Load` класса Form1, добавьте следующий код для запроса к таблицам, которые представляются как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="83000-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="83000-143">`Select` Предложение запроса будет создан новый `CustomerInfo` типа вместо анонимного типа для каждого элемента результата запроса.</span><span class="sxs-lookup"><span data-stu-id="83000-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  <span data-ttu-id="83000-144">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="83000-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83000-145">См. также</span><span class="sxs-lookup"><span data-stu-id="83000-145">See also</span></span>
- [<span data-ttu-id="83000-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="83000-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="83000-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="83000-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="83000-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="83000-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="83000-149">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="83000-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
