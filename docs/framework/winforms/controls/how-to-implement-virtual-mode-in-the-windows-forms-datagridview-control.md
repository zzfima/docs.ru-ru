---
title: Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: 064b58b64e0a9f55e3ef7d15b4962cfec514eff3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592403"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c77e9-102">Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c77e9-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c77e9-103">В примере кода ниже показано, как управлять большими наборами данных с помощью элемента управления <xref:System.Windows.Forms.DataGridView>, свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> которого присвоено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c77e9-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="c77e9-104">Полное описание этого примера кода, см. в разделе [Пошаговое руководство: Реализация виртуального режима в Windows Forms элемента управления DataGridView](implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c77e9-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c77e9-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c77e9-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c77e9-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c77e9-106">Compiling the Code</span></span>  
 <span data-ttu-id="c77e9-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c77e9-107">This example requires:</span></span>  
  
- <span data-ttu-id="c77e9-108">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="c77e9-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77e9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c77e9-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="c77e9-110">Пошаговое руководство: Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c77e9-110">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="c77e9-111">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c77e9-111">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c77e9-112">Виртуальный режим элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c77e9-112">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
