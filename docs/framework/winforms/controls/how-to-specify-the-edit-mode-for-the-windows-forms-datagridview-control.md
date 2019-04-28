---
title: Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: 7cb9278cd311d211ef95df238b930970ae472d05
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012949"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="6fea2-102">Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6fea2-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6fea2-103">По умолчанию, пользователи могут изменять содержимое текущего <xref:System.Windows.Forms.DataGridView> ячейке текстового поля, введя его или нажав клавишу F2.</span><span class="sxs-lookup"><span data-stu-id="6fea2-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="6fea2-104">Таким образом ячейки в режиме редактирования, если выполняются все из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="6fea2-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="6fea2-105">Базовый источник данных поддерживает редактирование.</span><span class="sxs-lookup"><span data-stu-id="6fea2-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="6fea2-106"><xref:System.Windows.Forms.DataGridView> Включен элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6fea2-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="6fea2-107"><xref:System.Windows.Forms.DataGridView.EditMode%2A> Значение свойства не является <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="6fea2-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="6fea2-108">`ReadOnly` Свойства ячейки, строки, столбца и управления имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="6fea2-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="6fea2-109">В режиме редактирования пользователя можно изменить значение ячейки и нажмите клавишу ВВОД для подтверждения изменений или ESC, чтобы отменить изменение для ячейки в исходное значение.</span><span class="sxs-lookup"><span data-stu-id="6fea2-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="6fea2-110">Можно настроить <xref:System.Windows.Forms.DataGridView> управления позволит ячейка переходит в режим редактирования, как только она становится текущей ячейкой.</span><span class="sxs-lookup"><span data-stu-id="6fea2-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="6fea2-111">В этом случае поведение клавиш ввод и ESC не изменяется, но ячейка остается в режиме редактирования после фиксации или вернуть значение.</span><span class="sxs-lookup"><span data-stu-id="6fea2-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="6fea2-112">Элемент управления также можно настроить таким образом, чтобы ячейки режим редактирования только в том случае, когда пользователь вводит в ячейку или только в том случае, при нажатии клавиши F2.</span><span class="sxs-lookup"><span data-stu-id="6fea2-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="6fea2-113">Наконец, можно предотвратить ячейки в режим редактирования, за исключением случаев, когда вы вызываете <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6fea2-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="6fea2-114">Чтобы изменить режим правки элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="6fea2-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="6fea2-115">Задайте <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> свойство в соответствующий <xref:System.Windows.Forms.DataGridViewEditMode> перечисления.</span><span class="sxs-lookup"><span data-stu-id="6fea2-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6fea2-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6fea2-116">Compiling the Code</span></span>  
 <span data-ttu-id="6fea2-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6fea2-117">This example requires:</span></span>  
  
- <span data-ttu-id="6fea2-118">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="6fea2-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="6fea2-119">ссылки на сборки <xref:System> и <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="6fea2-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fea2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6fea2-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6fea2-121">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6fea2-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
