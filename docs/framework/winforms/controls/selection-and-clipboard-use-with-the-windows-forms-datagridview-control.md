---
title: "Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ceea4108f39619ccbcbf0286905a94b8236607cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="f9f84-102">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9f84-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f9f84-103">`DataGridView` Элемент управления предоставляет множество параметров для настройки, как пользователи могут выбрать ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="f9f84-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="f9f84-104">Например можно включить выделение одного или нескольких элементов, выбор целых строк или столбцов, при щелчке ячейки или выбор целых строк или столбцов только в том случае, если пользователь щелкнет их заголовки, что позволяет также выделение ячеек.</span><span class="sxs-lookup"><span data-stu-id="f9f84-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="f9f84-105">Если вы хотите предоставить собственный пользовательский интерфейс для выбора, можно отключить стандартные функции выбора и обрабатывать все команды выбора программным путем.</span><span class="sxs-lookup"><span data-stu-id="f9f84-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="f9f84-106">Кроме того можно разрешить пользователям копировать выбранные значения в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="f9f84-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9f84-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f9f84-107">In This Section</span></span>  
 [<span data-ttu-id="f9f84-108">Режимы выделения содержимого элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9f84-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f9f84-109">Описывает параметры для пользователей и программный выбор в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="f9f84-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="f9f84-110">Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9f84-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f9f84-111">Описывает, как настроить элемент управления для выбора одной строки, когда пользователь щелкает ячейку.</span><span class="sxs-lookup"><span data-stu-id="f9f84-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="f9f84-112">Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9f84-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="f9f84-113">Описание работы с выбранными коллекциями ячеек, строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="f9f84-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="f9f84-114">Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9f84-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="f9f84-115">Описывает способ включения поддержки буфера обмена в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="f9f84-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f9f84-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f9f84-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="f9f84-117">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="f9f84-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="f9f84-118">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f9f84-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="f9f84-119">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f9f84-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="f9f84-120">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="f9f84-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="f9f84-121">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="f9f84-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="f9f84-122">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="f9f84-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f84-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f9f84-123">See Also</span></span>  
 [<span data-ttu-id="f9f84-124">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="f9f84-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="f9f84-125">Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9f84-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
