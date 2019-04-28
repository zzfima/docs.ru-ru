---
title: Практическое руководство. Добавление сведений о строках в элемент управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911399"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="07e41-102">Практическое руководство. Добавление сведений о строках в элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="07e41-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="07e41-103">При использовании <xref:System.Windows.Controls.DataGrid> элемента управления, можно настраивать представление данных, добавив раздел сведений о строке.</span><span class="sxs-lookup"><span data-stu-id="07e41-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="07e41-104">Добавление раздела сведений о строке позволяет группировать некоторые данные в шаблон, который при необходимости видима или свернута.</span><span class="sxs-lookup"><span data-stu-id="07e41-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="07e41-105">Например, можно добавить сведения о строке в <xref:System.Windows.Controls.DataGrid> , представляющие только сводку данных для каждой строки в <xref:System.Windows.Controls.DataGrid>, но предоставляет дополнительные поля данных, когда пользователь выбирает строку.</span><span class="sxs-lookup"><span data-stu-id="07e41-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="07e41-106">Необходимо задать шаблон для раздела сведений о строке в <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="07e41-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="07e41-107">Ниже показан пример раздела сведений о строке.</span><span class="sxs-lookup"><span data-stu-id="07e41-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="07e41-108">![Сетка DataGrid, показанная со сведениями в строке](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="07e41-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="07e41-109">Определение шаблона сведений о строке, либо как встроенный XAML или как ресурс.</span><span class="sxs-lookup"><span data-stu-id="07e41-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="07e41-110">В следующих процедурах показаны оба подхода.</span><span class="sxs-lookup"><span data-stu-id="07e41-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="07e41-111">Шаблон данных, который добавляется в качестве ресурса можно использовать в проекте без повторного создания шаблона.</span><span class="sxs-lookup"><span data-stu-id="07e41-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="07e41-112">Шаблон данных, в который добавляется встроенный XAML доступен только из элемента управления, где он определен.</span><span class="sxs-lookup"><span data-stu-id="07e41-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="07e41-113">Отображение сведений о строке с помощью встроенного XAML</span><span class="sxs-lookup"><span data-stu-id="07e41-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="07e41-114">Создание <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.</span><span class="sxs-lookup"><span data-stu-id="07e41-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="07e41-115">В элементе <xref:System.Windows.Controls.DataGrid> добавьте элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="07e41-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="07e41-116">Создание <xref:System.Windows.DataTemplate> , определяющий внешний вид раздела сведений о строке.</span><span class="sxs-lookup"><span data-stu-id="07e41-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="07e41-117">В следующем XAML показан <xref:System.Windows.Controls.DataGrid> и как определить <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> встроенный.</span><span class="sxs-lookup"><span data-stu-id="07e41-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="07e41-118"><xref:System.Windows.Controls.DataGrid> Отображает три значения в каждой строке и три дополнительные значения при выборе строки.</span><span class="sxs-lookup"><span data-stu-id="07e41-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="07e41-119">В следующем коде показано запрос, который используется для выбора данных, который отображается в <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="07e41-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="07e41-120">В этом примере запрос выбирает данные из сущности, содержащей сведения о клиенте.</span><span class="sxs-lookup"><span data-stu-id="07e41-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="07e41-121">Отображение сведений о строке с помощью ресурса</span><span class="sxs-lookup"><span data-stu-id="07e41-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="07e41-122">Создание <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.</span><span class="sxs-lookup"><span data-stu-id="07e41-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="07e41-123">Добавить <xref:System.Windows.FrameworkElement.Resources%2A> элемент к корневому элементу, такие как <xref:System.Windows.Window> управления или <xref:System.Windows.Controls.Page> , или же добавьте <xref:System.Windows.Application.Resources%2A> элемент <xref:System.Windows.Application> класс в файле App.xaml (или файл Application.xaml).</span><span class="sxs-lookup"><span data-stu-id="07e41-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="07e41-124">В элементе ресурсов создайте <xref:System.Windows.DataTemplate> , определяющий внешний вид раздела сведений о строке.</span><span class="sxs-lookup"><span data-stu-id="07e41-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="07e41-125">В следующем XAML показан <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> определенные в <xref:System.Windows.Application> класса.</span><span class="sxs-lookup"><span data-stu-id="07e41-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="07e41-126">На <xref:System.Windows.DataTemplate>, задайте [директивы x: Key](../../xaml-services/x-key-directive.md) значение, которое однозначно определяет шаблон данных.</span><span class="sxs-lookup"><span data-stu-id="07e41-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../xaml-services/x-key-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="07e41-127">В <xref:System.Windows.Controls.DataGrid> элемент, наборе <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойство ресурс, определенный в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="07e41-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="07e41-128">Назначьте универсальный код ресурса, как статический ресурс.</span><span class="sxs-lookup"><span data-stu-id="07e41-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="07e41-129">В следующем XAML показан <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойство присвоен ресурс из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="07e41-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="07e41-130">Чтобы задать видимость и предотвратить горизонтальная прокрутка сведений о строке</span><span class="sxs-lookup"><span data-stu-id="07e41-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="07e41-131">При необходимости задайте <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> свойства <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> значение.</span><span class="sxs-lookup"><span data-stu-id="07e41-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="07e41-132">По умолчанию, присваивается значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="07e41-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="07e41-133">Можно задать значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> для отображения сведений для всех строк или <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> Чтобы скрыть сведения для всех строк.</span><span class="sxs-lookup"><span data-stu-id="07e41-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="07e41-134">При необходимости задайте <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> свойства `true` во избежание строки раздел горизонтальная прокрутка сведений о.</span><span class="sxs-lookup"><span data-stu-id="07e41-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
