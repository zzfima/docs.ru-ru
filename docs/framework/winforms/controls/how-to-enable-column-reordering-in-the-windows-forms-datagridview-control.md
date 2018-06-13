---
title: Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: fbcafae2cb4e4cc320c31794269355d6312b95b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532588"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f2601-102">Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2601-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f2601-103">При разрешении изменения порядка столбцов в элементе управления <xref:System.Windows.Forms.DataGridView> пользователи могут переместить столбец в новое местоположение, перетащив заголовок столбца с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="f2601-103">When you enable column reordering in the <xref:System.Windows.Forms.DataGridView> control, users can move a column to a new position by dragging the column header with the mouse.</span></span> <span data-ttu-id="f2601-104">В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> определяет, могут ли пользователи перемещать столбцы.</span><span class="sxs-lookup"><span data-stu-id="f2601-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property value determines whether users can move columns to different positions.</span></span>  
  
 <span data-ttu-id="f2601-105">Эта задача поддерживается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f2601-105">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="f2601-106">См. также [как: Разрешить изменение порядка столбцов в Windows Forms управления DataGridView с помощью конструктора](http://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f2601-106">Also see [How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span></span>  
  
### <a name="to-enable-column-reordering-programmatically"></a><span data-ttu-id="f2601-107">Разрешение изменения порядка столбцов программным путем</span><span class="sxs-lookup"><span data-stu-id="f2601-107">To enable column reordering programmatically</span></span>  
  
-   <span data-ttu-id="f2601-108">Задайте для свойства <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f2601-108">Set the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2601-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f2601-109">Compiling the Code</span></span>  
 <span data-ttu-id="f2601-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f2601-110">This example requires:</span></span>  
  
-   <span data-ttu-id="f2601-111">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="f2601-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="f2601-112">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2601-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2601-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f2601-113">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="f2601-114">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2601-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="f2601-115">Практическое руководство. Замораживание столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2601-115">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
