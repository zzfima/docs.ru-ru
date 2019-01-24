---
title: Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: af8dcaf8b6d32f03c2f2f46312d1290a99381c43
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611505"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="af285-102">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="af285-103">Многие базовое поведение `DataGridView` ячеек, строк и столбцов можно изменить путем задания одного свойства.</span><span class="sxs-lookup"><span data-stu-id="af285-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="af285-104">В этом разделе описываются некоторые из наиболее часто используемые из этих функций.</span><span class="sxs-lookup"><span data-stu-id="af285-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af285-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="af285-105">In This Section</span></span>  
 [<span data-ttu-id="af285-106">Практическое руководство. Скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af285-107">Описание способа отключения определенных столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="af285-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="af285-108">Практическое руководство. Скрытие заголовков столбцов в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af285-109">Описание способов предотвратить появление в элементе управления заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="af285-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="af285-110">Практическое руководство. Разрешение изменения порядка столбцов в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af285-111">Описывает, как разрешить пользователям для изменения порядка столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="af285-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="af285-112">Практическое руководство. Закрепление столбцов в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af285-113">Описывает способ избежать прокрутки один или несколько смежных столбцов.</span><span class="sxs-lookup"><span data-stu-id="af285-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="af285-114">Практическое руководство. Столбцы, сделайте доступным только для чтения в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af285-115">Описывает способ запретить пользователям изменять определенные столбцы в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="af285-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="af285-116">Практическое руководство. Предотвращение добавления и удаления в элементе управления DataGridView Windows Forms строк</span><span class="sxs-lookup"><span data-stu-id="af285-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="af285-117">В этой статье описывается удаление строки для новых записей в нижней части элемента управления, чтобы запретить пользователям добавлять строки.</span><span class="sxs-lookup"><span data-stu-id="af285-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="af285-118">Также описывает способ запретить пользователям удалять строки.</span><span class="sxs-lookup"><span data-stu-id="af285-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="af285-119">Практическое руководство. Получение и установка значения текущей ячейки в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="af285-120">Описание способов доступа к ячейке, которая в данный момент имеет фокус в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="af285-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="af285-121">Практическое руководство. Отображение изображений в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af285-122">В этой статье описывается создание столбца с изображением, в каждой ячейке отображается значок.</span><span class="sxs-lookup"><span data-stu-id="af285-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="af285-123">Ссылка</span><span class="sxs-lookup"><span data-stu-id="af285-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="af285-124">Содержит справочную документацию для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af285-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="af285-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="af285-125">Related Sections</span></span>  
 [<span data-ttu-id="af285-126">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af285-127">Разделы, описывающие способы изменения базового внешнего вида элемента управления и форматирования отображаемых данных ячейки.</span><span class="sxs-lookup"><span data-stu-id="af285-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="af285-128">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="af285-129">Разделы, описывающие программирование объектов ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="af285-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af285-130">См. также</span><span class="sxs-lookup"><span data-stu-id="af285-130">See also</span></span>
- [<span data-ttu-id="af285-131">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="af285-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
- [<span data-ttu-id="af285-132">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af285-132">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
