---
title: Указание режима редактирования для элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743763"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="9148a-102">Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9148a-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9148a-103">По умолчанию пользователи могут изменять содержимое ячейки текстового поля <xref:System.Windows.Forms.DataGridView>, вводя ее или нажав клавишу F2.</span><span class="sxs-lookup"><span data-stu-id="9148a-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="9148a-104">Это приведет к помещению ячейки в режим редактирования, если выполняются все перечисленные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="9148a-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="9148a-105">Базовый источник данных поддерживает редактирование.</span><span class="sxs-lookup"><span data-stu-id="9148a-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="9148a-106">Элемент управления <xref:System.Windows.Forms.DataGridView> включен.</span><span class="sxs-lookup"><span data-stu-id="9148a-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="9148a-107">Значение свойства <xref:System.Windows.Forms.DataGridView.EditMode%2A> не равно <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="9148a-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="9148a-108">Для свойств `ReadOnly` ячейки, строки, столбца и элемента управления устанавливается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9148a-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="9148a-109">В режиме редактирования пользователь может изменить значение ячейки и нажать клавишу ВВОД для фиксации изменения или ESC для возврата ячейки к исходному значению.</span><span class="sxs-lookup"><span data-stu-id="9148a-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="9148a-110">Можно настроить <xref:System.Windows.Forms.DataGridView> элемент управления таким образом, чтобы ячейка перейдет в режим правки сразу после того, как она станет текущей ячейкой.</span><span class="sxs-lookup"><span data-stu-id="9148a-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="9148a-111">Поведение клавиш ENTER и ESC в этом случае не меняется, но после фиксации или возврата ячейки остаются в режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="9148a-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="9148a-112">Можно также настроить элемент управления таким образом, чтобы ячейки перейдет в режим редактирования только тогда, когда пользователи вводят в ячейку или только когда пользователь нажмет клавишу F2.</span><span class="sxs-lookup"><span data-stu-id="9148a-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="9148a-113">Наконец, можно предотвратить переход ячеек в режим правки, кроме случая вызова метода <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="9148a-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="9148a-114">Изменение режима редактирования элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="9148a-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="9148a-115">Задайте для свойства <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> соответствующее перечисление <xref:System.Windows.Forms.DataGridViewEditMode>.</span><span class="sxs-lookup"><span data-stu-id="9148a-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9148a-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9148a-116">Compiling the Code</span></span>  
 <span data-ttu-id="9148a-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9148a-117">This example requires:</span></span>  
  
- <span data-ttu-id="9148a-118">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="9148a-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="9148a-119">ссылки на сборки <xref:System> и <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="9148a-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9148a-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9148a-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9148a-121">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9148a-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
