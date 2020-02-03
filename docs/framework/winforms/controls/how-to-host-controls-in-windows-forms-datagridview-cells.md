---
title: Элементы управления ведущего приложения в ячейках DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: a64521a15a272ca8140302f39d15e7f17e0c423b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736537"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="7bc87-102">Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bc87-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="7bc87-103">Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет несколько типов столбцов, что позволяет пользователям вводить и редактировать значения различными способами.</span><span class="sxs-lookup"><span data-stu-id="7bc87-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="7bc87-104">Если эти типы столбцов не удовлетворяют вашим потребностям ввода данных, вы можете создать собственные типы столбцов с ячейками, содержащими элементы управления по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="7bc87-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="7bc87-105">Для этого необходимо определить классы, производные от <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="7bc87-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="7bc87-106">Необходимо также определить класс, производный от <xref:System.Windows.Forms.Control> и реализующий интерфейс <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="7bc87-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="7bc87-107">В следующем примере кода показано, как создать столбец календаря.</span><span class="sxs-lookup"><span data-stu-id="7bc87-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="7bc87-108">В ячейках этого столбца отображаются даты с помощью обычных текстовых полей, однако при редактировании ячейки появляется элемент управления <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="7bc87-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="7bc87-109">Чтобы избежать необходимости повторно реализовать функции отображения текстового поля, класс `CalendarCell` является производным от класса <xref:System.Windows.Forms.DataGridViewTextBoxCell>, а не наследует класс <xref:System.Windows.Forms.DataGridViewCell> напрямую.</span><span class="sxs-lookup"><span data-stu-id="7bc87-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bc87-110">При наследовании от класса <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewColumn> и добавлении новых свойств к производному классу необходимо переопределить метод `Clone`, чтобы скопировать новые свойства во время операций копирования.</span><span class="sxs-lookup"><span data-stu-id="7bc87-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="7bc87-111">Кроме того, необходимо вызвать метод `Clone` базового класса, чтобы свойства базового класса скопировались в новую ячейку или столбец.</span><span class="sxs-lookup"><span data-stu-id="7bc87-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bc87-112">Пример</span><span class="sxs-lookup"><span data-stu-id="7bc87-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7bc87-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7bc87-113">Compiling the Code</span></span>  
 <span data-ttu-id="7bc87-114">В следующем примере требуется:</span><span class="sxs-lookup"><span data-stu-id="7bc87-114">The following example requires:</span></span>  
  
- <span data-ttu-id="7bc87-115">ссылки на сборки System и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7bc87-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc87-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7bc87-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="7bc87-117">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bc87-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7bc87-118">Архитектура элементов управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="7bc87-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="7bc87-119">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bc87-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
