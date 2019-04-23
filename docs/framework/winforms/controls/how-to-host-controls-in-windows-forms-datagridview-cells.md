---
title: Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 008b6da56c3428d0edcc44778b4d3bef1a52c443
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194205"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="bfb2a-102">Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfb2a-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="bfb2a-103">Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет несколько типов столбцов, что позволяет пользователям вводить и редактировать значения различными способами.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="bfb2a-104">Если эти типы столбцов не удовлетворяют вашим потребностям ввода данных, вы можете создать собственные типы столбцов с ячейками, содержащими элементы управления по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="bfb2a-105">Для этого необходимо определить классы, производные от <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="bfb2a-106">Необходимо также определить класс, производный от <xref:System.Windows.Forms.Control> и реализующий интерфейс <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="bfb2a-107">В следующем примере кода показано, как создать столбец календаря.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="bfb2a-108">В ячейках этого столбца отображаются даты с помощью обычных текстовых полей, однако при редактировании ячейки появляется элемент управления <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="bfb2a-109">Чтобы избежать необходимости повторно реализовать функции отображения текстового поля, класс `CalendarCell` является производным от класса <xref:System.Windows.Forms.DataGridViewTextBoxCell>, а не наследует класс <xref:System.Windows.Forms.DataGridViewCell> напрямую.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfb2a-110">При наследовании от класса <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewColumn> и добавлении новых свойств к производному классу необходимо переопределить метод `Clone`, чтобы скопировать новые свойства во время операций копирования.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="bfb2a-111">Кроме того, необходимо вызвать метод `Clone` базового класса, чтобы свойства базового класса скопировались в новую ячейку или столбец.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfb2a-112">Пример</span><span class="sxs-lookup"><span data-stu-id="bfb2a-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bfb2a-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bfb2a-113">Compiling the Code</span></span>  
 <span data-ttu-id="bfb2a-114">В следующем примере требуется:</span><span class="sxs-lookup"><span data-stu-id="bfb2a-114">The following example requires:</span></span>  
  
-   <span data-ttu-id="bfb2a-115">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="bfb2a-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bfb2a-116">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bfb2a-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bfb2a-117">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="bfb2a-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb2a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bfb2a-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="bfb2a-119">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfb2a-119">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bfb2a-120">Архитектура элементов управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="bfb2a-120">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="bfb2a-121">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfb2a-121">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
