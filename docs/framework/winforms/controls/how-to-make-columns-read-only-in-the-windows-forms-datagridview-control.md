---
title: Как выполнить Столбцы, сделайте доступным только для чтения в элементе управления DataGridView Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: e57f926208e67ce894b58bdfaf5d0c3e3815b2ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514885"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="18a98-102">Как выполнить Столбцы, сделайте доступным только для чтения в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18a98-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="18a98-103">Не все данные допускается изменять.</span><span class="sxs-lookup"><span data-stu-id="18a98-103">Not all data is meant for editing.</span></span> <span data-ttu-id="18a98-104">В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> столбца определяет, могут ли пользователи редактировать ячейки в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="18a98-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="18a98-105">Сведения о том, как сделать элемент управления доступным только для чтения, см. в разделе [как: Запретить добавление строк и удаления в Windows Forms элемента управления DataGridView](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="18a98-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="18a98-106">Эта задача поддерживается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="18a98-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="18a98-107">Также см. раздел [Как Определение столбцов только для чтения в Windows Forms с помощью конструктора элемента управления DataGridView](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="18a98-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="18a98-108">Программное определение столбца как доступного только для чтения</span><span class="sxs-lookup"><span data-stu-id="18a98-108">To make a column read-only programmatically</span></span>  
  
-   <span data-ttu-id="18a98-109">Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="18a98-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="18a98-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="18a98-110">Compiling the Code</span></span>  
 <span data-ttu-id="18a98-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="18a98-111">This example requires:</span></span>  
  
-   <span data-ttu-id="18a98-112">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1` и столбцом с именем `CompanyName`;</span><span class="sxs-lookup"><span data-stu-id="18a98-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
-   <span data-ttu-id="18a98-113">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18a98-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a98-114">См. также</span><span class="sxs-lookup"><span data-stu-id="18a98-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="18a98-115">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18a98-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="18a98-116">Практическое руководство. Предотвращение добавления и удаления в элементе управления DataGridView Windows Forms строк</span><span class="sxs-lookup"><span data-stu-id="18a98-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
