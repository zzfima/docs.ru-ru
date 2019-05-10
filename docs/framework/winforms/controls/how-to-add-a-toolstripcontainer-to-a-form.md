---
title: Практическое руководство. Добавление в форму элемента управления ToolStripContainer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 6b35baac09ac47a25cc55877b2c94628f1b57111
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624074"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="70507-102">Практическое руководство. Добавление в форму элемента управления ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="70507-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="70507-103">В форму Windows Forms можно программно добавить контейнер <xref:System.Windows.Forms.ToolStripContainer> и заполнить его элементами управления.</span><span class="sxs-lookup"><span data-stu-id="70507-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70507-104">Пример</span><span class="sxs-lookup"><span data-stu-id="70507-104">Example</span></span>  
 <span data-ttu-id="70507-105">В следующем примере кода показано, как добавить <xref:System.Windows.Forms.ToolStripContainer> и <xref:System.Windows.Forms.ToolStrip> в форму Windows Forms, добавить элементы в <xref:System.Windows.Forms.ToolStrip> и как добавить <xref:System.Windows.Forms.ToolStrip> к <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> из <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="70507-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70507-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="70507-106">Compiling the Code</span></span>  
 <span data-ttu-id="70507-107">Для этого примера кода требуются:</span><span class="sxs-lookup"><span data-stu-id="70507-107">This code example requires:</span></span>  
  
- <span data-ttu-id="70507-108">ссылки на сборки System.Drawing, System.Windows.Forms и System.Xml.</span><span class="sxs-lookup"><span data-stu-id="70507-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="70507-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="70507-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="70507-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="70507-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="70507-111">См. также</span><span class="sxs-lookup"><span data-stu-id="70507-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="70507-112">Элемент управления ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="70507-112">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="70507-113">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="70507-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
