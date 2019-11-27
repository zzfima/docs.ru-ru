---
title: Инструкции. подсчет, суммирование или средние данные с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
ms.openlocfilehash: 7e105c75653f979f53567ef49f1f4cdeafaa4d0f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345014"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="6ba0e-102">Практическое руководство. Выполнение над данными функций Count, Sum и Average с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ba0e-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="6ba0e-103">LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="6ba0e-104">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="6ba0e-105">Пример подсчитывает, суммирует и усредняет результаты с помощью предложений `Aggregate` и `Group By`.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="6ba0e-106">Дополнительные сведения см. в разделе [предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение GROUP BY](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6ba0e-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="6ba0e-107">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="6ba0e-108">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="6ba0e-109">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="6ba0e-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="6ba0e-110">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="6ba0e-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="6ba0e-111">В Visual Studio откройте **обозреватель сервера**/**обозреватель базы данных** , выбрав **Обозреватель сервера**/**Обозреватель базы данных** в меню **вид** .</span><span class="sxs-lookup"><span data-stu-id="6ba0e-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="6ba0e-112">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем нажмите кнопку **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="6ba0e-113">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="6ba0e-114">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6ba0e-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="6ba0e-115">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="6ba0e-116">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="6ba0e-117">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6ba0e-118">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="6ba0e-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="6ba0e-119">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="6ba0e-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-120">Click **Add**.</span></span> <span data-ttu-id="6ba0e-121">Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="6ba0e-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="6ba0e-122">Добавление таблиц в запрос в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="6ba0e-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="6ba0e-123">В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="6ba0e-124">Разверните папку **таблицы** .</span><span class="sxs-lookup"><span data-stu-id="6ba0e-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="6ba0e-125">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="6ba0e-126">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="6ba0e-127">Щелкните таблицу Orders и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="6ba0e-128">Конструктор создает в проекте новые `Customer` и `Order` объекты.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="6ba0e-129">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="6ba0e-130">Например, IntelliSense покажет, что объект `Customer` имеет свойство `Orders` для всех заказов, связанных с этим клиентом.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="6ba0e-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="6ba0e-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="6ba0e-133">Добавление кода для запроса к базе данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="6ba0e-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="6ba0e-134">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="6ba0e-135">Дважды щелкните Form1, чтобы добавить код в событие `Load` формы.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="6ba0e-136">При добавлении таблиц в реляционный конструктор объектов конструктор добавил объект <xref:System.Data.Linq.DataContext> для проекта.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="6ba0e-137">Этот объект содержит код, который необходим для доступа к этим таблицам и для доступа к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="6ba0e-138">Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="6ba0e-139">Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="6ba0e-140">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, заданные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="6ba0e-141">Добавьте следующий код в событие `Load`, чтобы запросить таблицы, предоставляемые как свойства <xref:System.Data.Linq.DataContext>, а также подсчитать, суммировать и усреднить результаты.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="6ba0e-142">В примере используется предложение `Aggregate` для запроса одного результата, а для отображения среднего для сгруппированных результатов — предложение `Group By`.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. <span data-ttu-id="6ba0e-143">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="6ba0e-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba0e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="6ba0e-144">See also</span></span>

- [<span data-ttu-id="6ba0e-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="6ba0e-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="6ba0e-146">Запросы</span><span class="sxs-lookup"><span data-stu-id="6ba0e-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="6ba0e-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6ba0e-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="6ba0e-148">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="6ba0e-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="6ba0e-149">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="6ba0e-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="6ba0e-150">Предложение Group By</span><span class="sxs-lookup"><span data-stu-id="6ba0e-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
