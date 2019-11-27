---
title: Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 1084743b0c50d381375b76a3116ed7c9e6f9d769
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354204"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="fe7bd-102">Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe7bd-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="fe7bd-103">LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="fe7bd-104">По умолчанию запросы LINQ возвращают список объектов в виде анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="fe7bd-105">Можно также указать, что запрос возвращает список определенного типа с помощью предложения `Select`.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="fe7bd-106">В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и проецирует результаты в виде определенного именованного типа.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="fe7bd-107">Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) и [предложение SELECT](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fe7bd-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="fe7bd-108">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fe7bd-109">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fe7bd-110">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fe7bd-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="fe7bd-111">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="fe7bd-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="fe7bd-112">В Visual Studio откройте **обозреватель сервера**/**обозреватель базы данных** , выбрав **Обозреватель сервера**/**Обозреватель базы данных** в меню **вид** .</span><span class="sxs-lookup"><span data-stu-id="fe7bd-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fe7bd-113">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем нажмите кнопку **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fe7bd-114">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fe7bd-115">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fe7bd-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fe7bd-116">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fe7bd-117">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fe7bd-118">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fe7bd-119">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="fe7bd-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fe7bd-120">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fe7bd-121">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-121">Click **Add**.</span></span> <span data-ttu-id="fe7bd-122">Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="fe7bd-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fe7bd-123">Добавление таблиц в запрос в реляционный конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="fe7bd-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fe7bd-124">В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fe7bd-125">Разверните папку **таблицы** .</span><span class="sxs-lookup"><span data-stu-id="fe7bd-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fe7bd-126">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fe7bd-127">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fe7bd-128">Конструктор создает новый объект `Customer` для проекта.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="fe7bd-129">Результат запроса можно проецировать в виде `Customer` типа или в виде создаваемого типа.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="fe7bd-130">Этот пример создаст новый тип в следующей процедуре и запишет результат запроса в качестве этого типа.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="fe7bd-131">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fe7bd-132">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fe7bd-133">Добавление кода для запроса к базе данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="fe7bd-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fe7bd-134">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fe7bd-135">Дважды щелкните Form1, чтобы изменить класс Form1.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="fe7bd-136">После оператора `End Class` класса Form1 добавьте следующий код, чтобы создать `CustomerInfo` тип для хранения результатов запроса для этого примера.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="fe7bd-137">При добавлении таблиц в реляционный конструктор объектов конструктор добавил в проект объект <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="fe7bd-138">Этот объект содержит код, который необходим для доступа к этим таблицам и для доступа к отдельным объектам и коллекциям для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="fe7bd-139">Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fe7bd-140">Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fe7bd-141">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, заданные конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fe7bd-142">В событии `Load` класса Form1 добавьте следующий код, чтобы запросить таблицы, предоставляемые как свойства контекста данных.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="fe7bd-143">В предложении `Select` запроса будет создан новый тип `CustomerInfo` вместо анонимного типа для каждого элемента результата запроса.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="fe7bd-144">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="fe7bd-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7bd-145">См. также</span><span class="sxs-lookup"><span data-stu-id="fe7bd-145">See also</span></span>

- [<span data-ttu-id="fe7bd-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="fe7bd-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="fe7bd-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="fe7bd-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="fe7bd-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fe7bd-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fe7bd-149">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="fe7bd-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
