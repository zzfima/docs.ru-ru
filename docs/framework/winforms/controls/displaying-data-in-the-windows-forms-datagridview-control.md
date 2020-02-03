---
title: Отображение данных в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: d02362895d75df3735d19554bd44bb8ac443c6c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745870"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c9612-102">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c9612-103">Элемент управления `DataGridView` используется для вывода данных из различных внешних источников данных.</span><span class="sxs-lookup"><span data-stu-id="c9612-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="c9612-104">Кроме того, можно добавить строки и столбцы в элемент управления и вручную заполнить его данными.</span><span class="sxs-lookup"><span data-stu-id="c9612-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="c9612-105">При привязке элемента управления к источнику данных столбцы можно создавать автоматически на основе схемы источника данных.</span><span class="sxs-lookup"><span data-stu-id="c9612-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="c9612-106">Если эти столбцы не отображаются так, как нужно, их можно скрыть, удалить или изменить.</span><span class="sxs-lookup"><span data-stu-id="c9612-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="c9612-107">Можно также добавить несвязанные столбцы, чтобы отобразить дополнительные данные, которые не поступают из источника данных.</span><span class="sxs-lookup"><span data-stu-id="c9612-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="c9612-108">Кроме того, можно отобразить данные с помощью стандартных форматов (например, формата валюты) или настроить форматирование отображения для представления данных, но вам потребуется (например, изменить цвет фона для отрицательных чисел или заменить строковые значения). с соответствующими образами).</span><span class="sxs-lookup"><span data-stu-id="c9612-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9612-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c9612-109">In This Section</span></span>  
 [<span data-ttu-id="c9612-110">Режимы отображения данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c9612-111">Описывает параметры заполнения элемента управления данными.</span><span class="sxs-lookup"><span data-stu-id="c9612-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="c9612-112">Форматирование данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c9612-113">Описывает параметры форматирования отображаемых значений ячеек.</span><span class="sxs-lookup"><span data-stu-id="c9612-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="c9612-114">Пошаговое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c9612-115">Описывает, как вручную заполнить элемент управления данными.</span><span class="sxs-lookup"><span data-stu-id="c9612-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="c9612-116">Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c9612-117">Описывает, как заполнить элемент управления данными, привязывая его к `BindingSource`, который содержит сведения, извлеченные из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c9612-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="c9612-118">Практическое руководство. Автоматическое создание столбцов связанного с данными элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="c9612-119">Описывает автоматическое создание столбцов на основе привязанного источника данных.</span><span class="sxs-lookup"><span data-stu-id="c9612-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="c9612-120">Практическое руководство. Удаление автоматически сгенерированных столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="c9612-121">Описывает, как скрывать или удалять столбцы, автоматически формируемые из привязанного источника данных.</span><span class="sxs-lookup"><span data-stu-id="c9612-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="c9612-122">Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c9612-123">Описывает, как изменить порядок столбцов, созданных автоматически, из привязанного источника данных.</span><span class="sxs-lookup"><span data-stu-id="c9612-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="c9612-124">Практическое руководство. Добавление столбца, не связанного с данными, в связанный с данными элемент управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="c9612-125">Описывает, как дополнять данные из привязанного источника данных путем отображения дополнительных несвязанных столбцов.</span><span class="sxs-lookup"><span data-stu-id="c9612-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="c9612-126">Практическое руководство. Связывание объектов с элементами управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="c9612-127">Описывает, как привязать элемент управления к коллекции произвольных объектов, чтобы каждый объект отображался в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="c9612-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="c9612-128">Практическое руководство. Доступ к связанным объектам в строках DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="c9612-129">Описывает, как получить объект, привязанный к определенной строке элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9612-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="c9612-130">Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="c9612-131">Описывает, как отобразить данные из двух связанных таблиц базы данных, чтобы значения, отображаемые в одном `DataGridView` элементе управления, зависели от текущей выбранной строки в другом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c9612-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="c9612-132">Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c9612-133">Описывает обработку события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> для изменения внешнего вида ячеек в зависимости от их значений.</span><span class="sxs-lookup"><span data-stu-id="c9612-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c9612-134">Справочник</span><span class="sxs-lookup"><span data-stu-id="c9612-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="c9612-135">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c9612-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="c9612-136">Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.DataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="c9612-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="c9612-137">Содержит справочную документацию по компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="c9612-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9612-138">См. также</span><span class="sxs-lookup"><span data-stu-id="c9612-138">Related Sections</span></span>  
 [<span data-ttu-id="c9612-139">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c9612-140">Разделы, в которых описывается изменение способов добавления и изменения данных в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c9612-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9612-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c9612-141">See also</span></span>

- [<span data-ttu-id="c9612-142">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="c9612-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="c9612-143">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9612-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
