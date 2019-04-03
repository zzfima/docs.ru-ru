---
title: Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 2d05d43ae8f9b93fd3e5e405bb7ff0d59832e830
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823354"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="aac16-102">Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aac16-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="aac16-103">Language-Integrated Query (LINQ) позволяет легко получить доступ к информации базы данных, включая объекты, такие как хранимые процедуры базы данных.</span><span class="sxs-lookup"><span data-stu-id="aac16-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="aac16-104">В следующем примере показано, как создать приложение, которое вызывает хранимую процедуру в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aac16-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="aac16-105">Образец показан порядок вызова двух различных хранимых процедур в базе данных.</span><span class="sxs-lookup"><span data-stu-id="aac16-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="aac16-106">Каждая процедура возвращает результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="aac16-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="aac16-107">Одна процедура принимает входные параметры, а другая процедура не принимает параметров.</span><span class="sxs-lookup"><span data-stu-id="aac16-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="aac16-108">В примерах в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="aac16-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="aac16-109">Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aac16-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="aac16-110">Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="aac16-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="aac16-111">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="aac16-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="aac16-112">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="aac16-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="aac16-113">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="aac16-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="aac16-114">Укажите допустимое соединение с образцом базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="aac16-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="aac16-115">Чтобы добавить в проект, содержащий файл классов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="aac16-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="aac16-116">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="aac16-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="aac16-117">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="aac16-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="aac16-118">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="aac16-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="aac16-119">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="aac16-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="aac16-120">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="aac16-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="aac16-121">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="aac16-121">Click **Add**.</span></span> <span data-ttu-id="aac16-122">Для файла northwind.dbml открывается реляционный конструктор объектов (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="aac16-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="aac16-123">Добавление хранимых процедур в конструктор O/R</span><span class="sxs-lookup"><span data-stu-id="aac16-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="aac16-124">В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="aac16-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="aac16-125">Разверните **хранимые процедуры** папки.</span><span class="sxs-lookup"><span data-stu-id="aac16-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="aac16-126">Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="aac16-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="aac16-127">Нажмите кнопку **продаж по годам** хранимую процедуру и перетащите его на правую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="aac16-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="aac16-128">Нажмите кнопку **десять самых дорогих продуктов** хранимой процедуры перетащите его на правую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="aac16-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="aac16-129">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="aac16-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="aac16-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="aac16-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="aac16-131">Чтобы добавить код для отображения результатов хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="aac16-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="aac16-132">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="aac16-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="aac16-133">Дважды щелкните файл Form1, чтобы добавить код для его `Load` событий.</span><span class="sxs-lookup"><span data-stu-id="aac16-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="aac16-134">При добавлении хранимых процедур в конструктор O/R, разработчик добавил <xref:System.Data.Linq.DataContext> объект для проекта.</span><span class="sxs-lookup"><span data-stu-id="aac16-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="aac16-135">Этот объект содержит код, которые необходимы для доступа к этим процедурам.</span><span class="sxs-lookup"><span data-stu-id="aac16-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="aac16-136"><xref:System.Data.Linq.DataContext> Объектов для проекта присваивается на основе имени из DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="aac16-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="aac16-137">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="aac16-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="aac16-138">Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и вызывать методы хранимой процедуры, указанную конструктором O/R.</span><span class="sxs-lookup"><span data-stu-id="aac16-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="aac16-139">Для привязки к <xref:System.Windows.Forms.DataGridView> объекта, может потребоваться принудительно выполнять запрос выполняться немедленно, вызвав <xref:System.Linq.Enumerable.ToList%2A> метод результатов хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="aac16-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="aac16-140">Добавьте следующий код, чтобы `Load` событий для вызова одной из хранимых процедур, предоставленных как методы в контексте данных.</span><span class="sxs-lookup"><span data-stu-id="aac16-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4.  <span data-ttu-id="aac16-141">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="aac16-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac16-142">См. также</span><span class="sxs-lookup"><span data-stu-id="aac16-142">See also</span></span>

- [<span data-ttu-id="aac16-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="aac16-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="aac16-144">Запросы</span><span class="sxs-lookup"><span data-stu-id="aac16-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="aac16-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="aac16-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="aac16-146">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="aac16-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="aac16-147">Практическое руководство. Назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="aac16-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
