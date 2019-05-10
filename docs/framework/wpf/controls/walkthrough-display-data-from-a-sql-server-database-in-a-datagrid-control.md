---
title: Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 8f17d16ecc4255356ec51b152223ef32c1c81968
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665199"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="32c0c-102">Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="32c0c-102">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="32c0c-103">В этом пошаговом руководстве, получения данных из базы данных SQL Server и отображение их в <xref:System.Windows.Controls.DataGrid> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="32c0c-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="32c0c-104">Использовать ADO.NET Entity Framework для создания классов сущностей, которые представляют данные и использовать LINQ для записи запроса, который получает указанные данные из класса сущностей.</span><span class="sxs-lookup"><span data-stu-id="32c0c-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32c0c-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="32c0c-105">Prerequisites</span></span>

<span data-ttu-id="32c0c-106">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="32c0c-106">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="32c0c-107">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="32c0c-107">Visual Studio.</span></span>

- <span data-ttu-id="32c0c-108">Доступ к запущенному экземпляру SQL Server или SQL Server Express с образца базы данных AdventureWorks, подключенные к ней.</span><span class="sxs-lookup"><span data-stu-id="32c0c-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="32c0c-109">Можно загрузить из базы данных AdventureWorks [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="32c0c-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="32c0c-110">Создайте классы сущностей</span><span class="sxs-lookup"><span data-stu-id="32c0c-110">Create entity classes</span></span>

1. <span data-ttu-id="32c0c-111">Создайте новый проект приложения WPF в Visual Basic или C# и назовите его `DataGridSQLExample`.</span><span class="sxs-lookup"><span data-stu-id="32c0c-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="32c0c-112">В обозревателе решений щелкните правой кнопкой мыши проект, выберите пункт **добавить**, а затем выберите **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="32c0c-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="32c0c-113">Будет открыто диалоговое окно Добавление нового элемента.</span><span class="sxs-lookup"><span data-stu-id="32c0c-113">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="32c0c-114">На панели "Установленные шаблоны", выберите **данных** и в списке шаблонов выберите **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="32c0c-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![Шаблон элемента модели EDM ADO.NET](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="32c0c-116">Назовите файл `AdventureWorksModel.edmx` и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="32c0c-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="32c0c-117">Появится мастер модели EDM.</span><span class="sxs-lookup"><span data-stu-id="32c0c-117">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="32c0c-118">На экране «Выбор содержимого модели» выберите **конструктор EF из базы данных** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="32c0c-118">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="32c0c-119">На экране «Выбор подключения к данным» обеспечивают подключение к базе данных AdventureWorksLT2008.</span><span class="sxs-lookup"><span data-stu-id="32c0c-119">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="32c0c-120">Дополнительные сведения см. в разделе [выберите Your данных диалогового окна соединения](https://go.microsoft.com/fwlink/?LinkId=160190).</span><span class="sxs-lookup"><span data-stu-id="32c0c-120">For more information, see [Choose Your Data Connection Dialog Box](https://go.microsoft.com/fwlink/?LinkId=160190).</span></span>

    <span data-ttu-id="32c0c-121">Убедитесь, что имя указано `AdventureWorksLT2008Entities` и что **сохранить настройки подключения сущности в App.Config как** флажок выбран и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="32c0c-121">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="32c0c-122">На экране «Выбор объектов базы данных» разверните узел таблицы и выберите **продукта** и **ProductCategory** таблиц.</span><span class="sxs-lookup"><span data-stu-id="32c0c-122">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="32c0c-123">Можно создавать классы сущностей для всех таблиц; Тем не менее в этом примере извлекаются данные только из этих двух таблиц.</span><span class="sxs-lookup"><span data-stu-id="32c0c-123">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="32c0c-124">![Выбор пунктов Product и ProductCategory из таблиц](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="32c0c-124">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="32c0c-125">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="32c0c-125">Click **Finish**.</span></span>

     <span data-ttu-id="32c0c-126">Сущности Product и ProductCategory, отображаются в конструкторе сущностей.</span><span class="sxs-lookup"><span data-stu-id="32c0c-126">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="32c0c-127">![Модели сущностей Product и ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="32c0c-127">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="32c0c-128">Извлечение и представление данных</span><span class="sxs-lookup"><span data-stu-id="32c0c-128">Retrieve and present the data</span></span>

1. <span data-ttu-id="32c0c-129">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="32c0c-129">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="32c0c-130">Задайте <xref:System.Windows.FrameworkElement.Width%2A> свойство <xref:System.Windows.Window> для 450.</span><span class="sxs-lookup"><span data-stu-id="32c0c-130">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="32c0c-131">В редакторе XAML добавьте следующий <xref:System.Windows.Controls.DataGrid> тег между `<Grid>` и `</Grid>` теги для добавления <xref:System.Windows.Controls.DataGrid> с именем `dataGrid1`.</span><span class="sxs-lookup"><span data-stu-id="32c0c-131">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="32c0c-132">![Окно с DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="32c0c-132">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="32c0c-133">Выберите <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="32c0c-133">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="32c0c-134">С помощью окна свойств или редактор XAML, создайте обработчик событий для <xref:System.Windows.Window> с именем `Window_Loaded` для <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="32c0c-134">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="32c0c-135">Дополнительные сведения см. в разделе [Как Создание простого обработчика событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="32c0c-135">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="32c0c-136">Ниже показан XAML для MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="32c0c-136">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32c0c-137">Если вы используете Visual Basic, в первой строке файла MainWindow.XAML, замените `x:Class="DataGridSQLExample.MainWindow"` с `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="32c0c-137">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="32c0c-138">Откройте файл с выделенным кодом (MainWindow.xaml.vb или MainWindow.xaml.cs) для <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="32c0c-138">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="32c0c-139">Добавьте следующий код, чтобы получить только определенные значения из соединяемых таблиц и задать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.DataGrid> к результатам запроса.</span><span class="sxs-lookup"><span data-stu-id="32c0c-139">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="32c0c-140">Запустите пример.</span><span class="sxs-lookup"><span data-stu-id="32c0c-140">Run the example.</span></span>

     <span data-ttu-id="32c0c-141">Вы должны увидеть <xref:System.Windows.Controls.DataGrid> , отображающий данные.</span><span class="sxs-lookup"><span data-stu-id="32c0c-141">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="32c0c-142">![DataGrid с данными из базы данных SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="32c0c-142">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="32c0c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="32c0c-143">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="32c0c-144">Инструкции: Начало работы с Entity Framework в приложениях WPF?</span><span class="sxs-lookup"><span data-stu-id="32c0c-144">How Do I: Get Started with Entity Framework in WPF Applications?</span></span>](https://go.microsoft.com/fwlink/?LinkId=159868)