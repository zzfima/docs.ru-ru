---
title: Отображение данных с помощью элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: c153d422470ff20491567aed70557e461dc2b4e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168640"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="24187-102">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="24187-103">`DataGridView` Управления используется для отображения данных из различных внешних источников данных.</span><span class="sxs-lookup"><span data-stu-id="24187-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="24187-104">Кроме того можно добавить строки и столбцы для элемента управления и вручную заполнить его данными.</span><span class="sxs-lookup"><span data-stu-id="24187-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="24187-105">При привязке элемента управления к источнику данных, можно создать столбцы, автоматически на основе схемы источника данных.</span><span class="sxs-lookup"><span data-stu-id="24187-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="24187-106">Если эти столбцы не отображаются так же, как надо, можно скрыть, удалить или изменить их порядок.</span><span class="sxs-lookup"><span data-stu-id="24187-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="24187-107">Можно также добавить несвязанные столбцы для отображения дополнительных данных, поступающих не из источника данных.</span><span class="sxs-lookup"><span data-stu-id="24187-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="24187-108">Кроме того можно отображать данные с помощью стандартных форматах (например, формат денежной единицы), или настроить форматирование представления данных, однако необходимо (например, изменение цвета фона для отрицательных чисел или заменить строковые значения отображения с помощью соответствующие образы).</span><span class="sxs-lookup"><span data-stu-id="24187-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24187-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="24187-109">In This Section</span></span>  
 [<span data-ttu-id="24187-110">Режимы отображения данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24187-111">Описание параметров заполнения элемента управления данными.</span><span class="sxs-lookup"><span data-stu-id="24187-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="24187-112">Форматирование данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24187-113">Описывает параметры для форматирования отображения значений ячеек.</span><span class="sxs-lookup"><span data-stu-id="24187-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="24187-114">Пошаговое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24187-115">Описывает, как вручную заполнение элемента управления с данными.</span><span class="sxs-lookup"><span data-stu-id="24187-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="24187-116">Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24187-117">Описывает заполнение элемента управления данными, привязав его к `BindingSource` , содержащий сведения, извлеченные из базы данных.</span><span class="sxs-lookup"><span data-stu-id="24187-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="24187-118">Практическое руководство. Автоматическое создание столбцов связанного с данными элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="24187-119">В этой статье описывается автоматическое создание столбцов, в зависимости от связанного источника данных.</span><span class="sxs-lookup"><span data-stu-id="24187-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="24187-120">Практическое руководство. Удаление автоматически сгенерированных столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="24187-121">Описывает, как скрыть или удалить столбцы, создается автоматически из привязанного источника данных.</span><span class="sxs-lookup"><span data-stu-id="24187-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="24187-122">Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24187-123">В этой статье описывается изменение порядка столбцов, автоматически создается из связанного источника данных.</span><span class="sxs-lookup"><span data-stu-id="24187-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="24187-124">Практическое руководство. Добавление столбца, не связанного с данными, в связанный с данными элемент управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="24187-125">Описывает способ дополнить данные из привязанного источника данных путем отображения дополнительных несвязанных столбцов.</span><span class="sxs-lookup"><span data-stu-id="24187-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="24187-126">Практическое руководство. Связывание объектов с элементами управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="24187-127">В этой статье описывается привязка элемента управления в коллекцию произвольных объектов, так что каждый объект отображается в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="24187-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="24187-128">Практическое руководство. Доступ к связанным объектам в строках DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="24187-129">В этой статье описывается извлечение объекта, связанного с определенной строкой элемента управления.</span><span class="sxs-lookup"><span data-stu-id="24187-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="24187-130">Пошаговое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="24187-131">Описание способа отображения данных из двух связанных таблиц базы данных, чтобы значения, показанные в одном `DataGridView` управления зависят от выбранной строки в другой элемент управления.</span><span class="sxs-lookup"><span data-stu-id="24187-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="24187-132">Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24187-133">Описание способов обработки <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> событий, чтобы изменить внешний вид ячеек в зависимости от их значения.</span><span class="sxs-lookup"><span data-stu-id="24187-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="24187-134">Ссылка</span><span class="sxs-lookup"><span data-stu-id="24187-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="24187-135">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="24187-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="24187-136">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="24187-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="24187-137">Содержит справочную документацию по компоненту <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="24187-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="24187-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="24187-138">Related Sections</span></span>  
 [<span data-ttu-id="24187-139">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24187-140">Разделы, в которых описывается изменение способов добавления и изменения данных в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="24187-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24187-141">См. также</span><span class="sxs-lookup"><span data-stu-id="24187-141">See also</span></span>

- [<span data-ttu-id="24187-142">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="24187-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="24187-143">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24187-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
