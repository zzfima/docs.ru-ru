---
title: Практическое руководство. Создание формы MDI с использованием элементов управления ToolStripPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: 9b3297acabbb05c25ae195acbb6fb9274ad02651
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725393"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="fb4b3-102">Практическое руководство. Создание формы MDI с использованием элементов управления ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="fb4b3-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="fb4b3-103">Можно создать форму с многодокументным интерфейсом (MDI) документа, имеющую элементы управления <xref:System.Windows.Forms.ToolStrip> по всем четырем сторонам формы.</span><span class="sxs-lookup"><span data-stu-id="fb4b3-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb4b3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fb4b3-104">Example</span></span>  
 <span data-ttu-id="fb4b3-105">В следующем примере кода показано, как использовать закрепленные элементы управления <xref:System.Windows.Forms.ToolStripPanel> в окне MDI с четырьмя элементами управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="fb4b3-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="fb4b3-106">В примере метод <xref:System.Windows.Forms.ToolStripPanel.Join%2A> присоединяет элементы управления <xref:System.Windows.Forms.ToolStrip> к соответствующим элементам управления <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="fb4b3-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fb4b3-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fb4b3-107">Compiling the Code</span></span>  
 <span data-ttu-id="fb4b3-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="fb4b3-108">This example requires:</span></span>  
  
-   <span data-ttu-id="fb4b3-109">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fb4b3-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fb4b3-110">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fb4b3-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fb4b3-111">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="fb4b3-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb4b3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fb4b3-112">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- <xref:System.Windows.Forms.ToolStripPanel.Join%2A>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="fb4b3-113">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fb4b3-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
