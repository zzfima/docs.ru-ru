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
ms.openlocfilehash: 7128b23790588a604989cb18918a7a7e8b598191
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584226"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="35d55-102">Пошаговое руководство. Привязка к данным в гибридных приложениях</span><span class="sxs-lookup"><span data-stu-id="35d55-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>
<span data-ttu-id="35d55-103">Привязка источника данных к элементу управления необходима для предоставления пользователям доступа к базовым данным независимо от используемой [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35d55-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="35d55-104">В этом пошаговом руководстве показано, как можно использовать привязку данных в гибридных приложениях, которые включают [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления.</span><span class="sxs-lookup"><span data-stu-id="35d55-104">This walkthrough shows how you can use data binding in hybrid applications that include both [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>  
  
 <span data-ttu-id="35d55-105">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="35d55-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="35d55-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="35d55-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="35d55-107">Определение шаблона данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-107">Defining the data template.</span></span>  
  
-   <span data-ttu-id="35d55-108">Задание макета формы.</span><span class="sxs-lookup"><span data-stu-id="35d55-108">Specifying the form layout.</span></span>  
  
-   <span data-ttu-id="35d55-109">Задание привязок данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-109">Specifying data bindings.</span></span>  
  
-   <span data-ttu-id="35d55-110">Отображение данных с помощью взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="35d55-110">Displaying data by using interoperation.</span></span>  
  
-   <span data-ttu-id="35d55-111">Добавление источника данных в проект.</span><span class="sxs-lookup"><span data-stu-id="35d55-111">Adding the data source to the project.</span></span>  
  
-   <span data-ttu-id="35d55-112">Подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-112">Binding to the data source.</span></span>  
  
 <span data-ttu-id="35d55-113">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. в разделе [привязка данных в гибридных приложениях-пример](https://go.microsoft.com/fwlink/?LinkID=159983).</span><span class="sxs-lookup"><span data-stu-id="35d55-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span></span>  
  
 <span data-ttu-id="35d55-114">Изучив этот раздел, вы будете иметь представление о функциях привязки данных в гибридных приложениях.</span><span class="sxs-lookup"><span data-stu-id="35d55-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="35d55-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="35d55-115">Prerequisites</span></span>  
 <span data-ttu-id="35d55-116">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="35d55-116">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="35d55-117">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="35d55-117">Visual Studio.</span></span>  
  
-   <span data-ttu-id="35d55-118">Доступ к базе данных Northwind на сервере Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35d55-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="35d55-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="35d55-119">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="35d55-120">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="35d55-120">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="35d55-121">Создание проекта приложения WPF с именем `WPFWithWFAndDatabinding`.</span><span class="sxs-lookup"><span data-stu-id="35d55-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>  
  
2.  <span data-ttu-id="35d55-122">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="35d55-122">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="35d55-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="35d55-123">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="35d55-124">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="35d55-124">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="35d55-125">Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35d55-125">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="35d55-126">В <xref:System.Windows.Window> элемента, добавьте следующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространств имен.</span><span class="sxs-lookup"><span data-stu-id="35d55-126">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespaces mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="35d55-127">По умолчанию имя <xref:System.Windows.Controls.Grid> элемент `mainGrid` , назначив <xref:System.Windows.FrameworkElement.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="35d55-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a><span data-ttu-id="35d55-128">Определение шаблона данных</span><span class="sxs-lookup"><span data-stu-id="35d55-128">Defining the Data Template</span></span>  
 <span data-ttu-id="35d55-129">Основной список клиентов отображается в <xref:System.Windows.Controls.ListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="35d55-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="35d55-130">В следующем примере кода определяется <xref:System.Windows.DataTemplate> объект с именем `ListItemsTemplate` визуальное дерево элемента, который управляет <xref:System.Windows.Controls.ListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="35d55-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="35d55-131">Это <xref:System.Windows.DataTemplate> назначается <xref:System.Windows.Controls.ListBox> элемента управления <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="35d55-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>  
  
#### <a name="to-define-the-data-template"></a><span data-ttu-id="35d55-132">Чтобы определить шаблон данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="35d55-132">To define the data template</span></span>  
  
-   <span data-ttu-id="35d55-133">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="35d55-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a><span data-ttu-id="35d55-134">Задание макета формы</span><span class="sxs-lookup"><span data-stu-id="35d55-134">Specifying the Form Layout</span></span>  
 <span data-ttu-id="35d55-135">Макет формы определяется сеткой с тремя строками и тремя столбцами.</span><span class="sxs-lookup"><span data-stu-id="35d55-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="35d55-136"><xref:System.Windows.Controls.Label> элементы управления предоставляются для идентификации каждого столбца в таблице Customers.</span><span class="sxs-lookup"><span data-stu-id="35d55-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>  
  
#### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="35d55-137">Настройка макета сетки</span><span class="sxs-lookup"><span data-stu-id="35d55-137">To set up the Grid layout</span></span>  
  
-   <span data-ttu-id="35d55-138">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="35d55-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="35d55-139">Чтобы настроить элементы управления Label, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="35d55-139">To set up the Label controls</span></span>  
  
-   <span data-ttu-id="35d55-140">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="35d55-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a><span data-ttu-id="35d55-141">Задание привязок данных</span><span class="sxs-lookup"><span data-stu-id="35d55-141">Specifying Data Bindings</span></span>  
 <span data-ttu-id="35d55-142">Основной список клиентов отображается в <xref:System.Windows.Controls.ListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="35d55-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="35d55-143">Вложенный `ListItemsTemplate` привязывает <xref:System.Windows.Controls.TextBlock> управления `ContactName` поля из базы данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>  
  
 <span data-ttu-id="35d55-144">Сведения о каждой записи клиента отображаются в нескольких <xref:System.Windows.Controls.TextBox> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="35d55-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>  
  
#### <a name="to-specify-data-bindings"></a><span data-ttu-id="35d55-145">Чтобы задать привязки данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="35d55-145">To specify data bindings</span></span>  
  
-   <span data-ttu-id="35d55-146">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="35d55-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     <span data-ttu-id="35d55-147"><xref:System.Windows.Data.Binding> Класса привязки <xref:System.Windows.Controls.TextBox> элементов управления к соответствующим полям в базе данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="35d55-148">Отображение данных с помощью взаимодействия</span><span class="sxs-lookup"><span data-stu-id="35d55-148">Displaying Data by Using Interoperation</span></span>  
 <span data-ttu-id="35d55-149">Заказы, соответствующие выбранному клиенту, отображаются в <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> управления с именем `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="35d55-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="35d55-150">`dataGridView1` Привязке элемента управления к источнику данных в файле кода.</span><span class="sxs-lookup"><span data-stu-id="35d55-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="35d55-151">Объект <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент управления является родительский элемент данного [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="35d55-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="35d55-152">Чтобы отобразить данные в элементе управления DataGridView, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="35d55-152">To display data in the DataGridView control</span></span>  
  
-   <span data-ttu-id="35d55-153">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> объявление элемента.</span><span class="sxs-lookup"><span data-stu-id="35d55-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="35d55-154">Добавление источника данных в проект</span><span class="sxs-lookup"><span data-stu-id="35d55-154">Adding the Data Source to the Project</span></span>  
 <span data-ttu-id="35d55-155">С помощью Visual Studio можно легко добавить источник данных в проект.</span><span class="sxs-lookup"><span data-stu-id="35d55-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="35d55-156">Эта процедура добавляет строго типизированный набор данных в ваш проект.</span><span class="sxs-lookup"><span data-stu-id="35d55-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="35d55-157">Также добавляется несколько других классов поддержки, таких как адаптеры таблиц для каждой из выбранных таблиц.</span><span class="sxs-lookup"><span data-stu-id="35d55-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="35d55-158">Добавление источника данных</span><span class="sxs-lookup"><span data-stu-id="35d55-158">To add the data source</span></span>  
  
1.  <span data-ttu-id="35d55-159">Из **данных** меню, выберите **добавить новый источник данных**.</span><span class="sxs-lookup"><span data-stu-id="35d55-159">From the **Data** menu, select **Add New Data Source**.</span></span>  
  
2.  <span data-ttu-id="35d55-160">В **мастер настройки источника данных**, создать подключение к базе данных "Борей" с помощью набора данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="35d55-161">Дополнительные сведения см. в разделе [как: подключение к данным в базе данных](https://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).</span><span class="sxs-lookup"><span data-stu-id="35d55-161">For more information, see [How to: Connect to Data in a Database](https://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).</span></span>  
  
3.  <span data-ttu-id="35d55-162">При появлении запроса с **мастер настройки источника данных**, сохранить строку подключения в качестве `NorthwindConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="35d55-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>  
  
4.  <span data-ttu-id="35d55-163">При появлении запроса на выбор объектов базы данных, выберите `Customers` и `Orders` таблицы и имя созданного набора данных `NorthwindDataSet`.</span><span class="sxs-lookup"><span data-stu-id="35d55-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>  
  
## <a name="binding-to-the-data-source"></a><span data-ttu-id="35d55-164">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="35d55-164">Binding to the Data Source</span></span>  
 <span data-ttu-id="35d55-165"><xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Компонент предоставляет единый интерфейс для источника данных приложения.</span><span class="sxs-lookup"><span data-stu-id="35d55-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="35d55-166">Привязка к источнику данных реализована в файле кода программной части.</span><span class="sxs-lookup"><span data-stu-id="35d55-166">Binding to the data source is implemented in the code-behind file.</span></span>  
  
#### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="35d55-167">Чтобы создать привязку к источнику данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="35d55-167">To bind to the data source</span></span>  
  
1.  <span data-ttu-id="35d55-168">Откройте файл кода программной части с именем MainWindow.xaml.vb или MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="35d55-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="35d55-169">Скопируйте следующий код в `MainWindow` определение класса.</span><span class="sxs-lookup"><span data-stu-id="35d55-169">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     <span data-ttu-id="35d55-170">Этот код объявляет <xref:System.Windows.Forms.BindingSource> компонента и связывает вспомогательные классы, которые подключаются к базе данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3.  <span data-ttu-id="35d55-171">Копируйте в конструктор следующий код.</span><span class="sxs-lookup"><span data-stu-id="35d55-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="35d55-172">Этот код создает и инициализирует <xref:System.Windows.Forms.BindingSource> компонента.</span><span class="sxs-lookup"><span data-stu-id="35d55-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4.  <span data-ttu-id="35d55-173">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="35d55-173">Open MainWindow.xaml.</span></span>

5.  <span data-ttu-id="35d55-174">В представлении конструирования или XAML, выберите <xref:System.Windows.Window> элемент.</span><span class="sxs-lookup"><span data-stu-id="35d55-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6.  <span data-ttu-id="35d55-175">В окне «Свойства» щелкните **события** вкладки.</span><span class="sxs-lookup"><span data-stu-id="35d55-175">In the Properties window, click the **Events** tab.</span></span>

7.  <span data-ttu-id="35d55-176">Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="35d55-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8.  <span data-ttu-id="35d55-177">Скопируйте следующий код в <xref:System.Windows.FrameworkElement.Loaded> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="35d55-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="35d55-178">Этот код присваивает <xref:System.Windows.Forms.BindingSource> компонент в качестве контекста данных и заполняет `Customers` и `Orders` объекты адаптера.</span><span class="sxs-lookup"><span data-stu-id="35d55-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="35d55-179">Скопируйте следующий код в `MainWindow` определение класса.</span><span class="sxs-lookup"><span data-stu-id="35d55-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="35d55-180">Этот метод обрабатывает <xref:System.Windows.Data.CollectionView.CurrentChanged> событий и обновляет текущий элемент привязки данных.</span><span class="sxs-lookup"><span data-stu-id="35d55-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. <span data-ttu-id="35d55-181">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="35d55-181">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d55-182">См. также</span><span class="sxs-lookup"><span data-stu-id="35d55-182">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="35d55-183">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35d55-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [<span data-ttu-id="35d55-184">Привязка данных в пример гибридного приложения</span><span class="sxs-lookup"><span data-stu-id="35d55-184">Data Binding in Hybrid Applications Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159983)  
 [<span data-ttu-id="35d55-185">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="35d55-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="35d55-186">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35d55-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
