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
ms.openlocfilehash: 670708f342e1cd1ac495c215b7508093349ac2e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933699"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1a11e-102">Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a11e-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1a11e-103">Для взаимодействия с <xref:System.Windows.Forms.DataGridView> часто требуется программно определить, какая ячейка активна в данный момент.</span><span class="sxs-lookup"><span data-stu-id="1a11e-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="1a11e-104">Также может потребоваться изменить текущую ячейку.</span><span class="sxs-lookup"><span data-stu-id="1a11e-104">You may also need to change the current cell.</span></span> <span data-ttu-id="1a11e-105">Эти задачи можно выполнить с помощью <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="1a11e-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a11e-106">Нельзя задать текущую ячейку в строке или столбце, <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> для `false`свойства которого задано значение.</span><span class="sxs-lookup"><span data-stu-id="1a11e-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="1a11e-107">В зависимости от <xref:System.Windows.Forms.DataGridView> режима выбора элемента управления изменение текущей ячейки может изменить выбор.</span><span class="sxs-lookup"><span data-stu-id="1a11e-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="1a11e-108">Дополнительные сведения см. [в разделе Режимы выделения в элементе управления Windows Forms DataGridView](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="1a11e-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="1a11e-109">Получение текущей ячейки программным способом</span><span class="sxs-lookup"><span data-stu-id="1a11e-109">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="1a11e-110"><xref:System.Windows.Forms.DataGridView> Используйте свойство<xref:System.Windows.Forms.DataGridView.CurrentCell%2A> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a11e-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="1a11e-111">Задание текущей ячейки программным способом</span><span class="sxs-lookup"><span data-stu-id="1a11e-111">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="1a11e-112"><xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Задайте свойство <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a11e-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1a11e-113">В следующем примере кода текущей ячейке присваивается значение строка 0, столбец 1.</span><span class="sxs-lookup"><span data-stu-id="1a11e-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1a11e-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1a11e-114">Compiling the Code</span></span>  
 <span data-ttu-id="1a11e-115">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="1a11e-115">This example requires:</span></span>  
  
- <span data-ttu-id="1a11e-116"><xref:System.Windows.Forms.Button>элементы управления `getCurrentCellButton` с `setCurrentCellButton`именами и.</span><span class="sxs-lookup"><span data-stu-id="1a11e-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="1a11e-117">В визуальном C#элементе <xref:System.Windows.Forms.Control.Click> события для каждой кнопки необходимо прикрепить к соответствующему обработчику событий в примере кода.</span><span class="sxs-lookup"><span data-stu-id="1a11e-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="1a11e-118">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="1a11e-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="1a11e-119">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a11e-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a11e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1a11e-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1a11e-121">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a11e-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="1a11e-122">Режимы выделения содержимого элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a11e-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
