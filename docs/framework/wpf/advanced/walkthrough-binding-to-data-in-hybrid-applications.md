---
title: Пошаговое руководство. Привязка к данным в гибридных приложениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: ef5f14cdbecab8bc780cb7b2a642429970a25316
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972280"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="b8ba2-102">Пошаговое руководство. Привязка к данным в гибридных приложениях</span><span class="sxs-lookup"><span data-stu-id="b8ba2-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="b8ba2-103">Привязка источника данных к элементу управления необходима для предоставления пользователям доступа к базовым данным независимо от того, используется [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8ba2-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="b8ba2-104">В этом пошаговом руководстве показано, как можно использовать привязку данных в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] гибридных приложениях, включающих как элементы управления, так и. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8ba2-104">This walkthrough shows how you can use data binding in hybrid applications that include both [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="b8ba2-105">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="b8ba2-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-106">Creating the project.</span></span>

- <span data-ttu-id="b8ba2-107">Определение шаблона данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-107">Defining the data template.</span></span>

- <span data-ttu-id="b8ba2-108">Задание макета формы.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-108">Specifying the form layout.</span></span>

- <span data-ttu-id="b8ba2-109">Задание привязок данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-109">Specifying data bindings.</span></span>

- <span data-ttu-id="b8ba2-110">Отображение данных с помощью взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="b8ba2-111">Добавление источника данных в проект.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="b8ba2-112">Подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-112">Binding to the data source.</span></span>

