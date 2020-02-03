---
title: Предотвращение добавления и удаления строк в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: de8e0412faf8c3731f9356771b35a4a5d31b6ec7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728718"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f86f4-102">Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f86f4-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f86f4-103">Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="f86f4-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f86f4-104">Свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> указывает, имеется ли в наличии строка для ввода новых записей в нижней части элемента управления, свойство <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> указывает, могут ли строки быть удалены.</span><span class="sxs-lookup"><span data-stu-id="f86f4-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="f86f4-105">В следующем примере кода используются эти свойства, а также задается свойство <xref:System.Windows.Forms.DataGridView.ReadOnly%2A>, чтобы сделать элемент управления доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f86f4-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="f86f4-106">Эта задача поддерживается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f86f4-106">There is support for this task in Visual Studio.</span></span> <span data-ttu-id="f86f4-107">См. также раздел [как предотвратить добавление и удаление строк в элементе управления Windows Forms DataGridView с помощью конструктора](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f86f4-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f86f4-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f86f4-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f86f4-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f86f4-109">Compiling the Code</span></span>  
 <span data-ttu-id="f86f4-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f86f4-110">This example requires:</span></span>  
  
- <span data-ttu-id="f86f4-111">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="f86f4-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="f86f4-112">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f86f4-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86f4-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f86f4-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f86f4-114">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f86f4-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
