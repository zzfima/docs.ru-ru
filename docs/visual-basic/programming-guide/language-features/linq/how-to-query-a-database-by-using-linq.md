---
title: Инструкции. запрос к базе данных с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: f4b2510bad2b23d7a0e179383b34c4e425e6564e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344959"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="b04f8-102">Практическое руководство. Выполнение запросов к базе данных с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b04f8-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="b04f8-103">LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.</span><span class="sxs-lookup"><span data-stu-id="b04f8-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="b04f8-104">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b04f8-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="b04f8-105">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="b04f8-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="b04f8-106">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b04f8-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="b04f8-107">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b04f8-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="b04f8-108">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="b04f8-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="b04f8-109">В Visual Studio откройте **обозреватель сервера**/**обозреватель базы данных** , выбрав **Обозреватель сервера**/**Обозреватель базы данных** в меню **вид** .</span><span class="sxs-lookup"><span data-stu-id="b04f8-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="b04f8-110">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем нажмите кнопку **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="b04f8-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="b04f8-111">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="b04f8-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="b04f8-112">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b04f8-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="b04f8-113">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="b04f8-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="b04f8-114">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="b04f8-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="b04f8-115">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="b04f8-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="b04f8-116">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="b04f8-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="b04f8-117">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="b04f8-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="b04f8-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b04f8-118">Click **Add**.</span></span> <span data-ttu-id="b04f8-119">Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="b04f8-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="b04f8-120">Добавление таблиц в запрос в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="b04f8-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="b04f8-121">В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="b04f8-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="b04f8-122">Разверните папку **таблицы** .</span><span class="sxs-lookup"><span data-stu-id="b04f8-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="b04f8-123">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="b04f8-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="b04f8-124">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="b04f8-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="b04f8-125">Щелкните таблицу Orders и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="b04f8-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="b04f8-126">Конструктор создает в проекте новые `Customer` и `Order` объекты.</span><span class="sxs-lookup"><span data-stu-id="b04f8-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="b04f8-127">Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="b04f8-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="b04f8-128">Например, IntelliSense покажет, что объект `Customer` имеет свойство `Orders` для всех заказов, связанных с этим клиентом.</span><span class="sxs-lookup"><span data-stu-id="b04f8-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="b04f8-129">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="b04f8-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="b04f8-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="b04f8-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="b04f8-131">Добавление кода для запроса к базе данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="b04f8-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="b04f8-132">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="b04f8-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="b04f8-133">Дважды щелкните Form1, чтобы добавить код в событие `Load` формы.</span><span class="sxs-lookup"><span data-stu-id="b04f8-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="b04f8-134">При добавлении таблиц в реляционный конструктор объектов конструктор добавил объект <xref:System.Data.Linq.DataContext> для проекта.</span><span class="sxs-lookup"><span data-stu-id="b04f8-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="b04f8-135">Этот объект содержит код, который необходим для доступа к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b04f8-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="b04f8-136">Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="b04f8-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="b04f8-137">Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="b04f8-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="b04f8-138">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, заданные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="b04f8-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="b04f8-139">Добавьте следующий код в событие `Load`, чтобы запросить таблицы, предоставляемые как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="b04f8-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="b04f8-140">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="b04f8-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="b04f8-141">Ниже приведены некоторые дополнительные запросы, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="b04f8-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="b04f8-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b04f8-142">See also</span></span>

- [<span data-ttu-id="b04f8-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="b04f8-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="b04f8-144">Запросы</span><span class="sxs-lookup"><span data-stu-id="b04f8-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b04f8-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b04f8-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="b04f8-146">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="b04f8-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
