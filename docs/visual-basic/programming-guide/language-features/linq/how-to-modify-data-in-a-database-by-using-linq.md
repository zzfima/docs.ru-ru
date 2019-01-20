---
title: Как выполнить Изменение данных в базе данных с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 1b957fb7524b7eaf46bf321713196e90bae66b6c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415212"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="e13a7-102">Как выполнить Изменение данных в базе данных с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e13a7-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e13a7-103">Запросы Language-Integrated Query (LINQ) упрощают доступ к данным базы данных и измените значения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e13a7-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="e13a7-104">В примере показан способ создания нового приложения, которое извлекает и обновляет сведения в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e13a7-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="e13a7-105">В примерах в этом разделе используется образец базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="e13a7-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e13a7-106">Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e13a7-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="e13a7-107">Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e13a7-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e13a7-108">Чтобы создать подключение к базе данных</span><span class="sxs-lookup"><span data-stu-id="e13a7-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="e13a7-109">В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **представление** меню, а затем выберите **обозревателя серверов** / **Проводника баз данных**.</span><span class="sxs-lookup"><span data-stu-id="e13a7-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="e13a7-110">Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных**и нажмите кнопку **добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="e13a7-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="e13a7-111">Укажите допустимое соединение с образцом базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="e13a7-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="e13a7-112">Добавление проекта с помощью LINQ to SQL-файл</span><span class="sxs-lookup"><span data-stu-id="e13a7-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="e13a7-113">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="e13a7-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e13a7-114">Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="e13a7-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="e13a7-115">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e13a7-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e13a7-116">Выберите **LINQ to SQL Classes** шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="e13a7-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="e13a7-117">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="e13a7-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e13a7-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e13a7-118">Click **Add**.</span></span> <span data-ttu-id="e13a7-119">Открывается реляционный конструктор объектов (O/R Designer) для `northwind.dbml` файла.</span><span class="sxs-lookup"><span data-stu-id="e13a7-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="e13a7-120">Чтобы добавить таблицы в запрос и изменение в конструктор</span><span class="sxs-lookup"><span data-stu-id="e13a7-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="e13a7-121">В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="e13a7-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e13a7-122">Разверните **таблиц** папки.</span><span class="sxs-lookup"><span data-stu-id="e13a7-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e13a7-123">Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув `northwind.dbml` файл, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="e13a7-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="e13a7-124">Щелкните таблицу Customers и перетащите его в левую область конструктора.</span><span class="sxs-lookup"><span data-stu-id="e13a7-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e13a7-125">Конструктор создает новый объект Customer для проекта.</span><span class="sxs-lookup"><span data-stu-id="e13a7-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="e13a7-126">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="e13a7-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="e13a7-127">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="e13a7-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="e13a7-128">Добавление кода для изменения базы данных и отображения результатов</span><span class="sxs-lookup"><span data-stu-id="e13a7-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="e13a7-129">Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="e13a7-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="e13a7-130">При добавлении таблиц в конструктор O/R designer добавлены <xref:System.Data.Linq.DataContext> объект в проект.</span><span class="sxs-lookup"><span data-stu-id="e13a7-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="e13a7-131">Этот объект содержит код, который можно использовать для доступа к таблице Customers.</span><span class="sxs-lookup"><span data-stu-id="e13a7-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="e13a7-132">Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы.</span><span class="sxs-lookup"><span data-stu-id="e13a7-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="e13a7-133"><xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml.</span><span class="sxs-lookup"><span data-stu-id="e13a7-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e13a7-134">Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="e13a7-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e13a7-135">Можно создать экземпляр <xref:System.Data.Linq.DataContext> объекта в коде и запрос и изменение коллекции клиентов, указанной в реляционный конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="e13a7-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="e13a7-136">Изменения, внесенные в коллекцию клиентов не отражаются в базе данных до их отправки, вызвав <xref:System.Data.Linq.DataContext.SubmitChanges%2A> метод <xref:System.Data.Linq.DataContext> объекта.</span><span class="sxs-lookup"><span data-stu-id="e13a7-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="e13a7-137">Дважды щелкните форму Windows, Form1, чтобы добавить код для <xref:System.Windows.Forms.Form.Load> событий для запроса, в таблице Customers, который предоставляется как свойство вашей <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="e13a7-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="e13a7-138">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e13a7-138">Add the following code:</span></span>  
  
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
  
3.  <span data-ttu-id="e13a7-139">Из **элементов**, перетащите три <xref:System.Windows.Forms.Button> элементов управления в форму.</span><span class="sxs-lookup"><span data-stu-id="e13a7-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="e13a7-140">Выберите первую `Button` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e13a7-140">Select the first `Button` control.</span></span> <span data-ttu-id="e13a7-141">В **свойства** окне `Name` из `Button` управления `AddButton` и `Text` для `Add`.</span><span class="sxs-lookup"><span data-stu-id="e13a7-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="e13a7-142">Выберите второй кнопки и задайте `Name` свойства `UpdateButton` и `Text` свойства `Update`.</span><span class="sxs-lookup"><span data-stu-id="e13a7-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="e13a7-143">Выберите третью кнопку и задайте `Name` свойства `DeleteButton` и `Text` свойства `Delete`.</span><span class="sxs-lookup"><span data-stu-id="e13a7-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="e13a7-144">Дважды щелкните **добавить** , чтобы добавить код для его `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="e13a7-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="e13a7-145">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e13a7-145">Add the following code:</span></span>  
  
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
  
5.  <span data-ttu-id="e13a7-146">Дважды щелкните **обновление** , чтобы добавить код для его `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="e13a7-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="e13a7-147">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e13a7-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="e13a7-148">Дважды щелкните **удалить** , чтобы добавить код для его `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="e13a7-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="e13a7-149">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e13a7-149">Add the following code:</span></span>  
  
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
  
7.  <span data-ttu-id="e13a7-150">Нажмите клавишу F5 для запуска проекта.</span><span class="sxs-lookup"><span data-stu-id="e13a7-150">Press F5 to run your project.</span></span> <span data-ttu-id="e13a7-151">Нажмите кнопку **добавить** для добавления новой записи.</span><span class="sxs-lookup"><span data-stu-id="e13a7-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="e13a7-152">Нажмите кнопку **обновления** изменение новой записи.</span><span class="sxs-lookup"><span data-stu-id="e13a7-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="e13a7-153">Нажмите кнопку **удалить** для удаления новой записи.</span><span class="sxs-lookup"><span data-stu-id="e13a7-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13a7-154">См. также</span><span class="sxs-lookup"><span data-stu-id="e13a7-154">See Also</span></span>  
 [<span data-ttu-id="e13a7-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="e13a7-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="e13a7-156">Запросы</span><span class="sxs-lookup"><span data-stu-id="e13a7-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="e13a7-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e13a7-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="e13a7-158">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="e13a7-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="e13a7-159">Практическое руководство. Назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="e13a7-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](https://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
