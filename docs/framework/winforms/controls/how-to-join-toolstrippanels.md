---
title: Практическое руководство. Соединение нескольких ToolStripPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: 297e3bfec9bb24fb2c06e903a5f32410618812d2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703677"
---
# <a name="how-to-join-toolstrippanels"></a><span data-ttu-id="7d01e-102">Практическое руководство. Соединение нескольких ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="7d01e-102">How to: Join ToolStripPanels</span></span>
<span data-ttu-id="7d01e-103">Элементы управления <xref:System.Windows.Forms.ToolStrip> можно подключать к <xref:System.Windows.Forms.ToolStripPanel> во время выполнения, благодаря чему обеспечивается гибкость приложений с интерфейсом MDI.</span><span class="sxs-lookup"><span data-stu-id="7d01e-103">You can join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel> at run time, which provides the flexibility of multiple-document interface (MDI) applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d01e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7d01e-104">Example</span></span>  
 <span data-ttu-id="7d01e-105">В примере кода ниже показано, как подключить элементы управления <xref:System.Windows.Forms.ToolStrip> к <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="7d01e-105">The following code example demonstrates how to join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d01e-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7d01e-106">Compiling the Code</span></span>  
 <span data-ttu-id="7d01e-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7d01e-107">This example requires:</span></span>  
  
-   <span data-ttu-id="7d01e-108">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7d01e-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7d01e-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7d01e-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7d01e-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="7d01e-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d01e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7d01e-111">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="7d01e-112">Практическое руководство. Руководство.</span><span class="sxs-lookup"><span data-stu-id="7d01e-112">How to: Use ToolStripPanels for MDI</span></span>](how-to-use-toolstrippanels-for-mdi.md)
