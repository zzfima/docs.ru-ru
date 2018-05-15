---
title: Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 3d6a44dce7dfd59d484d1a3495982a0d7d1f3e46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="eb184-102">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="eb184-103">Во многих случаях basic поведение `DataGridView` ячеек, строк и столбцов можно изменить путем задания одного свойства.</span><span class="sxs-lookup"><span data-stu-id="eb184-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="eb184-104">В этом разделе описываются некоторые из наиболее часто используемые из этих функций.</span><span class="sxs-lookup"><span data-stu-id="eb184-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb184-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="eb184-105">In This Section</span></span>  
 [<span data-ttu-id="eb184-106">Практическое руководство. Скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb184-107">Описывает, как для отключения определенных столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="eb184-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="eb184-108">Практическое руководство. Скрытие заголовков столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb184-109">Описывает, как предотвратить заголовки столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="eb184-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="eb184-110">Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb184-111">Описывает, как разрешить пользователям изменять порядок столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="eb184-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="eb184-112">Практическое руководство. Замораживание столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb184-113">Описывает способ предотвратить один или несколько смежных столбцов, в результате прокрутки.</span><span class="sxs-lookup"><span data-stu-id="eb184-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="eb184-114">Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb184-115">Описывает, как запретить пользователям редактировать определенные столбцы в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="eb184-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="eb184-116">Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="eb184-117">Описывает, как удалить строку для новых записей в нижней части элемента управления, чтобы запретить пользователям добавлять строки.</span><span class="sxs-lookup"><span data-stu-id="eb184-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="eb184-118">Также описывает, как запретить пользователям удалять строки.</span><span class="sxs-lookup"><span data-stu-id="eb184-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="eb184-119">Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="eb184-120">Описание способов доступа к ячейке, которая фокус в данный момент в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="eb184-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="eb184-121">Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb184-122">Описание способов создания столбца с изображением, отображается значок в каждой ячейке.</span><span class="sxs-lookup"><span data-stu-id="eb184-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eb184-123">Ссылка</span><span class="sxs-lookup"><span data-stu-id="eb184-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="eb184-124">Содержит справочную документацию для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="eb184-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eb184-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="eb184-125">Related Sections</span></span>  
 [<span data-ttu-id="eb184-126">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb184-127">Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.</span><span class="sxs-lookup"><span data-stu-id="eb184-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="eb184-128">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="eb184-129">Разделы, описывающие программирование объектов ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="eb184-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb184-130">См. также</span><span class="sxs-lookup"><span data-stu-id="eb184-130">See Also</span></span>  
 [<span data-ttu-id="eb184-131">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="eb184-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="eb184-132">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb184-132">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
