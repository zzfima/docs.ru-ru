---
title: Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: a09262d2e874eebaa8c9224266f5eeb585a4f6ea
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630445"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="42d16-102">Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="42d16-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="42d16-103">Для размещения элемента управления <xref:System.Windows.Forms.ToolStripStatusLabel> в элементе <xref:System.Windows.Forms.StatusStrip> можно использовать свойство <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.</span><span class="sxs-lookup"><span data-stu-id="42d16-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="42d16-104">Свойство <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> определяет, заполняет ли элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> доступное пространство в элементе управления <xref:System.Windows.Forms.StatusStrip> автоматически.</span><span class="sxs-lookup"><span data-stu-id="42d16-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42d16-105">Пример</span><span class="sxs-lookup"><span data-stu-id="42d16-105">Example</span></span>  
 <span data-ttu-id="42d16-106">В примере кода ниже показано использование свойства <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> для размещения элемента управления <xref:System.Windows.Forms.ToolStripStatusLabel> в элементе <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="42d16-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="42d16-107">Для переключения значения свойства <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> выполняет исключающую операцию ИЛИ (XOR).</span><span class="sxs-lookup"><span data-stu-id="42d16-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="42d16-108">Чтобы использовать этот пример кода, компиляции и запуска приложения и нажмите кнопку **Middle (Spring)** на <xref:System.Windows.Forms.StatusStrip> переключите значение <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="42d16-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="42d16-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="42d16-109">Compiling the Code</span></span>  
 <span data-ttu-id="42d16-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="42d16-110">This example requires:</span></span>  
  
- <span data-ttu-id="42d16-111">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="42d16-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="42d16-112">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="42d16-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="42d16-113">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="42d16-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d16-114">См. также</span><span class="sxs-lookup"><span data-stu-id="42d16-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="42d16-115">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="42d16-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
