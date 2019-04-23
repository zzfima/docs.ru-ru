---
title: Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: fb71a6e3259d3007e11f528377c95a9c4cbeb023
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096983"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="35f1f-102">Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35f1f-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="35f1f-103">Взаимодействие с <xref:System.Windows.Forms.DataGridView> часто требуется программно найденные ячейки, которая в данный момент активна.</span><span class="sxs-lookup"><span data-stu-id="35f1f-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="35f1f-104">Кроме того, может потребоваться изменить текущую ячейку.</span><span class="sxs-lookup"><span data-stu-id="35f1f-104">You may also need to change the current cell.</span></span> <span data-ttu-id="35f1f-105">Можно выполнять эти задачи с помощью <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="35f1f-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35f1f-106">Невозможно задать текущую ячейку в строке или столбце с его <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> свойство значение `false`.</span><span class="sxs-lookup"><span data-stu-id="35f1f-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="35f1f-107">В зависимости от <xref:System.Windows.Forms.DataGridView> Выбор можно изменить режим выбора элемента управления, изменение текущей ячейки.</span><span class="sxs-lookup"><span data-stu-id="35f1f-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="35f1f-108">Дополнительные сведения см. в разделе [режимы выделения в элементе управления DataGridView Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="35f1f-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="35f1f-109">Чтобы получить текущую ячейку программным способом</span><span class="sxs-lookup"><span data-stu-id="35f1f-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="35f1f-110">Используйте <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="35f1f-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="35f1f-111">Установка текущей ячейки программным способом</span><span class="sxs-lookup"><span data-stu-id="35f1f-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="35f1f-112">Задайте <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойство <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="35f1f-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="35f1f-113">В следующем примере кода текущая ячейка имеет значение в строке 0, столбец 1.</span><span class="sxs-lookup"><span data-stu-id="35f1f-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="35f1f-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="35f1f-114">Compiling the Code</span></span>  
 <span data-ttu-id="35f1f-115">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="35f1f-115">This example requires:</span></span>  
  
-   <span data-ttu-id="35f1f-116"><xref:System.Windows.Forms.Button> элементы управления с именем `getCurrentCellButton` и `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="35f1f-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="35f1f-117">В визуальном элементе C#, необходимо присоединить <xref:System.Windows.Forms.Control.Click> событий для каждой кнопки в соответствующем обработчике событий в примере кода.</span><span class="sxs-lookup"><span data-stu-id="35f1f-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="35f1f-118">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="35f1f-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="35f1f-119">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="35f1f-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f1f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="35f1f-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="35f1f-121">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35f1f-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="35f1f-122">Режимы выделения содержимого элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35f1f-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
