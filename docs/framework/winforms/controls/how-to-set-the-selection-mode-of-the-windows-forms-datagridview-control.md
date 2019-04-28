---
title: Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: 2e430dfb170943178f6db27c0bd2c1ef0f972882
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013118"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="95083-102">Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95083-102">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="95083-103">В следующем примере кода показано, как настроить <xref:System.Windows.Forms.DataGridView> элемент управления, щелкнув в любом месте в пределах строки автоматически выбирает всю строку, и поэтому можно выбрать только одну строку за раз.</span><span class="sxs-lookup"><span data-stu-id="95083-103">The following code example demonstrates how to configure a <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row automatically selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95083-104">Пример</span><span class="sxs-lookup"><span data-stu-id="95083-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="95083-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="95083-105">Compiling the Code</span></span>  
 <span data-ttu-id="95083-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="95083-106">This example requires:</span></span>  
  
- <span data-ttu-id="95083-107">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="95083-107">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="95083-108">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="95083-108">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95083-109">См. также</span><span class="sxs-lookup"><span data-stu-id="95083-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [<span data-ttu-id="95083-110">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95083-110">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="95083-111">Режимы выделения содержимого элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95083-111">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
