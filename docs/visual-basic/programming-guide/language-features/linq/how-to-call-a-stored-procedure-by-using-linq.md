---
title: "Практическое руководство: вызов хранимой процедуры с помощью LINQ (Visual Basic) | Документы Microsoft"
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
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
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
ms.openlocfilehash: 40e72ece8399b1ffbe8c5457c63113d563c9f7f8
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="d4ebe-102">Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4ebe-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="d4ebe-103">Language Integrated Query (LINQ) позволяет легко доступа к базе данных, включая объекты, такие как хранимые процедуры базы данных.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="d4ebe-104">В следующем примере демонстрируется создание приложения, которое вызывает хранимую процедуру в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="d4ebe-105">Образец показано, как вызвать две различные хранимые процедуры в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="d4ebe-106">Каждая процедура возвращает результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="d4ebe-107">Одна процедура принимает входные параметры, а другая процедура не принимает параметров.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="d4ebe-108">Примеры в этом разделе используется образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="d4ebe-109">Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="d4ebe-110">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="d4ebe-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="d4ebe-111">Создание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="d4ebe-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="d4ebe-112">В Visual Studio откройте **обозреватель серверов**/**обозревателя базы данных** , щелкнув **обозревателя**/**обозреватель баз данных** на **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="d4ebe-113">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных** и нажмите кнопку **Добавление подключения**.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="d4ebe-114">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="d4ebe-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="d4ebe-115">Добавление проекта, содержащего файл LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d4ebe-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="d4ebe-116">В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="d4ebe-117">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="d4ebe-118">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="d4ebe-119">Выберите **классы LINQ to SQL** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="d4ebe-120">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="d4ebe-121">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-121">Click **Add**.</span></span> <span data-ttu-id="d4ebe-122">Реляционный конструктор объектов (конструктор O/R) открыт для файла northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="d4ebe-123">Добавление хранимой процедуры в реляционный конструктор объектов</span><span class="sxs-lookup"><span data-stu-id="d4ebe-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="d4ebe-124">В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="d4ebe-125">Разверните **хранимых процедур** папки.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="d4ebe-126">Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="d4ebe-127">Щелкните **Sales by Year** хранимую процедуру и перетащите ее в правую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="d4ebe-128">Щелкните **десять самых дорогих продуктов** хранимой процедуры перетащите ее в правую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="d4ebe-129">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="d4ebe-130">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="d4ebe-131">Чтобы добавить код для отображения результатов хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="d4ebe-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="d4ebe-132">От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="d4ebe-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="d4ebe-133">Дважды щелкните Form1, чтобы добавить код для его `Load` события.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="d4ebe-134">При добавлении хранимых процедур в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект для проекта.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="d4ebe-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="d4ebe-135">Этот объект содержит код, который требуется для доступа к этим процедурам.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="d4ebe-136"><xref:System.Data.Linq.DataContext>Объект для присваивается имя на основе имени DBML-файл.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="d4ebe-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="d4ebe-137">Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="d4ebe-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="d4ebe-138">Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и вызывать методы хранимой процедуры, определяемой реляционный конструктор объектов.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="d4ebe-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="d4ebe-139">Для привязки к <xref:System.Windows.Forms.DataGridView>объекта, необходимо принудительно выполнить запрос немедленно путем вызова <xref:System.Linq.Enumerable.ToList%2A>метод результаты хранимой процедуры.</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="d4ebe-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="d4ebe-140">Добавьте следующий код в `Load` событий для вызова одной из процедур, предоставленных как методы в контексте данных.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     <span data-ttu-id="d4ebe-141">[!code-vb[VbLINQtoSQLHowTos&#1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d4ebe-141">[!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span></span>  
    <span data-ttu-id="d4ebe-142">[!code-vb[VbLINQtoSQLHowTos&#2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d4ebe-142">[!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span></span>  
  
4.  <span data-ttu-id="d4ebe-143">Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ebe-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d4ebe-144">See Also</span></span>  
 <span data-ttu-id="d4ebe-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4ebe-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="d4ebe-146"> [Запросы](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="d4ebe-146"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="d4ebe-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="d4ebe-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="d4ebe-148"> [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span><span class="sxs-lookup"><span data-stu-id="d4ebe-148"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span></span>  
<span data-ttu-id="d4ebe-149"> [Практическое руководство: назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span><span class="sxs-lookup"><span data-stu-id="d4ebe-149"> [How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span></span>

