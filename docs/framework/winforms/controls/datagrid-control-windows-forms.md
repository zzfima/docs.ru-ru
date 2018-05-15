---
title: Элемент управления DataGrid (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: 8618bfc691e86e8c609a6205ab44a891cc7e9f80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="3a63a-102">Элемент управления DataGrid (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3a63a-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="3a63a-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления `DataGrid` и расширяет его функциональные возможности; однако при необходимости элемент управления `DataGrid` можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="3a63a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="3a63a-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3a63a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="3a63a-105">Элемент управления Windows Forms `DataGrid` предоставляет пользовательский интерфейс для наборов данных [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], отображения табличных данных и включения обновлений в источник данных.</span><span class="sxs-lookup"><span data-stu-id="3a63a-105">The Windows Forms `DataGrid` control provides a user interface to [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="3a63a-106">Когда элементу управления `DataGrid` присвоен допустимый источник данных, этот элемент автоматически заполняется и создаются столбцы и строки, исходя из формы данных.</span><span class="sxs-lookup"><span data-stu-id="3a63a-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="3a63a-107">Элемент управления `DataGrid` можно использовать для отображения одной таблицы или иерархических связей между набором таблиц.</span><span class="sxs-lookup"><span data-stu-id="3a63a-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a63a-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3a63a-108">In This Section</span></span>  
 [<span data-ttu-id="3a63a-109">Общие сведения об элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3a63a-109">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="3a63a-110">Описание основных возможностей элемента управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="3a63a-111">Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="3a63a-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="3a63a-112">Описание добавления таблиц и столбцов в элемент управления `DataGrid` с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a63a-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="3a63a-113">Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="3a63a-114">Описание программного добавления таблиц и столбцов в элемент управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="3a63a-115">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="3a63a-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="3a63a-116">Описание привязки набора данных [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] к элементу управления `DataGrid` с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a63a-116">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="3a63a-117">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных</span><span class="sxs-lookup"><span data-stu-id="3a63a-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="3a63a-118">Описание привязки набора данных [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] к элементу управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-118">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="3a63a-119">Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="3a63a-120">Описание программного изменения данных в элементе управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="3a63a-121">Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="3a63a-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="3a63a-122">Описание способа отображения двух таблиц, связанных между собой отношением подчинения, в двух отдельных элементах управления `DataGrid` с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a63a-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="3a63a-123">Практическое руководство. Создание основных или подробных списков с помощью элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="3a63a-124">Описание способа отображения двух таблиц, связанных между собой отношением подчинения, в двух отдельных элементах управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="3a63a-125">Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="3a63a-126">Описание удаления столбцов в элементе управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="3a63a-127">Практическое руководство. Форматирование элемента управления DataGrid в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="3a63a-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="3a63a-128">Описание способов изменения свойств, связанных с внешним видом элемента управления `DataGrid` с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a63a-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="3a63a-129">Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-129">How to: Format the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="3a63a-130">Описание способов изменения свойств, связанных с внешним видом элемента управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="3a63a-131">Сочетания клавиш для элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="3a63a-132">Список сочетаний клавиш для навигации по элементу управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="3a63a-133">Практическое руководство. Обработка щелчка мыши элементом управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="3a63a-134">Описание способов определения того, какую ячейку пользователь щелкнул в элементе управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="3a63a-135">Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="3a63a-136">Описание способов проверки входных данных в наборе данных, привязанном к элементу управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="3a63a-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3a63a-137">Ссылка</span><span class="sxs-lookup"><span data-stu-id="3a63a-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="3a63a-138">Общие сведения о <xref:System.Windows.Forms.DataGrid> класса.</span><span class="sxs-lookup"><span data-stu-id="3a63a-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="3a63a-139">Предоставляет подробные сведения об использовании этого свойства для привязки <xref:System.Windows.Forms.DataGrid> элемента управления к данным.</span><span class="sxs-lookup"><span data-stu-id="3a63a-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3a63a-140">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3a63a-140">Related Sections</span></span>  
 [<span data-ttu-id="3a63a-141">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-141">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 <span data-ttu-id="3a63a-142">Ссылки на разделы о привязке данных в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3a63a-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a63a-143">См. также</span><span class="sxs-lookup"><span data-stu-id="3a63a-143">See Also</span></span>  
 [<span data-ttu-id="3a63a-144">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="3a63a-144">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="3a63a-145">Различия элементов управления DataGridView и DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a63a-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
