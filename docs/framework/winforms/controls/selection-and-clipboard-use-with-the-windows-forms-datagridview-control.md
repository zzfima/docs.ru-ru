---
title: Выбор и использование буфера обмена с элементом управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 6993f77e8ce532d8df1bdc7e6b6abc1cc3268e49
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743064"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="d4f54-102">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f54-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d4f54-103">Элемент управления `DataGridView` предоставляет разнообразные параметры для настройки того, как пользователи могут выбирать ячейки, строки и столбцы.</span><span class="sxs-lookup"><span data-stu-id="d4f54-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="d4f54-104">Например, можно включить единичное или множественное выделение, выбрать целые строки или столбцы, если пользователь щелкнул ячейки, или выбрать целые строки или столбцы только в том случае, если пользователи щелкают заголовки, что также позволяет выбрать ячейку.</span><span class="sxs-lookup"><span data-stu-id="d4f54-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="d4f54-105">Если вы хотите предоставить собственный пользовательский интерфейс для выбора, можно отключить обычный выбор и все выбранные элементы программным способом.</span><span class="sxs-lookup"><span data-stu-id="d4f54-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="d4f54-106">Кроме того, можно разрешить пользователям копировать выбранные значения в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="d4f54-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4f54-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d4f54-107">In This Section</span></span>  
 [<span data-ttu-id="d4f54-108">Режимы выделения содержимого элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f54-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4f54-109">Описывает параметры для пользователя и программного выбора в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d4f54-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="d4f54-110">Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f54-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4f54-111">Описывает, как настроить элемент управления для выбора одной строки, когда пользователь щелкнет ячейку.</span><span class="sxs-lookup"><span data-stu-id="d4f54-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="d4f54-112">Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f54-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="d4f54-113">Описывает, как работать с выбранными коллекциями ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="d4f54-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="d4f54-114">Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f54-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="d4f54-115">Описывает, как включить поддержку буфера обмена в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d4f54-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d4f54-116">Справочник</span><span class="sxs-lookup"><span data-stu-id="d4f54-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d4f54-117">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d4f54-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="d4f54-118">Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4f54-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="d4f54-119">Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4f54-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="d4f54-120">Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>.</span><span class="sxs-lookup"><span data-stu-id="d4f54-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="d4f54-121">Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>.</span><span class="sxs-lookup"><span data-stu-id="d4f54-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="d4f54-122">Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="d4f54-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f54-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d4f54-123">See also</span></span>

- [<span data-ttu-id="d4f54-124">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="d4f54-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="d4f54-125">Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f54-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
