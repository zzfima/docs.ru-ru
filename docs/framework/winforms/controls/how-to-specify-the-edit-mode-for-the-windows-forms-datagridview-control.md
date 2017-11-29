---
title: "Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70bf241865eef3366444e1b4dc20c19adaff983e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="48442-102">Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48442-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="48442-103">По умолчанию пользователи могут редактировать содержимое текущего <xref:System.Windows.Forms.DataGridView> ячейки текстового поля, введя в него или нажав клавишу F2.</span><span class="sxs-lookup"><span data-stu-id="48442-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="48442-104">Ячейка переключается в режим редактирования при выполнении всех следующих условий:</span><span class="sxs-lookup"><span data-stu-id="48442-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
-   <span data-ttu-id="48442-105">Базовый источник данных поддерживает редактирование.</span><span class="sxs-lookup"><span data-stu-id="48442-105">The underlying data source supports editing.</span></span>  
  
-   <span data-ttu-id="48442-106"><xref:System.Windows.Forms.DataGridView> Элемент управления включен.</span><span class="sxs-lookup"><span data-stu-id="48442-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
-   <span data-ttu-id="48442-107"><xref:System.Windows.Forms.DataGridView.EditMode%2A> Значение свойства не является <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="48442-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
-   <span data-ttu-id="48442-108">`ReadOnly` Свойства ячеек, строк, столбцов и элемента управления имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="48442-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="48442-109">В режиме редактирования пользователь может изменить значение ячейки и нажмите клавишу ВВОД, чтобы внести изменения или ESC, чтобы вернуть исходное значение ячейки.</span><span class="sxs-lookup"><span data-stu-id="48442-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="48442-110">Можно настроить <xref:System.Windows.Forms.DataGridView> управления ячейку в режим редактирования, как только она становится текущей ячейкой.</span><span class="sxs-lookup"><span data-stu-id="48442-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="48442-111">В этом случае поведение клавиш ввод и ESC не изменяется, но ячейка остается в режиме редактирования после подтверждения или возврата значения.</span><span class="sxs-lookup"><span data-stu-id="48442-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="48442-112">Можно также настроить элемент управления, чтобы ячейки режим редактирования только в том случае, когда пользователи вводят в ячейке или только при нажатии клавиши F2.</span><span class="sxs-lookup"><span data-stu-id="48442-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="48442-113">Наконец, можно предотвратить ячеек в режим редактирования, за исключением того, при вызове <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="48442-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="48442-114">Чтобы изменить режим редактирования элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="48442-114">To change the edit mode of a DataGridView control</span></span>  
  
-   <span data-ttu-id="48442-115">Задать <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> свойство к соответствующему <xref:System.Windows.Forms.DataGridViewEditMode> перечисления.</span><span class="sxs-lookup"><span data-stu-id="48442-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="48442-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="48442-116">Compiling the Code</span></span>  
 <span data-ttu-id="48442-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="48442-117">This example requires:</span></span>  
  
-   <span data-ttu-id="48442-118">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="48442-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="48442-119">ссылки на сборки <xref:System> и <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="48442-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48442-120">См. также</span><span class="sxs-lookup"><span data-stu-id="48442-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="48442-121">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48442-121">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
