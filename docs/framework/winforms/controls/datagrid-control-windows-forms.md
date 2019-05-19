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
ms.openlocfilehash: 5a69605901eef7366c7a9ff9930e5f4ec6cece23
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878776"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="04373-102">Элемент управления DataGrid (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="04373-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="04373-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления `DataGrid` и расширяет его функциональные возможности; однако при необходимости элемент управления `DataGrid` можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="04373-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="04373-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="04373-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="04373-105">Windows Forms `DataGrid` управления предоставляет пользовательский интерфейс для наборов данных ADO.NET, отображения табличных данных и включении обновления к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="04373-105">The Windows Forms `DataGrid` control provides a user interface to ADO.NET datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="04373-106">Когда элементу управления `DataGrid` присвоен допустимый источник данных, этот элемент автоматически заполняется и создаются столбцы и строки, исходя из формы данных.</span><span class="sxs-lookup"><span data-stu-id="04373-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="04373-107">Элемент управления `DataGrid` можно использовать для отображения одной таблицы или иерархических связей между набором таблиц.</span><span class="sxs-lookup"><span data-stu-id="04373-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04373-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="04373-108">In This Section</span></span>  
 [<span data-ttu-id="04373-109">Общие сведения об элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="04373-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="04373-110">Описание основных возможностей элемента управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="04373-111">Практическое руководство. Добавление таблиц и столбцов элемента управления Windows Forms DataGrid с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="04373-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="04373-112">Описание добавления таблиц и столбцов в элемент управления `DataGrid` с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="04373-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="04373-113">Практическое руководство. Добавление таблиц и столбцов элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="04373-114">Описание программного добавления таблиц и столбцов в элемент управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="04373-115">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="04373-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="04373-116">Описание привязки набора данных ADO.NET для `DataGrid` управления с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="04373-116">Describes how to bind an ADO.NET dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="04373-117">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных</span><span class="sxs-lookup"><span data-stu-id="04373-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="04373-118">Описание привязки набора данных ADO.NET для `DataGrid` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="04373-118">Describes how to bind an ADO.NET dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="04373-119">Практическое руководство. Изменение данных, отображаемых в элементе управления DataGrid Windows Forms во время выполнения</span><span class="sxs-lookup"><span data-stu-id="04373-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="04373-120">Описание программного изменения данных в элементе управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="04373-121">Практическое руководство. Создание списков основных сведений с помощью элемента управления Windows Forms DataGrid с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="04373-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="04373-122">Описание способа отображения двух таблиц, связанных между собой отношением подчинения, в двух отдельных элементах управления `DataGrid` с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="04373-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="04373-123">Практическое руководство. Создание списков основных сведений с помощью элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="04373-124">Описание способа отображения двух таблиц, связанных между собой отношением подчинения, в двух отдельных элементах управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="04373-125">Практическое руководство. Удаление или скрытие столбцов элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="04373-126">Описание удаления столбцов в элементе управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="04373-127">Практическое руководство. Форматирование элемента управления Windows Forms DataGrid с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="04373-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="04373-128">Описание способов изменения свойств, связанных с внешним видом элемента управления `DataGrid` с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="04373-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="04373-129">Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="04373-130">Описание способов изменения свойств, связанных с внешним видом элемента управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="04373-131">Сочетания клавиш для элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="04373-132">Список сочетаний клавиш для навигации по элементу управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="04373-133">Практическое руководство. Обработка щелчка мыши в элементе управления DataGrid Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="04373-134">Описание способов определения того, какую ячейку пользователь щелкнул в элементе управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="04373-135">Практическое руководство. Проверки входных данных с помощью элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="04373-136">Описание способов проверки входных данных в наборе данных, привязанном к элементу управления `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="04373-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="04373-137">Ссылка</span><span class="sxs-lookup"><span data-stu-id="04373-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="04373-138">Общие сведения о <xref:System.Windows.Forms.DataGrid> класса.</span><span class="sxs-lookup"><span data-stu-id="04373-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="04373-139">Подробные сведения об использовании этого свойства для привязки <xref:System.Windows.Forms.DataGrid> элемент управления к данным.</span><span class="sxs-lookup"><span data-stu-id="04373-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="04373-140">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="04373-140">Related Sections</span></span>  
 [<span data-ttu-id="04373-141">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="04373-142">Ссылки на разделы о привязке данных в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="04373-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04373-143">См. также</span><span class="sxs-lookup"><span data-stu-id="04373-143">See also</span></span>

- [<span data-ttu-id="04373-144">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="04373-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="04373-145">Различия элементов управления DataGridView и DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04373-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
