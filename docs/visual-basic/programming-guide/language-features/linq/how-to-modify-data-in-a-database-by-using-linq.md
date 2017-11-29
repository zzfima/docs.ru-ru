---
title: "Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c491825d8fcacb9852584e7934682598441c2bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="0f4d2-102">Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f4d2-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="0f4d2-103">Запросы LINQ запросы (LINQ) упрощают доступ к данным базы данных, а также изменять значения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="0f4d2-104">В следующем примере показано создание нового приложения, которое получает и обновляет сведения в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="0f4d2-105">Примеры в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="0f4d2-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="0f4d2-106">Если у вас образца базы данных "Борей" на компьютере разработчика, его можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="0f4d2-107">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="0f4d2-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="0f4d2-108">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="0f4d2-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="0f4d2-109">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **представление** меню, а затем выберите **обозревателя серверов** / **Проводника баз данных**.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="0f4d2-110">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных**и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="0f4d2-111">Укажите допустимое подключение к учебной базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="0f4d2-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="0f4d2-112">Чтобы добавить проект с LINQ to SQL-файл</span><span class="sxs-lookup"><span data-stu-id="0f4d2-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="0f4d2-113">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="0f4d2-114">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="0f4d2-115">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="0f4d2-116">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="0f4d2-117">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="0f4d2-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-118">Click **Add**.</span></span> <span data-ttu-id="0f4d2-119">Реляционный конструктор объектов (O/R-конструктор) открыт для `northwind.dbml` файла.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="0f4d2-120">Добавление таблицы к запросу и изменить в конструкторе</span><span class="sxs-lookup"><span data-stu-id="0f4d2-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="0f4d2-121">В **обозревателя серверов**/**обозревателя базы данных**, разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="0f4d2-122">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="0f4d2-123">Если O/R-конструктор закрыт, его можно открыть, дважды щелкнув `northwind.dbml` файл, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="0f4d2-124">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="0f4d2-125">Конструктор создает новый объект Customer для проекта.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="0f4d2-126">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="0f4d2-127">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="0f4d2-128">Чтобы добавить код для изменения базы данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="0f4d2-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="0f4d2-129">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> на форме Windows Forms по умолчанию для проекта, Form1 элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="0f4d2-130">При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объекта к проекту.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="0f4d2-131">Этот объект содержит код, который можно использовать для доступа к таблице Customers.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="0f4d2-132">Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="0f4d2-133"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="0f4d2-134">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="0f4d2-135">Можно создать экземпляр <xref:System.Data.Linq.DataContext> объекта в коде и запросов и изменение коллекции клиентов, указанной в реляционный конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="0f4d2-136">Изменения, внесенные в коллекцию Customers, не отражаются в базе данных до их отправки, вызвав <xref:System.Data.Linq.DataContext.SubmitChanges%2A> метод <xref:System.Data.Linq.DataContext> объекта.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="0f4d2-137">Дважды щелкните Windows форму Form1, чтобы добавить код для <xref:System.Windows.Forms.Form.Load> событий для запросов в таблице Customers, который предоставляется как свойство вашей <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="0f4d2-138">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0f4d2-138">Add the following code:</span></span>  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  <span data-ttu-id="0f4d2-139">Из **элементов**, перетащите три <xref:System.Windows.Forms.Button> элементов управления в форму.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="0f4d2-140">Выберите первую `Button` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-140">Select the first `Button` control.</span></span> <span data-ttu-id="0f4d2-141">В **свойства** задайте `Name` из `Button` управления `AddButton` и `Text` для `Add`.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="0f4d2-142">Выберите вторую кнопку и задайте `Name` свойства `UpdateButton` и `Text` свойства `Update`.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="0f4d2-143">Выберите третий кнопку и задайте `Name` свойства `DeleteButton` и `Text` свойства `Delete`.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="0f4d2-144">Дважды щелкните **добавить** кнопку, чтобы добавить код, чтобы его `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="0f4d2-145">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0f4d2-145">Add the following code:</span></span>  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  <span data-ttu-id="0f4d2-146">Дважды щелкните **обновление** кнопку, чтобы добавить код, чтобы его `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="0f4d2-147">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0f4d2-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="0f4d2-148">Дважды щелкните **удаление** кнопку, чтобы добавить код, чтобы его `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="0f4d2-149">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0f4d2-149">Add the following code:</span></span>  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  <span data-ttu-id="0f4d2-150">Нажмите клавишу F5 для запуска проекта.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-150">Press F5 to run your project.</span></span> <span data-ttu-id="0f4d2-151">Нажмите кнопку **добавить** для добавления новой записи.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="0f4d2-152">Нажмите кнопку **обновление** для изменения новой записи.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="0f4d2-153">Нажмите кнопку **удаление** для удаления новой записи.</span><span class="sxs-lookup"><span data-stu-id="0f4d2-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4d2-154">См. также</span><span class="sxs-lookup"><span data-stu-id="0f4d2-154">See Also</span></span>  
 [<span data-ttu-id="0f4d2-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="0f4d2-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="0f4d2-156">Запросы</span><span class="sxs-lookup"><span data-stu-id="0f4d2-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="0f4d2-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0f4d2-157">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="0f4d2-158">Методы DataContext (O/R-конструктор)</span><span class="sxs-lookup"><span data-stu-id="0f4d2-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="0f4d2-159">Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)</span><span class="sxs-lookup"><span data-stu-id="0f4d2-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
