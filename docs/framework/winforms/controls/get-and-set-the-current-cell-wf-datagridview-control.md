---
title: Получение и задание текущей ячейки в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 0fb01d5392e02b53e0e5bf905c872dbeeb22fad9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745658"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c2fd7-102">Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2fd7-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c2fd7-103">Взаимодействие с <xref:System.Windows.Forms.DataGridView> часто требует, чтобы вы программно обнаружили, какая ячейка активна в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="c2fd7-104">Также может потребоваться изменить текущую ячейку.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-104">You may also need to change the current cell.</span></span> <span data-ttu-id="c2fd7-105">Эти задачи можно выполнить с помощью свойства <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2fd7-106">Нельзя задать текущую ячейку в строке или столбце, для свойства <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> которого задано значение `false`.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="c2fd7-107">В зависимости от режима выбора элемента управления <xref:System.Windows.Forms.DataGridView> изменение текущей ячейки может изменить выбор.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="c2fd7-108">Дополнительные сведения см. [в разделе Режимы выделения в элементе управления Windows Forms DataGridView](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c2fd7-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="c2fd7-109">Получение текущей ячейки программным способом</span><span class="sxs-lookup"><span data-stu-id="c2fd7-109">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="c2fd7-110">Используйте свойство <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="c2fd7-111">Задание текущей ячейки программным способом</span><span class="sxs-lookup"><span data-stu-id="c2fd7-111">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="c2fd7-112">Задайте свойство <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c2fd7-113">В следующем примере кода текущей ячейке присваивается значение строка 0, столбец 1.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c2fd7-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c2fd7-114">Compiling the Code</span></span>  
 <span data-ttu-id="c2fd7-115">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c2fd7-115">This example requires:</span></span>  
  
- <span data-ttu-id="c2fd7-116"><xref:System.Windows.Forms.Button> элементы управления с именами `getCurrentCellButton` и `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="c2fd7-117">В визуальном C#элементе необходимо прикрепить события <xref:System.Windows.Forms.Control.Click> для каждой кнопки к соответствующему обработчику событий в примере кода.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="c2fd7-118">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="c2fd7-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="c2fd7-119">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c2fd7-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fd7-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c2fd7-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c2fd7-121">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2fd7-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="c2fd7-122">Режимы выделения содержимого элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2fd7-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
