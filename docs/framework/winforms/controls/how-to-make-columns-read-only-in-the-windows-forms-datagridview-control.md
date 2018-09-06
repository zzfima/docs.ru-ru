---
title: Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: a8b5c0f9492941cf0e01e016d9fb097e1df44d2e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43802775"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="657e4-102">Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="657e4-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="657e4-103">Не все данные допускается изменять.</span><span class="sxs-lookup"><span data-stu-id="657e4-103">Not all data is meant for editing.</span></span> <span data-ttu-id="657e4-104">В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> столбца определяет, могут ли пользователи редактировать ячейки в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="657e4-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="657e4-105">Сведения о том, как сделать элемент управления доступным только для чтения, см. в разделе [как: Предотвращение добавления и удаления строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="657e4-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="657e4-106">Эта задача поддерживается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="657e4-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="657e4-107">Также см. в разделе [как: сделать только для чтения в Windows Forms DataGridView элемента управления с помощью конструктора](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="657e4-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="657e4-108">Программное определение столбца как доступного только для чтения</span><span class="sxs-lookup"><span data-stu-id="657e4-108">To make a column read-only programmatically</span></span>  
  
-   <span data-ttu-id="657e4-109">Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="657e4-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="657e4-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="657e4-110">Compiling the Code</span></span>  
 <span data-ttu-id="657e4-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="657e4-111">This example requires:</span></span>  
  
-   <span data-ttu-id="657e4-112">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1` и столбцом с именем `CompanyName`;</span><span class="sxs-lookup"><span data-stu-id="657e4-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
-   <span data-ttu-id="657e4-113">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="657e4-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657e4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="657e4-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="657e4-115">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="657e4-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="657e4-116">Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="657e4-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