<span data-ttu-id="b8ba2-113">Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Пример привязки данных в гибридных приложениях](https://go.microsoft.com/fwlink/?LinkID=159983).</span><span class="sxs-lookup"><span data-stu-id="b8ba2-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span></span>

<span data-ttu-id="b8ba2-114">Изучив этот раздел, вы будете иметь представление о функциях привязки данных в гибридных приложениях.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8ba2-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b8ba2-115">Prerequisites</span></span>

<span data-ttu-id="b8ba2-116">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="b8ba2-117">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-117">Visual Studio.</span></span>

- <span data-ttu-id="b8ba2-118">Доступ к учебной базе данных Northwind, выполняемой на Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="b8ba2-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="b8ba2-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="b8ba2-120">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="b8ba2-120">To create and set up the project</span></span>

1. <span data-ttu-id="b8ba2-121">Создайте проект приложения WPF с именем `WPFWithWFAndDatabinding`.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="b8ba2-122">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="b8ba2-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="b8ba2-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="b8ba2-124">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="b8ba2-125">Откройте файл MainWindow. XAML в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8ba2-125">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

4. <span data-ttu-id="b8ba2-126">В элементе добавьте следующее [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространств имен. <xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="b8ba2-126">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="b8ba2-127">Присвойте <xref:System.Windows.Controls.Grid> элементу `mainGrid` имя по умолчанию, назначив <xref:System.Windows.FrameworkElement.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="b8ba2-128">Определение шаблона данных</span><span class="sxs-lookup"><span data-stu-id="b8ba2-128">Defining the Data Template</span></span>

<span data-ttu-id="b8ba2-129">Главный список клиентов отображается в <xref:System.Windows.Controls.ListBox> элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="b8ba2-130">В следующем примере кода определяется <xref:System.Windows.DataTemplate> объект с именем `ListItemsTemplate` , который управляет визуальным деревом <xref:System.Windows.Controls.ListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="b8ba2-131">Это <xref:System.Windows.DataTemplate> значение присваивается <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойству элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="b8ba2-132">Чтобы определить шаблон данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-132">To define the data template</span></span>

- <span data-ttu-id="b8ba2-133">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="b8ba2-134">Задание макета формы</span><span class="sxs-lookup"><span data-stu-id="b8ba2-134">Specifying the Form Layout</span></span>

<span data-ttu-id="b8ba2-135">Макет формы определяется сеткой с тремя строками и тремя столбцами.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="b8ba2-136"><xref:System.Windows.Controls.Label>для поиска каждого столбца в таблице Customers предусмотрены элементы управления.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="b8ba2-137">Настройка макета сетки</span><span class="sxs-lookup"><span data-stu-id="b8ba2-137">To set up the Grid layout</span></span>

- <span data-ttu-id="b8ba2-138">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="b8ba2-139">Чтобы настроить элементы управления Label, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-139">To set up the Label controls</span></span>

- <span data-ttu-id="b8ba2-140">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="b8ba2-141">Задание привязок данных</span><span class="sxs-lookup"><span data-stu-id="b8ba2-141">Specifying Data Bindings</span></span>

<span data-ttu-id="b8ba2-142">Главный список клиентов отображается в <xref:System.Windows.Controls.ListBox> элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="b8ba2-143">Присоединенная `ListItemsTemplate` привязка привязывает <xref:System.Windows.Controls.TextBlock> элемент управления к `ContactName` полю из базы данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="b8ba2-144">Сведения о каждой записи клиента отображаются в нескольких <xref:System.Windows.Controls.TextBox> элементах управления.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="b8ba2-145">Чтобы задать привязки данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-145">To specify data bindings</span></span>

- <span data-ttu-id="b8ba2-146">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="b8ba2-147">Класс привязывает <xref:System.Windows.Controls.TextBox> элементы управления к соответствующим полям в базе данных. <xref:System.Windows.Data.Binding></span><span class="sxs-lookup"><span data-stu-id="b8ba2-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="b8ba2-148">Отображение данных с помощью взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b8ba2-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="b8ba2-149">Заказы, соответствующие выбранному клиенту, отображаются в <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> элементе управления с именем. `dataGridView1`</span><span class="sxs-lookup"><span data-stu-id="b8ba2-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="b8ba2-150">`dataGridView1` Элемент управления привязан к источнику данных в файле кода программной части.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="b8ba2-151">Элемент управления является родительским для этого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления. <xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="b8ba2-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="b8ba2-152">Чтобы отобразить данные в элементе управления DataGridView, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="b8ba2-153">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="b8ba2-154">Добавление источника данных в проект</span><span class="sxs-lookup"><span data-stu-id="b8ba2-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="b8ba2-155">С помощью Visual Studio можно легко добавить в проект источник данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="b8ba2-156">Эта процедура добавляет строго типизированный набор данных в ваш проект.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="b8ba2-157">Также добавляется несколько других классов поддержки, таких как адаптеры таблиц для каждой из выбранных таблиц.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="b8ba2-158">Добавление источника данных</span><span class="sxs-lookup"><span data-stu-id="b8ba2-158">To add the data source</span></span>

1. <span data-ttu-id="b8ba2-159">В меню **данные** выберите команду **Добавить новый источник данных**.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="b8ba2-160">В **мастере настройки источника данных**создайте подключение к базе данных Northwind с помощью набора данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="b8ba2-161">Дополнительные сведения см. в разделе [Практическое руководство. Подключение к данным в базе данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="b8ba2-161">For more information, see [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="b8ba2-162">При появлении запроса в **мастере настройки источника данных**сохраните строку подключения как `NorthwindConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="b8ba2-163">Когда появится запрос на выбор объектов базы данных, выберите `Customers` таблицы и `Orders` и назовите созданный набор `NorthwindDataSet`данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="b8ba2-164">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="b8ba2-164">Binding to the Data Source</span></span>

<span data-ttu-id="b8ba2-165"><xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Компонент предоставляет единый интерфейс для источника данных приложения.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="b8ba2-166">Привязка к источнику данных реализована в файле кода программной части.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="b8ba2-167">Чтобы создать привязку к источнику данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-167">To bind to the data source</span></span>

1. <span data-ttu-id="b8ba2-168">Откройте файл кода программной части с именем MainWindow.xaml.vb или MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="b8ba2-169">Скопируйте следующий код в `MainWindow` определение класса.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="b8ba2-170">Этот код объявляет <xref:System.Windows.Forms.BindingSource> компонент и связанные вспомогательные классы, подключающиеся к базе данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="b8ba2-171">Копируйте в конструктор следующий код.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="b8ba2-172">Этот код создает и инициализирует <xref:System.Windows.Forms.BindingSource> компонент.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="b8ba2-173">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="b8ba2-174">В представление конструирования или представлении XAML выберите <xref:System.Windows.Window> элемент.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="b8ba2-175">В окно свойств перейдите на вкладку **события** .</span><span class="sxs-lookup"><span data-stu-id="b8ba2-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="b8ba2-176">Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событие.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="b8ba2-177">Скопируйте следующий код в <xref:System.Windows.FrameworkElement.Loaded> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="b8ba2-178">Этот код назначает <xref:System.Windows.Forms.BindingSource> компонент в качестве контекста данных и заполняет `Customers` объекты адаптера и `Orders` .</span><span class="sxs-lookup"><span data-stu-id="b8ba2-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="b8ba2-179">Скопируйте следующий код в `MainWindow` определение класса.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="b8ba2-180">Этот метод обрабатывает <xref:System.Windows.Data.CollectionView.CurrentChanged> событие и обновляет текущий элемент привязки данных.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="b8ba2-181">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8ba2-182">См. также</span><span class="sxs-lookup"><span data-stu-id="b8ba2-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b8ba2-183">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8ba2-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="b8ba2-184">Пример привязки данных в гибридных приложениях</span><span class="sxs-lookup"><span data-stu-id="b8ba2-184">Data Binding in Hybrid Applications Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159983)
- [<span data-ttu-id="b8ba2-185">Пошаговое руководство: Размещение составного элемента управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="b8ba2-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="b8ba2-186">Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8ba2-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
