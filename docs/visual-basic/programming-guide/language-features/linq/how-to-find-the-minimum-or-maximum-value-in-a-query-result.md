---
title: Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ
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
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112366"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="4b4b3-102">Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b4b3-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="4b4b3-103">Интегрированный в язык запрос (LINЗ) упрощает доступ к информации базы данных и выполняет запросы.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="4b4b3-104">В следующем примере показано, как создать новое приложение, выполняя запросы в соответствии с базой данных сервера S'L.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="4b4b3-105">Выборка определяет минимальные и максимальные значения результатов `Group By` с помощью ипредложений. `Aggregate`</span><span class="sxs-lookup"><span data-stu-id="4b4b3-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="4b4b3-106">Для получения дополнительной информации [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) [см.](../../../../visual-basic/language-reference/queries/aggregate-clause.md)</span><span class="sxs-lookup"><span data-stu-id="4b4b3-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="4b4b3-107">Примеры этой темы используют базу данных примеров Northwind.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="4b4b3-108">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="4b4b3-109">Для получения инструкций [см.](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)</span><span class="sxs-lookup"><span data-stu-id="4b4b3-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="4b4b3-110">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="4b4b3-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="4b4b3-111">В Visual Studio, открыть **Server Explorer**/**Database Explorer,** нажав **Сервер Explorer**/**базы данных Explorer** в меню **просмотра.**</span><span class="sxs-lookup"><span data-stu-id="4b4b3-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="4b4b3-112">Правый клик **подключения к данным** в Server **Explorer**/**Database Explorer,** а затем нажмите **Добавить соединение**.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="4b4b3-113">Укажите действительное подключение к базе данных образца Northwind.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="4b4b3-114">Добавление проекта, содержащего файл LIN's в файл S'L</span><span class="sxs-lookup"><span data-stu-id="4b4b3-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="4b4b3-115">В Visual Studio, в меню **файла,** укажите на **новый,** а затем нажмите **Project**.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="4b4b3-116">Выберите приложение Visual Basic **Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="4b4b3-117">В меню **Проект** выберите **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="4b4b3-118">Выберите шаблон элементов **LIN's для классов S'L.**</span><span class="sxs-lookup"><span data-stu-id="4b4b3-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="4b4b3-119">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="4b4b3-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-120">Click **Add**.</span></span> <span data-ttu-id="4b4b3-121">Объект реляционный конструктор (O/R Designer) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="4b4b3-122">Добавление таблиц в запрос к конструктору O/R</span><span class="sxs-lookup"><span data-stu-id="4b4b3-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="4b4b3-123">В **Server Explorer**/**Database Explorer**расширьте подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="4b4b3-124">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="4b4b3-125">Если вы закрыли O/R Designer, вы можете открыть его, дважды нажав на файл northwind.dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="4b4b3-126">Нажмите таблицу Клиентов и перетащите его в левую панель дизайнера.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="4b4b3-127">Нажмите на таблицу заказов и перетащите ее в левую панель дизайнера.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="4b4b3-128">Дизайнер создает `Customer` новые и `Order` объекты для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="4b4b3-129">Обратите внимание, что дизайнер автоматически обнаруживает отношения между таблицами и создает свойства ребенка для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="4b4b3-130">Например, IntelliSense покажет, `Customer` что `Orders` объект имеет свойство для всех заказов, связанных с этим клиентом.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="4b4b3-131">Сохраните изменения и закройте дизайнера.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="4b4b3-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="4b4b3-133">Добавление кода для запроса базы данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="4b4b3-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="4b4b3-134">Из **toolbox**перетащите <xref:System.Windows.Forms.DataGridView> элемент управления на форму Windows по умолчанию для вашего проекта Form1.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="4b4b3-135">Дважды щелкните форму1, чтобы добавить код к событию `Load` формы.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="4b4b3-136">При добавлении таблиц в конструктор O/R <xref:System.Data.Linq.DataContext> дизайнер добавляет объект для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="4b4b3-137">Этот объект содержит код, который необходимо получить доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="4b4b3-138">Объект <xref:System.Data.Linq.DataContext> для проекта назван на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="4b4b3-139">Для этого проекта <xref:System.Data.Linq.DataContext> объект `northwindDataContext`называется .</span><span class="sxs-lookup"><span data-stu-id="4b4b3-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="4b4b3-140">Можно создать экземпляр <xref:System.Data.Linq.DataContext> кода и заказать таблицы, указанные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="4b4b3-141">Добавьте в событие `Load` следующий код.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="4b4b3-142">Этот код запрашивает таблицы, которые разоблачаются как свойства контекста данных, и определяет минимальные и максимальные значения для результатов.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="4b4b3-143">В выборке `Aggregate` используется оговорка для запроса `Group By` для одного результата, а в предложении — среднее значение для сгруппированных результатов.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="4b4b3-144">Нажмите **F5,** чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="4b4b3-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b4b3-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4b4b3-145">See also</span></span>

- [<span data-ttu-id="4b4b3-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="4b4b3-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="4b4b3-147">Запросов</span><span class="sxs-lookup"><span data-stu-id="4b4b3-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="4b4b3-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4b4b3-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="4b4b3-149">Методы DataContext (O/R Конструктор)</span><span class="sxs-lookup"><span data-stu-id="4b4b3-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
