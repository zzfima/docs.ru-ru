---
title: Инструкции. изменение данных в базе данных с помощью LINQ
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
ms.openlocfilehash: 9a10efef5ae92dd21888594ae80a3fc07869a8c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344948"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="f0f42-102">Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0f42-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="f0f42-103">Запросы LINQ позволяют легко получить доступ к сведениям о базе данных и изменить значения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f0f42-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>

<span data-ttu-id="f0f42-104">В следующем примере показано, как создать новое приложение, которое извлекает и обновляет сведения в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f0f42-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>

<span data-ttu-id="f0f42-105">В примерах этого раздела используется учебная база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f0f42-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="f0f42-106">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0f42-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="f0f42-107">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f0f42-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="f0f42-108">Создание соединения с базой данных</span><span class="sxs-lookup"><span data-stu-id="f0f42-108">To create a connection to a database</span></span>

1. <span data-ttu-id="f0f42-109">В Visual Studio откройте **обозреватель сервера**/**Обозреватель базы данных** , выбрав в меню **вид** пункт **Обозреватель сервера**/**Обозреватель базы данных**.</span><span class="sxs-lookup"><span data-stu-id="f0f42-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>

2. <span data-ttu-id="f0f42-110">Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных**и выберите команду **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="f0f42-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>

3. <span data-ttu-id="f0f42-111">Укажите допустимое соединение с образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f0f42-111">Specify a valid connection to the Northwind sample database.</span></span>

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="f0f42-112">Добавление проекта с файлом LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f0f42-112">To add a Project with a LINQ to SQL file</span></span>

1. <span data-ttu-id="f0f42-113">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="f0f42-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="f0f42-114">Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="f0f42-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="f0f42-115">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="f0f42-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="f0f42-116">Выберите шаблон элемента **LINQ to SQL классы** .</span><span class="sxs-lookup"><span data-stu-id="f0f42-116">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="f0f42-117">Назовите файл `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="f0f42-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f0f42-118">Click **Add**.</span></span> <span data-ttu-id="f0f42-119">Для файла `northwind.dbml` открыт реляционный конструктор объектов (реляционный конструктор R).</span><span class="sxs-lookup"><span data-stu-id="f0f42-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="f0f42-120">Добавление таблиц к запросам и их изменение в конструкторе</span><span class="sxs-lookup"><span data-stu-id="f0f42-120">To add tables to query and modify to the designer</span></span>

1. <span data-ttu-id="f0f42-121">В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f0f42-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="f0f42-122">Разверните папку **таблицы** .</span><span class="sxs-lookup"><span data-stu-id="f0f42-122">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="f0f42-123">Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл `northwind.dbml`, который был добавлен ранее.</span><span class="sxs-lookup"><span data-stu-id="f0f42-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>

2. <span data-ttu-id="f0f42-124">Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.</span><span class="sxs-lookup"><span data-stu-id="f0f42-124">Click the Customers table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="f0f42-125">Конструктор создает новый объект Customer для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="f0f42-125">The designer creates a new Customer object for your project.</span></span>

3. <span data-ttu-id="f0f42-126">Сохраните изменения и закройте конструктор.</span><span class="sxs-lookup"><span data-stu-id="f0f42-126">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="f0f42-127">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="f0f42-127">Save your project.</span></span>

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="f0f42-128">Добавление кода для изменения базы данных и вывода результатов</span><span class="sxs-lookup"><span data-stu-id="f0f42-128">To add code to modify the database and display the results</span></span>

1. <span data-ttu-id="f0f42-129">Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.</span><span class="sxs-lookup"><span data-stu-id="f0f42-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="f0f42-130">При добавлении таблиц в реляционный конструктор объектов конструктор добавил в проект объект <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="f0f42-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="f0f42-131">Этот объект содержит код, который можно использовать для доступа к таблице Customers.</span><span class="sxs-lookup"><span data-stu-id="f0f42-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="f0f42-132">Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы.</span><span class="sxs-lookup"><span data-stu-id="f0f42-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="f0f42-133">Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="f0f42-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="f0f42-134">Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

     <span data-ttu-id="f0f42-135">Можно создать экземпляр объекта <xref:System.Data.Linq.DataContext> в коде и запросить и изменить коллекцию Customers, указанную в конструкторе O/R.</span><span class="sxs-lookup"><span data-stu-id="f0f42-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="f0f42-136">Изменения, вносимые в коллекцию Customers, не отражаются в базе данных, пока они не будут отправлены путем вызова метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="f0f42-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>

     <span data-ttu-id="f0f42-137">Дважды щелкните форму Windows Forms, форму Form1, чтобы добавить код в событие <xref:System.Windows.Forms.Form.Load>, чтобы запросить таблицу Customers, доступную в качестве свойства <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="f0f42-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="f0f42-138">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f0f42-138">Add the following code:</span></span>

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

3. <span data-ttu-id="f0f42-139">Перетащите на форму три элемента управления <xref:System.Windows.Forms.Button> из **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="f0f42-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="f0f42-140">Выберите первый элемент управления `Button`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-140">Select the first `Button` control.</span></span> <span data-ttu-id="f0f42-141">В окне **Свойства** задайте для `Name` элемента управления `Button` значение `AddButton` а `Text` — `Add`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="f0f42-142">Нажмите вторую кнопку и задайте для свойства `Name` значение `UpdateButton` а свойству `Text` — значение `Update`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="f0f42-143">Нажмите третью кнопку и задайте для свойства `Name` значение `DeleteButton` а свойству `Text` — значение `Delete`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>

4. <span data-ttu-id="f0f42-144">Дважды щелкните кнопку **Добавить** , чтобы добавить код к событию `Click`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="f0f42-145">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f0f42-145">Add the following code:</span></span>

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

5. <span data-ttu-id="f0f42-146">Дважды щелкните кнопку " **Обновить** ", чтобы добавить код к событию `Click`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="f0f42-147">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f0f42-147">Add the following code:</span></span>

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

6. <span data-ttu-id="f0f42-148">Дважды щелкните кнопку **Удалить** , чтобы добавить код к событию `Click`.</span><span class="sxs-lookup"><span data-stu-id="f0f42-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="f0f42-149">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f0f42-149">Add the following code:</span></span>

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

7. <span data-ttu-id="f0f42-150">Нажмите клавишу F5 для запуска проекта.</span><span class="sxs-lookup"><span data-stu-id="f0f42-150">Press F5 to run your project.</span></span> <span data-ttu-id="f0f42-151">Нажмите кнопку **Добавить** , чтобы добавить новую запись.</span><span class="sxs-lookup"><span data-stu-id="f0f42-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="f0f42-152">Нажмите кнопку **Обновить** , чтобы изменить новую запись.</span><span class="sxs-lookup"><span data-stu-id="f0f42-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="f0f42-153">Нажмите кнопку **Удалить** , чтобы удалить новую запись.</span><span class="sxs-lookup"><span data-stu-id="f0f42-153">Click **Delete** to delete the new record.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0f42-154">См. также</span><span class="sxs-lookup"><span data-stu-id="f0f42-154">See also</span></span>

- [<span data-ttu-id="f0f42-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="f0f42-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="f0f42-156">Запросы</span><span class="sxs-lookup"><span data-stu-id="f0f42-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="f0f42-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f0f42-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="f0f42-158">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="f0f42-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="f0f42-159">Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="f0f42-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
