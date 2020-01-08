---
title: Добавление сведений о строках в элемент управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 4db414e1907d42071f7251c390077d4020fa577c
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559681"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="1c4e7-102">Добавление сведений о строках в элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="1c4e7-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="1c4e7-103">При использовании элемента управления <xref:System.Windows.Controls.DataGrid> можно настроить представление данных, добавив раздел сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="1c4e7-104">Добавление раздела сведений о строке позволяет сгруппировать некоторые данные в шаблон, который можно показать или свернуть.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="1c4e7-105">Например, можно добавить сведения о строках в <xref:System.Windows.Controls.DataGrid>, которая представляет только сводку по данным для каждой строки в <xref:System.Windows.Controls.DataGrid>, но при этом предоставляет больше полей данных, когда пользователь выбирает строку.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="1c4e7-106">Вы определяете шаблон для раздела сведения о строке в свойстве <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="1c4e7-107">На следующем рисунке показан пример раздела сведений о строке.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="1c4e7-108">![Сетка, показанная со сведениями о строках](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="1c4e7-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="1c4e7-109">Шаблон сведений о строках определяется как встроенный XAML или ресурс.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="1c4e7-110">Оба подхода показаны в следующих процедурах.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="1c4e7-111">Шаблон данных, добавленный в качестве ресурса, можно использовать во всем проекте без повторного создания шаблона.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="1c4e7-112">Шаблон данных, добавленный как встроенный код XAML, доступен только из элемента управления, в котором он определен.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="1c4e7-113">Отображение сведений о строках с помощью встроенного кода XAML</span><span class="sxs-lookup"><span data-stu-id="1c4e7-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="1c4e7-114">Создайте <xref:System.Windows.Controls.DataGrid>, отображающий данные из источника данных.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="1c4e7-115">В элементе <xref:System.Windows.Controls.DataGrid> добавьте элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="1c4e7-116">Создайте <xref:System.Windows.DataTemplate>, определяющую внешний вид раздела сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="1c4e7-117">В следующем коде XAML показан <xref:System.Windows.Controls.DataGrid> и определение встроенного <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="1c4e7-118"><xref:System.Windows.Controls.DataGrid> отображает три значения в каждой строке и три дополнительных значения при выборе строки.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="1c4e7-119">В следующем коде показан запрос, используемый для выбора данных, отображаемых в <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="1c4e7-120">В этом примере запрос выбирает данные из сущности, содержащей сведения о клиенте.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="1c4e7-121">Отображение сведений о строках с помощью ресурса</span><span class="sxs-lookup"><span data-stu-id="1c4e7-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="1c4e7-122">Создайте <xref:System.Windows.Controls.DataGrid>, отображающий данные из источника данных.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="1c4e7-123">Добавьте элемент <xref:System.Windows.FrameworkElement.Resources%2A> в корневой элемент, например элемент управления <xref:System.Windows.Window> или элемент управления <xref:System.Windows.Controls.Page>, или добавьте элемент <xref:System.Windows.Application.Resources%2A> в класс <xref:System.Windows.Application> в файле App. XAML (или Application. XAML).</span><span class="sxs-lookup"><span data-stu-id="1c4e7-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="1c4e7-124">В элементе Resources создайте <xref:System.Windows.DataTemplate>, определяющую внешний вид раздела сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="1c4e7-125">В следующем коде XAML показан <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>, определенный в классе <xref:System.Windows.Application>.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="1c4e7-126">На <xref:System.Windows.DataTemplate>задайте для [директивы x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) значение, уникально идентифицирующее шаблон данных.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="1c4e7-127">В элементе <xref:System.Windows.Controls.DataGrid> задайте для свойства <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> ресурс, определенный на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="1c4e7-128">Назначьте ресурс как статический ресурс.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="1c4e7-129">В следующем коде XAML показано свойство <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>, заданное для ресурса из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="1c4e7-130">Установка видимости и предотвращение горизонтальной прокрутки для сведений о строках</span><span class="sxs-lookup"><span data-stu-id="1c4e7-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="1c4e7-131">При необходимости задайте для свойства <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="1c4e7-132">По умолчанию устанавливается значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="1c4e7-133">Можно задать для него значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible>, чтобы отобразить подробные сведения для всех строк или <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed>, чтобы скрыть сведения для всех строк.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="1c4e7-134">При необходимости задайте для свойства <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> значение `true`, чтобы не допустить горизонтальной прокрутки раздела сведений о строках.</span><span class="sxs-lookup"><span data-stu-id="1c4e7-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
